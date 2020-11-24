# Positioning

## Offset properties

Offset properties work in conjunction with `position` to determine what direction an element should be moved in and how far, Each offset measures the **inward** distance from the side of the container named by the offset property. For example, `bottom: 50px` moves an element 50px inward (up) from the bottom of the container. This is important to remember. Negative offsets shift elements in the opposite direction (move the element outward).

## The `position` property

This property tells the browser how to position selected elements. 

### `position: static`

This is the default position. While floated, grid, flex and elements with absolute or fixed positioning are removed from the page flow, statically positioned elements are part of the page flow. They appear in the same order as they appear in the markup. Offset properties do not affect static elements.

### `position: relative`

Moves an element to a new position relative to where the browser would put it, if it was static. For example `left: 50px` and `bottom: 100px` with `position: relative` would cause the browser to move the element 50px inwards from the left edge and 100px up from the bottom edge, relative to where the browser would otherwise place it.

When using relative positioning, it is standard to provide a maximum of one vertical offset and one horizontal offset, although CSS does allow for both vertical or both horizontal offsets to be used at the same time. If both are used, the following rules apply:

- `left` overrides `right` for left-to-right languages.
- `right` overrides `left` for right-to-left languages.
- `top` overrides `bottom` at all times.

Relative positioning does not remove an element from the document flow. The browser positions the next element as though the previous one was occupying its pre-offset position.

```html
<section>
  <aside class="normal">normal</aside>
  <aside class="shifted pos">top</aside>
  <aside class="shifted neg">-top</aside>
  <aside class="normal">normal</aside>
</section>
```

```css
section {
  border: 1px solid gray;
  padding: 70px 10px;
}

aside {
  border: 1px solid black;
  display: inline-block;
  height: 100px;
  line-height: 100px;
  margin: 0;
  padding: 0;
  text-align: center;
  width: 100px;
}

.normal {
  background-color: yellow;
}

.shifted {
  position: relative;
}

.pos {
  background-color: cyan;
  top: 60px;
}

.neg {
  background-color: lightgreen;
  top: -60px;
}
```

![Positioning%20bafd299f49cb45d9bd239dfea6bb319f/Untitled.png](Positioning%20bafd299f49cb45d9bd239dfea6bb319f/Untitled.png)

```html
<section>
  <aside class="normal">normal</aside>
  <aside class="shifted pos">bottom</aside>
  <aside class="shifted neg">-bottom</aside>
  <aside class="normal">normal</aside>
</section>
```

```css
.pos {
  /* top: 60px; */.
  bottom: 60px;
}

.neg {
  /* top: -60px; */.
  bottom: -60px;
}
```

![Positioning%20bafd299f49cb45d9bd239dfea6bb319f/Untitled%201.png](Positioning%20bafd299f49cb45d9bd239dfea6bb319f/Untitled%201.png)

Right positioning example:

```html
<section>
  <aside class="normal">normal</aside>
  <aside class="shifted pos">right</aside>
  <aside class="shifted neg">-right</aside>
  <aside class="normal">normal</aside>
</section>
```

```css
section {
  padding: 10px;
}

.pos {
  /* bottom: 60px; */.
  right: 60px;
}

.neg {
  /* bottom: -60px; */.
  right: -60px;
}
```

![Positioning%20bafd299f49cb45d9bd239dfea6bb319f/Untitled%202.png](Positioning%20bafd299f49cb45d9bd239dfea6bb319f/Untitled%202.png)

Left positioning example:

```html
<section>
  <aside class="normal">normal</aside>
  <aside class="shifted pos">left</aside>
  <aside class="shifted neg">-left</aside>
  <aside class="normal">normal</aside>
</section>
```

```css
.pos {
  /* right: 50px; */.
  left: 50px;
}

.neg {
  /* right: -50px; */.
  left: -50px;
}
```

![Positioning%20bafd299f49cb45d9bd239dfea6bb319f/Untitled%203.png](Positioning%20bafd299f49cb45d9bd239dfea6bb319f/Untitled%203.png)

### `position: absolute`

Causes the browser to move the element to a new position within a container element. By default, the container is the nearest ancestor element that has a relative, absolute or sticky `position`. If no such ancestor is present, the initial containing block (the `body`) will be used.

```html
<section>
  <aside class="relative">
    <div class="absolute-1"></div>
  </aside>
  <aside class="relative">
    <div class="absolute-2"></div>
  </aside>
  <aside class="relative">
    <div class="absolute-3"></div>
  </aside>
</section>
```

```css
section {
  border: 1px solid gray;
  padding: 10px 10px 60px;
  width: 780px;
}

aside {
  border: 1px solid black;
  display: inline-block;
}

.relative {
  background-color: yellow;
  height: 200px;
  left: 0;
  margin: 0 25px;
  position: relative;
  top: 0;
  width: 200px;
}

.absolute-1 {
  background-color: lightgreen;
  bottom: 33%;
  left: 33%;
  position: absolute;
  right: 33%;
  top: 33%;
}

.absolute-2 {
  background-color: cyan;
  bottom: 150px;
  left: 0;
  position: absolute;
  right: 20px;
  top: 0;
}

.absolute-3 {
  background-color: pink;
  bottom: -50px;
  left: 100px;
  position: absolute;
  right: -40px;
  top: 150px;
}
```

![Positioning%20bafd299f49cb45d9bd239dfea6bb319f/Untitled%204.png](Positioning%20bafd299f49cb45d9bd239dfea6bb319f/Untitled%204.png)

In the above example:

- The yellow boxes are our containers; they use relative positioning. Recall that absolute positioning requires an ancestor element that uses relative, absolute, or sticky positioning; otherwise, it uses the body.
- The green box demonstrates how we can use absolute positioning to center an item within its container: set all four offset properties to the same value. Note: this won't work if the green box has an explicit height or width; see the next assignment for a way to handle that situation.
- The cyan box shows a different example of absolute positioning. The critical point is that we need to specify the offset positions as distances from the four corresponding sides. Thus, the bottom of the cyan box is 150px from the bottom of the yellow container.
- The pink box reveals that you can use negative offsets, which moves part of the pink box outside of its container.

Absolute positioning removes elements from the normal document flow. The browser won't treat the space as occupied and will place other elements in the same position:

```html
<section>
  <aside class="relative">
    <div class="absolute-1"></div>
    <div class="absolute-2"></div>
    <div class="absolute-3"></div>
    <div class="unpositioned"></div>
  </aside>
</section>
```

```css
.unpositioned {
  background-color: black;
  height: 100px;
  width: 100px;
}
```

![Positioning%20bafd299f49cb45d9bd239dfea6bb319f/Untitled%205.png](Positioning%20bafd299f49cb45d9bd239dfea6bb319f/Untitled%205.png)

Three boxes with absolute positioning have been placed inside the container along with a box that has `static` positioning. The black box is positioned as though the other elements weren't present.

### `position: fixed`

Sets an element to a fixed position and the element doesn't move, even if the user scrolls the page. This is commonly used with navigation bars.

```html
<header>
  Fixed Position Demo
</header>

<section>
  <p>
    This part of the window scrolls up and down.
  </p>
  <p>
    Sint cillum tempor esse eu laborum ipsum eu. Cupidatat sint laboris
    excepteur eu enim adipisicing officia. Sunt cupidatat id ipsum reprehenderit
    et irure veniam ex. Duis cupidatat ullamco adipisicing mollit ea nulla irure
    mollit eu. Aliqua laboris aute sint consectetur aute occaecat cillum sint
    aliqua. Culpa eiusmod officia Lorem dolore.
  </p>
  <p>
    Dolor proident mollit eiusmod. Cupidatat Lorem ipsum irure culpa quis. Non
    consequat sunt non nostrud sint id quis consectetur aute. Exercitation nisi
    tempor excepteur. Magna exercitation ad amet ut commodo consequat non. Duis
    veniam culpa esse magna laborum aute sunt quis.
  </p>
  <!-- add several more paragraph here -->
</section>
```

```css
header {
  background-color: lightgreen;
  font-size: 4rem;
  height: 8rem;
  left: 0;
  line-height: 8rem;
  opacity: .75;
  position: fixed;
  text-align: center;
  top: 0;
  width: 100%;
}

section {
  margin: 0 auto;
  padding: 10rem 1rem 0;
  width: 600px;
}

p {
  font-size: 2rem;
  margin-bottom: 1.5rem;
}
```