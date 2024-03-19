# test-landing-page

Dummy landing page created using the project details provided by [The Odin Project](https://www.theodinproject.com/lessons/foundations-landing-page).

## Table of Contents

- [Before attempting project](#before-the-attempt)
- [Durring the attempt](#during-attempt)
  - [Header](#header)
  - [Hero](#hero)
  - [Members Info](#members-info)
  - [Quote](#quote)

## Before the attempt

Below is what the landing page template looks like and will be following it as a guide. I will try my best to only use use flexbox wherever it seems ideal to do so. Might pull images from one of my hobbies for motivation.
![Template](./notes/01.png)

Below is the typography:
![Typography](./notes/02.png)

## During the attempt

### Header

I had a little trouble figuring out how to get the `background-color` for the header to stretch the whole screen while also making sure the header content doesn't exceed a specific width but also shrinks when the viewport shrinks.

```html
<header>
  <div class="header-container">
    <img class="logo" src="./img/hololive-icon.png" alt="hololive" />
    <ul class="header-links">
      <li><a href="#">TOP</a></li>
      <li><a href="#">NEWS</a></li>
      <li><a href="#">ABOUT</a></li>
    </ul>
  </div>
</header>
```

```css
header {
  background-color: #1f2937;
  padding: 1rem;
}

/* content for header */
.header-container {
  max-width: 65rem;
  margin-inline: auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

I placed the `background-color` inside header so it can be stretched to it's parent container which is body(entire viewport). Then I wrapped the actual header content into a container where I put a `max-width` to stop it from growing too big and then centering/spacing.

### Hero

The tricky part here was trying to get the image to fit into it's parent container while also wanting it to wrap to another line whenever it shrinks down too much.

```css
/* hero content */
.hero-container {
  max-width: 65rem;
  margin-inline: auto;
  display: flex;
  justify-content: space-between;
  gap: 3rem;
  flex-wrap: wrap;
  padding-block: 5rem;
}

.hero-text,
.hero-img {
  flex: 1;
}

.hero-img {
  min-width: 50%;
}
```

This is the only way I could think of keeping equal space between the two flex children while also wrapping onto a new line whenever the image gets too small.

### Members Info

This section was fairly easy, I also made a big realization that it is better to use a specific width in pixels when combining width and `flex-grow`, `flex-shrink`, and `flex-basis`. Before, I used percent values which would always give me unwanted behavior due to the width value constantly changing whenever I resize the viewport. So it's overall more consistent to set a specific width when using these properties at the same time as well as `flex-wrap`.

So I changed this:

```css
.hero-img {
  min-width: 50%;
}
```

into this:

```css
.hero-img {
  min-width: 520px;
}
```

I applied these changes when creating the cards for the members section as well.

### Quote

Very simple quote added near the bottom. The challenge here was fiddling with the `background-image`.

```css
.quote {
  background-color: #e5e7eb;
  padding-block: 5rem;
  background-image: url(./img/yagoo.png);
  background-repeat: no-repeat;
  background-size: 40%;
  background-position: right 50% top 35%;
}
```

There were a lot of options for background-size, but I needed it to be a specific size so putting in a value instead of `contain` or `cover` here works perfectly. And then simply moving it around using `background-position`.

[BACK TO TOP](#test-landing-page)
