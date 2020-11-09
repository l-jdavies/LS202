# Tutorial 1: building first webpage

[https://learn.shayhowe.com/html-css/building-your-first-web-page/](https://learn.shayhowe.com/html-css/building-your-first-web-page/)

## Definitions

HTML = HyperText Markup Language

CSS = Cascading Style Sheets

### Elements

Elements are designators that define the structure and content of objects within a page. Elements include headings and paragraphs, `<a>`, `<div>`, `<span>`, `<strong>`, and `<em>` and others.

Elements are defined by the use of angle brackets (`<` `>`) surrounding the element name.

### Tags

Angle brackets surrounding an element creates a tag. Tags most commonly occur in pairs of opening and closing tags. An opening tag marks the beginning of an element, e.g. `<div>` and a closing tag marks the end of an element, such as `</div>`.

### Attributes

Attributes are properties that provide additional information about an element. The most common attributes include the `id` attribute, which identifies an element and the `class` attribute, which classifies an element. The `src` attribute specifies a source for embeddable content and the `href` attribute provides a hyperlink reference to a linked resource.

Attributes are defined within the opening tag, after an element's name. Generally attributes include a name and value, for example this anchor element containing a `href` attribute:

```ruby
<a href="https://launchschool.com">Launch School</a>
```

![Tutorial%201%20building%20first%20webpage%20ad3b621101e5433a9243fa0c29ef3fb8/Untitled.png](Tutorial%201%20building%20first%20webpage%20ad3b621101e5433a9243fa0c29ef3fb8/Untitled.png)

## Setting up HTML document structure

All HTML documents have a required structure that includes the following declaration and elements: `<!DOCTYPE html>` , `<html>`, `<head>`, and `<body>`.

The document type declaration `<!DOCTYPE html>` informs the web browser of the version of HTML is being used - if you don't specify a version then the most recent one will be used.

This is followed by `<html>` element and inside that is the `<head>` element. The `<head>` element identifies the top of the document and contains metadata about the page. The content inside `<head>` isn't displayed on the webpage. It may include the document title, which is displayed on the title bar in the browser window, links to any external files or other metadata.

All visible content within the webpage occurs within the `<body>` element. A typical HTML document looks like this:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>Hello World</title>
  </head>
  <body>
    <h1>Hello World</h1>
    <p>This is a web page.</p>
  </body>
</html>
```

## Self-closing elements

In the previous example, the `<meta>` element had only one tag and didn’t include a closing tag. Fear not, this was intentional. Not all elements consist of opening and closing tags. Some elements simply receive their content or behavior from attributes within a single tag. The `<meta>` element is one of these elements. The content of the previous `<meta>` element is assigned with the use of the charset attribute and value. Other common selfclosing elements include

- `<br>`
- `<embed>`
- `<hr>`
- `<img>`
- `<input>`
- `<link>`
- `<meta>`
- `<param>`
- `<source>`
- `<wbr>`

## Common CSS terms

### Selectors

A selector designates which HTML element or elements the CSS style should be applied to. Selectors may include a combination of different qualifiers to select unique elements - it depends how specific you want to be. 

Selectors generally target an attribute or value, such as `id` or `class` or target the type of element, such as `<h1>`. Selectors are followed by curly braces, which contain the styles that will be applied to the selected element. For example a selector that targets all `<p>` elements:

```css
p { ... }
```

### Properties

Once an element is selected, a property determines the style that will be applied to the element. Property names fall after a selector, within the curly brackets, `{}`, and immediately preceding a colon, `:`. There are numerous properties we can use, such as `background`, `color`, `font-size`, `height`, and `width`, and new properties are often added. In the following code, we are defining the `color` and `font-size` properties to be applied to all `<p>` elements.

```css
p {
  color: ...;
  font-size: ...;
}
```

![Tutorial%201%20building%20first%20webpage%20ad3b621101e5433a9243fa0c29ef3fb8/Untitled%201.png](Tutorial%201%20building%20first%20webpage%20ad3b621101e5433a9243fa0c29ef3fb8/Untitled%201.png)

## Working with Selectors

There are different types of selectors that indicate which HTML element should be styled. The most common selectors are: type, class and id selectors.

### Type selectors

Type selectors target elements by their element type. For example, targeting all division elements, `<div>`

The CSS code:

```css
div {
    ...
}
```

Would select all HTML code within the following elements:

```html
<div>...</div>
```

### Class selectors

Class selectors select an element based on the elements `class` attribute value. Class selectors are more specific than type selectors. Class selectors allow us to apply the same styles to different elements at once by using the same class attribute value across multiple elements. Class selectors are denoted by a leading period followed by the `class` attribute value.

For example, selecting any element with the `class` attribute value of `testing`:

```css
.testing {
         ....
}
```

Would select all HTML code within the following elements (both division and paragraph elements):

```html
<div class="testing">...</div>
<p class="testing">...</p>
```

### ID selectors

ID selectors are more precise than class selectors because they only target one unique element at a time. Regardless of which type of element they appear on, an `id` attribute can only be used once per page. They should only be used for significant elements.

Within CSS, ID selectors are denoted by a leading `#` followed by the `id` attribute value. For example, selecting an element with an `id` attribute value of `"example_id"` :

```css
#example_id {
             ...
}
```

Would select all HTML code within the following element:

```html
<div id="example_id">...</div>
```

## Referencing CSS

CSS files need to be referenced within the HTML. The best practice is include all the CSS styles in a single external stylesheet, which is referenced from within the `<head>` element of the HTML document. Within the `<head>` element the `<link>` element is used to define the relationship between the HTML and CSS file. The `rel` attribute with the value `"stylesheet"` is used to specify the relationship and the `href` attribute is used to identify the path of the CSS file.

```html
<head>
  <link rel="stylesheet" href="main.css">
</head>
```

## Using CSS Resets

Each web browser has its own default styles for different elements. To ensure cross-browser compatibility CSS resets have become widely used. CSS resets take common HTML elements with a predefined style and provide one unified style for all browsers. The resets generally involve removing sizing, margins, paddings or additional styles. Because CSS is a top-down language the reset needs to be at the top of the stylesheet.

There are several different resets available, the most popular is Eric Meyer's reset, which includes styles for the new HTML5 elements.