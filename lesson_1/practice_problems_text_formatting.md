1. Create an HTML page with a single paragraph of text. Write CSS to set the font size for most elements on the page to 20px (you may ignore headers, subscripts, and other items that often have a different size).

```html
<body>
  <p>Example text</p>
</body>
```

```css
body {
  font-size: 20px;
}
```

2. Change the font family for the page from the previous problem to a sans-serif font.

```css
body {
  font-size: 20px;
  font-family: sans-serif;
}
```

3. Change the CSS for the previous problem to give the browser a choice one of three fonts (Tahoma, Trebuchet MS, Verdana), depending on what is available, before it uses the default sans-serif font.

```css
body {
  font-size: 20px;
  font-family: Tahoma, "Trebuchet MS", Verdana, sans-serif;
}
```

4. Change the text from the previous problem to italic.

```css
body {
  font-size: 20px;
  font-family: Tahoma, "Trebuchet MS", Verdana, sans-serif;
  font-style: italic;
}
```

5. Change the CSS from the previous problem to boldface (keep the italics).

```css
body {
  font-size: 20px;
  font-family: Tahoma, "Trebuchet MS", Verdana, sans-serif;
  font-style: italic;
  font-weight: bold;
}
```

6. Change the CSS from the previous problem to increase the line height to 2.5 times its default height.

```css
body {
  font-size: 20px;
  font-family: Tahoma, "Trebuchet MS", Verdana, sans-serif;
  font-style: italic;
  font-weight: bold;
  line-height: 2.5;
}
```

7. Change the CSS you wrote in questions 1-6 to a shorthand form that uses precisely one property. The output should not change.

```css
body {
  font: italic bold 20px/2.5 Verdana, "Trebuchet MS", Tahoma, sans-serif;
}
```

8. Change the CSS from the previous problem to right-align the text within the paragraph:

```css
body {
  text-align: right;
  font: italic bold 20px/2.5 Verdana, "Trebuchet MS", Tahoma, sans-serif;
}
```

9. Change the CSS from the previous problem to center-align the text within the paragraph:

```css
body {
  text-align: center;
  font: italic bold 20px/2.5 Verdana, "Trebuchet MS", Tahoma, sans-serif;
}
```

10. Change the CSS from the previous problem to fully justify the text within the paragraph:

```css
body {
  text-align: center;
  font: italic bold 20px/2.5 Verdana, "Trebuchet MS", Tahoma, sans-serif;
}
```

11. Change the CSS from the previous problem to indent the start of the paragraph by 4em.

```css
body {
  text-indent: 4em;
}
```

12. Write the CSS needed to reproduce this screenshot:

You should use this HTML:
```html
<article>
  <header>
    <h1>Finessing `feColorMatrix`</h1>
  </header>
  <p>
    Harness the power of <code>feColorMatrix</code> to create detailed
    filters, with Una Kravets as your guide.
  </p>
</article>
```
The h1 heading uses the Georgia font while the code element uses the browser's default monospace font. The remaining text uses a 14px sans-serif font, with Helvetica and Arial preferred.

```css
h1 {
  font-family: Georgia;
}

body {
  font-family: Helvetica, Arial, sans-serif;
  font-size: 14px;
}

code {
  font-family: monospace;
  font-style: italic;
  text-decoration: underline;
}
```

13. Change the CSS from the previous problem to display the h1 element text in blue, and the code text in green.

```css
h1 {
  font-family: Georgia;
  color: blue;
}

body {
  font-family: Helvetica, Arial, sans-serif;
  font-size: 14px;
}

code {
  font-family: monospace;
  font-style: italic;
  text-decoration: underline;
  color: green;
}
```

14. Write the CSS needed to reproduce this screenshot:

You should use this HTML:
```html
<p>That episode was <mark>un<strong>be<em>lieve</em></strong>able</mark>!</p>
```

The font highlighted in yellow is Courier; use a backup font of monospace. The text uses four font sizes - 12px, 15px, 18px and 20px.

```css
p {
  font-size: 18px
}

mark {
  font-family: courier, monospace;
  background: yellow;
  font-size: 12px;
}

strong {
  font-weight: bold; /*not required*/
  font-size: 15px;
}

em {
  font-style: italic; /*not required*/
  font-size: 20px;
  text-transform: uppercase;
}
```

15. Create some HTML with this paragraph:
```
<p>
  The Creating Hyperlinks section of Getting to Know HTML discusses
  hyperlinks, or anchors. Be sure to work both "In Practice" sections; they
  pick up from where you left off in an earlier reading assignment.
</p>
```

Convert the text Getting to Know HTML to a hypertext link to this URL:
```
http://learn.shayhowe.com/html-css/getting-to-know-html/#creating-hyperlinks
```

The link should open in a new browser tab or window. Add CSS to remove the underline and change the color to red.

```html
<p>
  The Creating Hyperlinks section of <a href="http://learn.shayhowe.com/html-css/getting-to-know-html/#creating-hyperlinks" target="_blank">Getting to Know HTML</a> discusses
  hyperlinks, or anchors. Be sure to work both "In Practice" sections; they
  pick up from where you left off in an earlier reading assignment.
</p>
```

```css
a {
  text-decoration: none;
  color: red;
}
```
