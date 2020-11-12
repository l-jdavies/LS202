# The Visual Formatting model

## Block elements

Most `block` elements group one or more elements (which themselves might be blocks) into areas of the page. For example, `header` elements group together elements in a page header. Groups of `block` elements are called **containers**. The master container is the `body` - every other element belongs to a container.

The default behaviour is for a `block` element to occupy all of the horizontal space that's available within a container, with nothing displayed to the left or right of the `block`. If a page only contains three `block` elements within the `body` element, then all three elements will displayed one above each other, like a stack of blocks.

`block` elements use the box properties (`width` `height` `padding` `border` `margin`) to determine the size of the element. If you want an element that is 928 pixels wide, 168 pixels high, with 20 pixels of left and right padding, 10 pixels of padding at the top and bottom, a 1-pixel border, and a 28-pixel bottom margin, all those properties will play a part in the overall dimensions of the element. Thus, the overall dimensions will be 970 x 218 pixels.

By default the `width` and `height` exclude the `padding` and `borders` but elements may include them (covered later). `width` and `height` measurements never include the margins. Technically, margins provide spacing between elements - they are not part of the elements.

If a `block` occupies an entire row in a container, the width of the element itself is not altered. The remaining pixels will be left empty.

### Which elements are `block`s by default

List of all `block` elements in the documentation: [https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements#Elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements#Elements)

Most elements are `block` elements by default. Here are some of the most common:

- `section`, `article`, `aside`, `header`, `footer`
- `p`
- `h1` through `h6`
- `blockquote`
- `ul`, `ol`, `dl`
- `figure` and `figcaption`
- `form` and `fieldset`

Any element can be converted to a `block` element using the CSS code `display: block`. It is common to render links (`a`) and images (`img`) as `block` elements.

## Inline elements

Relevant docs: [https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements)

Inline elements give some semantic meaning to content. They are used by the browser to alter the way small sections of text are displayed, for example making text bold. `inline` elements handle the dimension properties (`width` `height` `padding` `border` `margin`) in a different way to `block` elements.

Browsers handle the left and right margins and padding for `inline` elements the same as `block`

elements are handled but other box model properties are handled differently:

- The `width` and `height` properties are **ignored** (except `img` elements). Instead, values computed from the element content are used.
- Top and bottom margins are ignored.
- Borders aren't ignored, but the results can look odd.
- Top and bottom padding properties aren't ignored but this will only be noticed if the page has a background or border.

### Which elements are `inline` by default

List in the docs: [https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements#Elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements#Elements)

Four elements from this `list`, `button`, `input`, `select`, and `textarea` may, in fact, default to `inline-block` instead of `inline`, but this depends on the browser.

The following elements are `inline` by default.

- `span`
- `b`, `i`, `u`, `strong`, `em`
- `a`
- `sub` and `sup`
- `img`

You can convert any element to an `inline` element with the `display: inline` CSS property. The most common reason to do so is to override a prior declaration.

## Inline-block elements

`inline-block` visual display model is a legacy model. It is equivalent to a new model called `inline flow-root`. `inline-block` is still widely used and probably will be for many years.

`inline-block` elements are a mixture of the types above. They act like `block` elements except for one important aspect - if the `width` of an `inline-block` element is less than the width that is available, the element will not occupy the entire row. Instead, they have the same flow as `inline` elements, which means they can be placed side by side with other `inline` or `inline-block` elements.

`inline-block` elements also differ from `inline` elements because the `width` and `height` properties of `inline-block` elements are used. The `padding`, `border` and `margin` properties all work the same as for `block` elements.

`inline-block` and `inline` elements can be vertically aligned, using the `vertical-align` property.

### Which elements are `inline-block` by default

The browser has some choice between using `inline` or `inline-block` as the default `display` property for an element type. Usually all browsers agree on the `display` property but not always. For instance, Chrome and Safari treat `input` and `textarea` elements as `inline-block`, while Firefox treats them as `inline` elements. This inconsistency typically isn't a problem. When it is, you can explicitly set the `display` property:

```css
input, textarea {
  display: inline-block;
}
```

It's a common misbelief that images (`img`) are `inline-block` elements; in fact, they are `inline` elements.

You can convert any element to an `inline-block` element with the `display: inline-block` CSS property. A useful application for this is to arrange the contents of a list horizontally instead of vertically; horizontal navigation bars often use list elements defined as `inline-block`. 

## Nesting elements and the visual display model

Nesting is controlled. For example, a `block` can't be nested inside an `inline` element, which means you can put an `em` element inside a `blockquote` but you can't put a `blockquote` inside an `em` element.

There is one exception to this rule: you can nest `block` and `inline-block` elements inside an `a` tag provided the block does not include interactive elements like `input`, `button`, `select`, `textarea`, or another `a` tag. In practice, you will probably not use this feature.

Even if incorrectly nested elements display in the desired manner, the code will fail W3C validation.

## Other visual display models

There are around 24 visual display models, for example list items default a `list-item` display model and table cells have a `table-cell` display model.