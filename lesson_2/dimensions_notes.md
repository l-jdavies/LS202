# Dimensions

## Absolute units

The most important absolute unit in CSS is the pixel (`px`). 

### Physical vs. reference pixels

The problem with using a pixel as an absolute unit of measurement is that pixels on different devices (i.e. desktop vs. phone) are different sizes and the density of pixels on a display can also cause differences. A pixel on a high-res screen is much smaller than a pixel on a low-res screen.

To tackle this, CSS has a **physical pixel** and the **CSS reference pixel** (also called the CSS pixel or the reference pixel). The size of a reference pixel is the size of a pixel on a display that has 96 pixels per inch. A high-res display might have 192 pixels per inch. To account for that CSS will use a total of four physical pixels on the high-res display for every CSS pixel (192 / 96 = 2 and because pixels are 2D, four physical pixels are required per CSS pixel).

This doesn't completely solve the issue though. CSS also defines the reference pixel based on the angular diameter of a CSS pixel as viewed from the **typical viewing distance (TVD)** for the display. The TVD for a phone (around 14 inches) is less than the TVD for a 27-inch desktop display (about 33 inches), so if we place both screens at the appropriate TVD, that 200x200 pixel image appears to be the same size (or close to it, anyway).

### Other absolute units

CSS supports other absolute units, including inches and millimeters, but you won't use these units often. In theory, a CSS inch should appear to be 1 inch on a screen at the TVD since a CSS inch is 96 CSS pixels. If you measure the length of that inch with a ruler, though, it may be larger or smaller than an actual inch. This difference leads most developers to stay away from inches and millimeters unless they need something that appears close to "life-size."

## Relative units

The relative units of interest in CSS are `em` `rem` and `percentages`.

### Ems and rems

Ems and rems are proportional to the calculated and root font sizes, respectively. 

Calculated font size = height of the current font in pixels

Root font size = the font size designated for the `html` element

If the calculated font size is 20 pixels and the root font size is 16 pixels, then `1.5em` is `30px` (20 * 1.5) and `1.5rem` is `24px` (16 * 1.5). In most cases pixels should be used to specify font size.

rems are more consistent than ems. Once the root font size for a document has been set, `1.5rem` means the same thing everywhere in the document. That isn't the case for ems because ems compound. 

![Dimensions%20a34acd3359224c04809a5fc98bfd77a8/Untitled.png](Dimensions%20a34acd3359224c04809a5fc98bfd77a8/Untitled.png)

Looking at the `1rem` and `1em` lines at the bottom, specifying `1rem` returns to the original font size but that isn't the case with `1em`.

This compounding makes ems hard to use and maintain. Some older browsers, though, don't recognize rems; if you must support such browsers, use a **fallback** unit:

```css
p {
  font-size: 20px; font-size: 1.25rem;
}
```

This CSS tells the browser to use `1.25rem` as the font size. If the browser doesn't recognize rems, it falls back to `20px`. Placing both values on the same line makes the presence of a fallback easier to see, but it isn't required.

### Percentages

Technically, CSS doesn't consider percentages as a length value, but this distinction doesn't matter much at this stage. You can use them to define dimensions as a fraction of the container's width or height. If you place a `block` or `inline-block` element in a container and set it to `width: 50%;`, the element's width is 50% of the width of the container. Likewise, if you need a height of one-quarter of the container's height, use `height: 25%`.

Remember: `width` and `height` have no effect on `inline` elements.

### Auto

The `auto` specifier also isn't a length value, but you can use it when you want to let the browser determine a width or height for you. Its specific role depends on where you use it, but it's most common uses are:

- As a `width` or `height`, it tells the browser to try to fit the entire element (including its margins) in its container.
- As a left or right `margin` value on a block element, it tells the browser to push the element all the way right or left (note the reversal!) inside its container. You can center a block element by setting both left and right margins to `auto`. See below.
- As a top or bottom `margin` value, `auto` is equivalent to `0`.
- Padding does not accept `auto` values.

New developers sometimes assume that `auto` and `100%` are the same, but they are not. For example, if you use `width: auto`, the browser tries to put the entire element, including its margins, border, and padding within the container. If you use `width: 100%` instead, the browser won't consider the margins when it calculates the required element size. Thus, the element may extend beyond the bounds of the container. Furthermore, if you use the `content-box` box-sizing model, the browser won't consider the border and padding when determining the required size.

![Dimensions%20a34acd3359224c04809a5fc98bfd77a8/Untitled%201.png](Dimensions%20a34acd3359224c04809a5fc98bfd77a8/Untitled%201.png)

### Zero length

Standard CSS omits the units when providing a length of 0. For example:

```css
blockquote {
  margin: 0;
}
```

### Mixing units

Units can be mixed within CSS code and even within the styling of a single element:

```css
p {
  border: 1rem solid red;
  height: auto;
  margin: 10px;
  padding: 0.5em 10vw 0.5in 18pt;
  width: 80%;
}
```

## Which units should be used?

Some general guidelines (not set in stone):

- Use absolute units sparingly, and stick with pixels. Pixels work well for:
    - the root font size
    - image widths and heights
    - top and bottom margins and padding, sometimes useful with left and right margins and padding
    - width or height of fixed-width/fixed-height containers such as navigation sidebars
    - border widths

- Use relative units liberally:
    - Use rems for fonts, possibly with a fallback to ems or pixels. The root font should use pixels.
    - If you must use ems instead of rems, try to avoid compounding font sizes.
    - Use rems, ems, or pixels for left and right margins and padding.
    - Use `%` for measurements that are proportional to the container element's width or height. Percentages work best for container dimensions and come in handy when you want certain areas of the page to grow and shrink as the width of the browser window changes.
    - Use `auto` with `width` and `height` to let the browser calculate an appropriate value.
    - Use `auto` with left and right margins to left, center, or right justify a block element within its container.

You can ignore or break any of these rules when appropriate.