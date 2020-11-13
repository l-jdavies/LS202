# Padding and margins

## Difference between padding and margins

The padding lies inside of the border and its typically opaque. The padding is part of the visible and clickable bounds of an element. 

The margin sits outside of the border and is the spacing between adjacent elements. 

If an element is nested in a container and the element and container each have a different coloured background, the element background will be visible in the padding area but the container background will be visible in the margin.

## Margins on inline elements

Remember that the top and bottom margins and padding **are not used** for spacing `inline` elements.

## Margin collapse

When two `block` elements are adjacent to one another the margin between them isn't the sum of the bottom margin of the first element and the top margin of the second element, instead the margin collapses to the larger of the two margins. For example:

```html
<p>This is the first sentence</p>
<p>This is the second sentence</p>
```

```css
p {
  margin-bottom: 15px;
  margin-top: 32px;
}
```

The spacing between the two paragraphs isn't 47px, it's 32px.

Margin collapse only occurs with top and bottom margins - it doesn't occur with left and right margins or padding.

## Use padding or margins?

There is no definitive answer but in general margins should be used for spacing between elements and padding should be used to affect the visible or clickable area of an element. Within a container, padding should be used for horizontal separation between its edges and content whilst margins should be used for vertical distance.

This approach works well but sometimes leaves you wondering about the correct choice. Another technique is to use margins everywhere except when you need padding. You probably need to use padding when:

- You want to change the height or width of a border.
- You want to adjust how much background is visible around an element.
- You want to alter the amount of clickable area.
- You want to avoid margin collapse.
- You want some horizontal spacing to the left or right of an `inline` element.
- As before, use padding to separate the left and right sides of a container from its content. Use margins for the vertical gap.

This approach is a simple mechanical process: ask yourself whether any of the above options apply to the element. If any do, use padding to provide those features. Otherwise, use margins.