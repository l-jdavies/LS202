# Floats

A better way than using `inline` or `inline-block` elements to place elements side-by-side is to use floats. The benefit of floats is that whitespace between elements doesn't need to be escaped.

A floated element will move as far as possible to the left or right but leave remaining space for additional content. Elements float in their immediate container, which limits how far a browser can move a floated element. If two elements in a row are floated in the same direction, their vertical edges (including margins) will touch, providing they fit on the same row. Any whitespace, apart from margins and padding, that would otherwise appear between the elements will collapse.

```html
<div class="outer">
  <div class="primary">
    <p>Main Content</p>
  </div>

  <div class="secondary">
    <p>Sidebar 1</p>
  </div>
</div>
```

```css
html {
  font-size: 16px;
}

* {
  margin: 0;
  padding: 0;
}

body {
  padding: 0.5rem;
}

p {
  color: black;
  font-family: serif;
  font-size: 1.5rem;
  font-weight: bold;
}

.outer {
  border: 1px solid gray;
  overflow: hidden;
  width: 100%;
}

.primary, .secondary {
  border: 1px solid black;
  box-sizing: border-box;
  text-align: center;
}

.primary {
  background-color: moccasin;
  float: left;
  height: 100px;
  line-height: 100px;
  width: 65%;
}

.secondary {
  background-color: coral;
  float: left;
  height: 75px;
  line-height: 75px;
  width: 30%;
}
```

![Floats%204fc14cfbbd344c3497638daecd2ccd8b/Untitled.png](Floats%204fc14cfbbd344c3497638daecd2ccd8b/Untitled.png)

To add space between the two boxes, instead of adding margins we can float the `.secondary` class elements to the right.

```css
.secondary {
  float: right;
}
```

![Floats%204fc14cfbbd344c3497638daecd2ccd8b/Untitled%201.png](Floats%204fc14cfbbd344c3497638daecd2ccd8b/Untitled%201.png)

The elements can even be swapped over, just by changing the CSS rather than editing multiple HTML files.

```css
.primary {
  float: right;
}

.secondary {
  float: left;
}
```

![Floats%204fc14cfbbd344c3497638daecd2ccd8b/Untitled%202.png](Floats%204fc14cfbbd344c3497638daecd2ccd8b/Untitled%202.png)