# CSS resets

CSS rests over-ride browser styling defaults. This is important because browser styling defaults differ between browsers and can result in a webpage rendering differently on different browsers. CSS rests will usually set a default font, zero out margins and padding, and eliminate browser-specific styling on input controls.

Resets are indispensable, particularly when it comes to margins and padding. 

The three most popular CSS resets are:

- [Eric Meyer's reset](http://meyerweb.com/eric/tools/css/reset/)
- [Normalize.css](http://necolas.github.io/normalize.css/)
- [Tantek Celik's whitespace reset](http://cssreset.com/scripts/undohtml-css-tantek-celik/).

[CSS Tools: Reset CSS](https://www.notion.so/CSS-Tools-Reset-CSS-e0a65ec9421f4df5b5c69dc1f485b542)

[Normalize.css: Make browsers render all elements more consistently.](https://www.notion.so/Normalize-css-Make-browsers-render-all-elements-more-consistently-40a6ea4afcdd4f788b2374b21ce73749)

[‘undohtml.css’ – Tantek Celik | CSS Reset](https://www.notion.so/undohtml-css-Tantek-Celik-CSS-Reset-418de02eb8c74af2b240f774e402ff3c)

Resets vary in aggressiveness and can be customised.

This is the one Launch School uses, a custom version of Tantek Celik's reset:

```css
/*
----------------------------------------
Tantek Celik's Whitespace Reset
     Author:    Tantek Celik, Shane Riley
    Version:    (CC) 2010 Some Rights Reserved - http://creativecommons.org/licenses/by/2.0
Description:  Resets default styling of browsers to a common base
----------------------------------------
*/

ul, ol { list-style: none; }
h1, h2, h3, h4, h5, h6, pre, code { font-size: 1em; }
ul, ol, li, h1, h2, h3, h4, h5, h6, pre, form, body, html, p, blockquote,
fieldset, input, dl, dt, dd, figure, figcaption {
  margin: 0;
  padding: 0;
}
a img, :link img, :visited img, fieldset { border: none; }
address { font-style: normal; }
header, section, article, nav, footer, hgroup, details, summary, figure, main {
  display: block;
}
mark {
  color: inherit;
  background-color: transparent;
}
abbr { border: none; }
summary::-webkit-details-marker { display: none; }
```

The reset does the following:

- removes the bullets on ordered and unordered lists.
- sets all headings and a few other items to use the same font size.
- sets the padding and margins on most `block` elements to 0.
- removes the border that surrounds images inside links on older browsers.
- removes the border on `fieldset`.
- converts `address` elements to look like regular text.
- sets newer HTML elements to `display: block`, in case the user has an old browser that defaults to `inline`.
- removes garish colors from the `mark` element.
- removes the bottom border from `abbr` elements.
- removes the toggle marker from the `summary` element.