# Adding images to web pages

## The `img` element

`<img>` is a self closing tag that tells the browser to load and display a foreground image from a separate resource. The tag has four attributes of importance:

- The `src` attribute is required. It uses the same URL format as in an `<a>` tag. The URL can be relative, root-relative or absolute.
- `alt` is optional but should be used. It contains a description of the image and is used by screen readers or is displayed if an image cant be rendered correctly. Search engines use `alt` to index images and without this attribute code will fail the W3C validator.
- `width` and `height` are optional. They enable the width and height of the image to be specified in pixels but the HTML attributes are overridden by the CSS properties in the rendered version of the webpage.

```html
<img src="lucrezia.jpg" alt="Da Vinci's Smarter Sister, Lucrezia"
     width="800" height="600" />  
```

## Figure and Figcaption

The `figure` element can be used to add a caption to a figure. The `figure` element can be used without `figcaption` and they should only be used if the media is referenced in the text and the media requires a caption. Anything that is just decoration, like a logo or background image, doesn't need a `figure` element.

```html
<figure>
  <img src="masthead.jpg" alt="Sunset over the forest" />
  <figcaption>The sun sets over the dense forest</figcaption>
</figure>
```

## Images as links

Any non-interactive HTML element can be used as a link i.e. images can be used but form controls cant. To make an image clickable and have it link to another page, an `img` tag needs to be placed inside an `a` tag:

```html
<a href="url-of-link">
  <img src="url-of-image" alt="alt-text" />
</a>
```

The URL of the link is typically different to the URL of the image but it doesn't have to be. If they are the same then the link can open a new page with just the image displayed.

## Background images

Background images can be added to an entire page or just an element by applying the `background` or `background-image` property. Background images will appear behind the content for the element that request the background and all of its descendants. For a background to appear on an entire page, the property should be specified in the `body` selector. A background can be applied to any selector. For example:

```html
<section>
  Sint duis dolor consectetur ad nostrud sint. Occaecat reprehenderit officia ex
  duis velit veniam magna labore.
</section>

<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">Work</a></li>
    <li><a href="#">Play</a></li>
  </ul>
</nav>
```

```css
html {
  font-size: 32px;
}

body {
  background-image:
    url("http://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/gradient-background.png");
}

section {
  display: inline-block;
  width: 500px;
}

nav {
  background-image:
    url("http://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/blurry.png");
  display: inline-block;
  height: 200px;
  width: 250px;
}
```

There are several other background properties you can provide with a background image, including the size of the image, the positioning, and repeat counts.

```css
body {
  background-size: 25%;
}
```