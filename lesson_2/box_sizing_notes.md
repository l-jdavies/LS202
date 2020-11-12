# Box sizing

There are two different ways of sizing boxes using the `box-sizing` property: `border-box` and `content-box`. 

## `content-box`

The `content-box` setting is default for all elements on all modern browsers. In this model the `width` and `height` properties specify the size of the **actual content area**. The size of the padding and borders is added to the size to determine the final size of the displayed box.

## `border-box`

With the `border-box` property, the browser will interpret the `width` and `height` properties as the **total box size**, excluding the margins. In other words, the `width` and `height` includes the content size, borders and padding.

The benefit of the `border-box` is that it simplifies things for front-end developers. To use `border-box` everywhere, this can be added to CSS:

```css
html {
  box-sizing: border-box;
}

*, *::before, *::after {
  box-sizing: inherit;
}
```

This will ensure all elements inherit the `border-box` property.