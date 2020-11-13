# Lists overview

Although there are a variety of lists used on the web, HTML only has 6 tags to implement three list types:

- unordered
- ordered
- description

## Unordered lists

Used for lists that don't use a visual numbering or naming system for each item, instead the items are displayed with a bullet point. Unordered lists uses the HTML tags `<ul>` and `<li>`.

```html
<ul>
  <li>Red</li>
  <li>Orange</li>
  <li>Yellow</li>
  <li>Green</li>
  <li>Blue</li>
  <li>Indigo</li>
  <li>Violet</li>
</ul>
```

## Ordered lists

By default ordered lists render a vertical list of numbers but that can be changed to roman numerals or alphabetic letters. Unordered lists use the `<ol>` and `<li>` tags.

```html
<ol>
  <li>Red</li>
  <li>Orange</li>
  <li>Yellow</li>
  <li>Green</li>
  <li>Blue</li>
  <li>Indigo</li>
  <li>Violet</li>
</ol>
```

## Description lists

Description lists were called definition lists before HTML5 and they contain a list of terms and definitions with the definitions indented below the term. HTML uses the `<dl>` `<dt>` and `<dd>` tags.

```html
<dl>
  <dt>Unordered</dt>
  <dd>A simple list with bullets.</dd>
  <dd>A plain list with no bullets or sequence numbers.</dd>

  <dt>Ordered</dt>
  <dd>A simple list with sequence numbers or letters.</dd>

  <dt>Description</dt>
  <dt>Definition</dt>
  <dd>A list with terms and definitions.</dd>
</dl>
```

![Lists%20overview%20132c950d1764444ba8ca4e2a608cea99/Untitled.png](Lists%20overview%20132c950d1764444ba8ca4e2a608cea99/Untitled.png)

## Nested lists

Lists can be nested with any other type of list. For example:

```html
<dl>
  <dt>Unordered</dt>
  <dd>A simple list with bullets.</dd>
  <dd>A plain list with no bullets or sequence numbers.</dd>
  <dd>
    <ul>
      <li>Red</li>
      <li>Green</li>
      <li>Blue</li>
    </ul>
  </dd>

  <dt>Ordered</dt>
  <dd>A simple list with a visible sequence.</dd>
  <dd>
    <ol>
      <li>Red</li>
      <li>Green</li>
      <li>Blue</li>
    </ol>
  </dd>

  <dt>Description</dt>
  <dt>Definition</dt>
  <dd>A list with terms and definitions.</dd>
  <dd>
    <dl>
      <dt>Red</dt>   <dd><div class="red"></div></dd>
      <dt>Green</dt> <dd><div class="green"></div></dd>
      <dt>Blue</dt>  <dd><div class="blue"></div></dd>
    </dl>
  </dd>
</dl>
```

## Navigation menus

Unordered lists are frequently used to construct vertical and horizontal navigation menus.

```html
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">Projects</a></li>
    <li><a href="#">Team</a></li>
    <li><a href="#">Help</a></li>
  </ul>
</nav>
```

```css
nav ul {
 background-color: powderblue;
 list-style-type: none;
 padding-left: 0;
 width: 200px;
}

nav li {
 color: blue;
 font-size: 1.25rem;
}

nav a {
 box-sizing: border-box;
 color: blue;
 display: inline-block;
 line-height: 2.5;
 padding: 0 10px;
 text-decoration: none;
 width: 100%;
}

nav a:hover,
nav a:focus {
 background-color: blue;
 color: white;
}
```

This CSS removes the list bullets with the `list-style-type` property and uses the `:hover` and `:focus` pseudo-classes to draw a highlight bar on the menu when the users mouse hovers over the appropriate item.

To convert the navigation list from vertical to horizontal, the following changes are required:

- Set the width of the menu `<ul>`
- Set the font of the list (`<ul>`) to `0` then restore it for the list items (`<li>`)
- Set the list items to `inline-block`
- Set the width of the list items to a value that will distribute the values the way you want them - this is usually a percentage width
- Center the list items horizontally

```css
nav ul {
  font-size: 0;
  width: 100%;
}

nav li {
  display: inline-block;
  font-size: 1.25rem;
  text-align: center;
  width: 25%;
}
```