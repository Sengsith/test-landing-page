# test-landing-page

Dummy landing page created using the project details provided by [The Odin Project](https://www.theodinproject.com/lessons/foundations-landing-page).

## Before attempting project

Below is what the landing page template looks like and will be following it as a guide. I will try my best to only use use flexbox wherever it seems ideal to do so. Might pull images from one of my hobbies for motivation.
![Template](./notes/01.png)

Below is the typography:
![Typography](./notes/02.png)

## During the attempt

### Header

I had a little trouble figuring out how to get the background color for the header to stretch the whole screen while also making sure the header content doesn't exceed a specific width but also shrinks when the viewport shrinks.

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

I placed the background color inside header so it can be stretched to it's parent container which is body(entire viewport). Then I wrapped the actual header content into a container where I put a max-width to stop it from growing too big and then centering/spacing.
