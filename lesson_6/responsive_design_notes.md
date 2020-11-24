# Responsive Design

CSS media queries enable webpages to display differently on different output devices.

## Media queries

Media queries define styles that change based on the current size of the browser window.

```css
a {
  color: #f00;
}

@media (max-width: 480px) {
  a {
    color: #06c;
  }
}
```

The words `not` and `and` can also be used in addition to selecting different media types such as `screen` `print` or `speech` . The most common is a combination of `screen` media type along with a `min-width` or `max-width` :

```css
@media screen and (max-width: 1600px) {
  /* CSS for 1600px (or smaller) screens (no printers!) */
}
```

[Using media queries - CSS: Cascading Style Sheets | MDN](https://www.notion.so/Using-media-queries-CSS-Cascading-Style-Sheets-MDN-4d9108602b994f449575614e33e99a1b)

### Mobile-first or desktop-first

When designing a website the decision needs to be made - will mobile or desktop devices be the primary device? The primary device is the device the CSS expects when no media query is active. Most developers use a mobile-first approach, then use media queries to handle progressively larger devices. 

```css
/* CSS for all cell phones and shared cross-browser CSS */

@media screen and (min-width: 481px) {
  /* CSS for tablets and larger */
}

@media screen and (min-width: 961px) {
  /* CSS for small desktop and laptop screens and larger */
}

@media screen and (min-width: 1501px) {
  /* CSS for large laptop and desktop displays */
}

@media print {
  /* CSS for printers */
}
```

Development starts in the section of the CSS file with no media query. Because colours don't often change on different devices, they usually appear in the top-most section. As the first media query specifies a min screen size of 481px, any CSS intended solely for small screens should also to stated in the top-most section.

The remaining screen queries are used to provide CSS that applies to the specific devices. There's also a media query for `print` that could be used to turn all colours into black and white for printing.

A mobile-first approach usually results in faster downloads on mobile devices, while the desktop-first approach is slower. The mobile-first is generally considered best practice. 

### Breakpoints

The different sizes stated in the code above are called breakpoints. Rather than trying to guess what type of device has each size screen (like has been done in the comments), it's better to think about what layout works best over a particular range of screens.

### Emulating devices on Google Chrome

To test what a page will look like on different devices, the emulation tool can be used in the developers toolbar. The emulation tool looks like a mobile ontop of a tablet. Different devices can be selected from the 'responsive' drop-down. It's also possible to simulate different connection speeds by choosing a mid-tier or low-tier mobile.

### Using webpage on multiple devices

If an application has been designed with responsiveness in mind, then a `<meta>` element needs to be added into the `<head>` part of the HTML. It tells mobile devices how to handle the page. Without it, devices will often display a miniaturised version of the page instead of displaying the mobile page described in the CSS media query.

```html
<meta name="viewport" content="width=device-width, initial-scale=1" /> 
```

## Fluid and liquid layouts

Liquid layouts often use percentage values for widths to maintain the same width ratios for content areas as the browser width changes.

Example of a liquid layout:

```html
<main>
  <article class="content">
    Enim Lorem aliqua anim nulla labore nulla ullamco. Deserunt fugiat duis ex
    dolor. Ex laboris ad officia minim quis.  Incididunt eu reprehenderit
    ullamco eiusmod dolor pariatur mollit qui. Officia aliqua velit deserunt
    adipisicing duis minim minim tempor.
  </article>

  <aside class="sidebar">
    Proident cillum ad cillum minim magna. Duis nulla est est non sunt. Est
    culpa laborum velit dolor.
  </aside>
</main>
```

```css
html {
  font-size: 16px;
}

body, article, p {
  margin: 0;
  padding: 0;
}

body {
  margin: 0;
  padding: 0.5rem;
}

main {
  clear: both;
  overflow: hidden;
  padding-bottom: 1.5rem;
}

.content,
.sidebar {
  box-sizing: border-box;
  float: left;
  padding: 20px 30px;
}

.content {
  background-color: pink;
  width: 70%;
}

.sidebar {
  background-color: cyan;
  width: 30%;
}
```

We can set `overflow` on the sidebar to either `hidden` or `auto` to achieve the same effect. However, there are some differences between these two values.

With `hidden`, the browser crops any content that doesn't fit inside the sidebar's container.

With `auto`, the browser doesn't crop content, but it may show unwanted scrollbars on the sidebar.

### Fluid layout

Liquid layouts usually take up the full width of the browser window. To restrict the expansion or collapse of the browser, a fluid layout should be used. Once the window reaches one of the limits, the elements will stop expanding or collapsing and will remain fixed in width, even if the browser width continues to change width. Fluid layouts expand and collapse like a liquid up to a point, then they become fixed once a browser reaches a certain size.

To convert to liquid layout to a fluid layout, a min-width and max-width is set on the container:

```css
main {
  max-width: 1000px;
  min-width: 500px;
}

.content,
.sidebar {
  padding: 20px 30px;
}

.content {
  box-sizing: border-box;
  float: left;
  width: 70%;
}

.sidebar {
  overflow: hidden;
}
```