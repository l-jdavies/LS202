# Tutorial 3: getting to know CSS

Ref: [https://learn.shayhowe.com/html-css/getting-to-know-css/](https://learn.shayhowe.com/html-css/getting-to-know-css/)

## The cascade

Within a CSS style sheet, the styles cascade from the top to the bottom, which allows different styles to be added or overwritten as the style sheet progresses.

For example:

```css
p {
  background: orange;
  font-size: 24px;
}
p {
  background: green;
}
```

Because the paragraph selector that sets the background color to `green` comes after the paragraph selector that sets the background color to `orange`, it will take precedence in the cascade. All of the paragraphs will appear with a green background. The font size will remain `24` pixels because the second paragraph selector didn’t identify a new font size.

### Cascading properties

The cascade also works with properties inside individual selectors:

```css
p {
  background: orange;
  background: green;
}
```

Because the `green` background color declaration comes after the `orange` background color declaration, it will overrule the `orange` background, and, as before, our paragraphs will appear with a `green` background.

There are times when the cascade doesn't function as it might be expected. This occurs when different types of selectors are used and the specificity of those selectors breaks the cascade.

## Calculating specificity

Each selector in CSS has a specificity weight. This weight, along with its placement in the cascade determines how the styles of that selector will be rendered. The **type** selector has the lowest specificity weight and holds a point value of `0-0-1`. The **class** selector has a medium specificity weight and holds a point value of `0-1-0`. Lastly, the **ID** selector has a high specificity weight and holds a point value of `1-0-0`. Specificity points are calculated in three columns: the first column counts type selectors, the second counts class selectors and the third counts ID selectors.

The higher the specificity weight of a selector, the more superiority the selector is given when styling conflicts occur. For example, if a paragraph element is selected using a type selector in one place and an ID selector in another, the ID selector will take precedence over the type selector regardless of where the ID selector appears in the cascade.

```html
<p id="food">...</p>
```

## Combining selectors

Combining selectors enables us to be more specific about which element, or group of elements we want to select. 

For example, say we want to select all paragraph elements that reside within an element with a class attribute value of `hotdog` and set their background color to `brown`. However, if one of those paragraphs happens to have the class attribute value of `mustard`, we want to set its background color to `yellow`. Our HTML and CSS may look like the following:

```html
<!-- HTML -->
<div class="hotdog">
  <p>...</p>
  <p>...</p>
  <p class="mustard">...</p>
</div>
```

```css
/* CSS */

.hotdog p {
  background: brown;
}
.hotdog p.mustard {
  background: yellow;
}
```

Combined selectors are read from left to right with the selector furthest to the right, known as the *key selector*. The key selector identifies which element the styles will be applied to. Selectors to the left of the key selector are prequalifiers. 

Different types of selectors can be combined to target any given element on a page.

### Spaces within selectors

Within the previous combined selector, `.hotdog p.mustard`, there is a space between the `hotdog` class selector and the paragraph type selector but not between the paragraph type selector and the `mustard` class selector. The use, and omission, of spaces makes a large difference in selectors.

Since there isn’t a space between the paragraph type selector and the `mustard` class selector that means the selector will only select paragraph elements with the class of `mustard`. If the paragraph type selector was removed, and the `mustard` class selector had spaces on both sides of it, it would select any element with the class of `mustard`, not just paragraphs.

The best practice is to not prefix a class selector with a type selector. Generally we want to select any element with a given class, not just one type of element. And following this best practice, our new combined selector would be better as `.hotdog .mustard`.

### Specificity within combined selectors

When selectors are combined, so are the specificity weights of the individual selectors. The combined specificity weights can be calculated by counting each different type of selector within a combined selector.

Looking at our combined selectors from before, the first selector, `.hotdog p`, had both a class selector and a type selector. Knowing that the point value of a class selector is `0-1-0` and the point value of a type selector is `0-0-1`, the total combined point value would be `0-1-1`, found by adding up each kind of selector.

The second selector, `.hotdog p.mustard`, had two class selectors and one type selector. Combined, the selector has a specificity point value of `0-2-1`. The `0` in the first column is for zero ID selectors, the `2` in the second column is for two class selectors, and the `1` in the last column is for one type selector.

Comparing the two selectors, the second selector, with its two classes, has a noticeably higher specificity weight and point value. As such it will take precedence within the cascade. If we were to flip the order of these selectors within our style sheet, placing the higher-weighted selector above the lower-weighted selector as shown here, the appearance of their styles would not be affected due to each selector’s specificity weight.

## Layering styles with multiple classes

Using multiple classes can help layer on different styles without increasing the specificity weight of selectors.

Elements within HTML can have more than one class attribute, as long as each value is separated. Styles that are going to be frequently used can be associated with one class and other classes used to layer on additional styles.

For example, if we want all buttons to have a font size of `16` pixels but we want the background of the buttons to vary, we can create multiple classes and layer them on an element to apply the required style.

```html
<a class="btn btn-danger">...</a>
<a class="btn btn-success">...</a>
```

```css
.btn {
  font-size: 16px;
}
.btn-danger {
  background: red;
}
.btn-success {
  background: green;
}
```

Both anchor elements have the class `btn` then each button has a different second class assigned, which will result in different coloured buttons.

Using multiple classes keeps code easy to understand and selector specificity weights low.

## Common CSS property values

## Colours

All colour values in CSS are defined on an sRGB (standard red, green, blue) colour space. By mixing different levels of red, green and blue millions of colours can be created. There are four primary ways to represent sRGB colours within CSS: keywords, hexadecimal notation, RGB values and HSL values.

### Keyword colours

Complete list of keyword names: [https://www.w3.org/TR/css-color-3/](https://www.w3.org/TR/css-color-3/)

Keyword colour values are simple but they provide limited options and therefore, are not the most popular colour value choice.

```css
.task {
  background: maroon;
}
.count {
  background: yellow;
}
```

### Hexadecimal colours

Hexadecimal colours consist of a `#` followed by a three or six character figure, which uses the numbers `0` to `9` and the letters `a` to `f`, upper or lower case.

In a six character notation, the first two characters represent the red channel, the third and fourth characters represent the green channel and the last two characters represent the blue channel.

In a three character notation the first character represents the red channel, the second character represents the green channel and the last character represents the blue channel.

If in six-character notation the first two characters are a matching pair, the third and fourth characters are a matching pair, and the last two characters are a matching pair, the six-character figure may be shortened to a three-character figure. To do this the repeated character from each pair should be used once. For example, a shade of orange represented by the hexadecimal color `#ff6600` could also be written as `#f60`.

The character pairs are obtained by converting `0` through `255 `into a base-16, or hexadecimal, format. The math is a little tricky—and worthy of its own book—but it helps to know that `0` equals black and `f` equals white.

Hexadecimal color values have been around for a while, and they have become fairly popular because they offer a large number of color options. They are, however, a little difficult to work with, especially if you’re not too familiar with them. Fortunately Adobe has created [Adobe Kuler](https://kuler.adobe.com/), a free application that provides a color wheel to help us find any color we want and its corresponding hexadecimal value.

Additionally, most image editing applications, such as Adobe Photoshop, provide the capability to locate hexadecimal color values.

### RGB and RGBa

RGB colour values are stated using the `rgb()` function. The function accepts three comma separated values, each of which is an integer from 0 to 255. A value of 0 is pure black and a value of 255 is pure white.

RGB color values may also include an alpha, or transparency, channel by using the `rgba()` function. The `rgba()` function requires a fourth value, which must be a number between `0` and `1`, including decimals. A value of `0` creates a fully transparent color, meaning it would be invisible, and a value of `1` creates a fully opaque color. Any decimal value in between `0` and `1` would create a semi-transparent color.

If we wanted our shade of orange to appear 50% opaque, we would use an RGBa color value of `rgba(255, 102, 0, .5)`. RGB color values are becoming more popular, especially due to the ability to create semi-transparent colors using RGBa.

### HSL and HSLa colours

HSL color values are stated using the `hsl()` function, which stands for hue, saturation, and lightness. Within the parentheses, the function accepts three comma-separated values, much like `rgb()`.

The first value, the hue, is a unitless number from `0` to `360`. The numbers `0` through `360` represent the color wheel, and the value identifies the degree of a color on the color wheel.

The second and third values, the saturation and lightness, are percentage values from `0` to `100%`. The saturation value identifies how saturated with color the hue is, with `0` being grayscale and `100%` being fully saturated. The lightness identifies how dark or light the hue value is, with `0` being completely black and `100%` being completely white.

Returning to our shade of orange, as an HSL color value it would be written as `hsl(24, 100%, 50%)`.

HSL color values, like RGBa, may also include an alpha, or transparency, channel with the use of the `hsla()` function. The behavior of the alpha channel is just like that of the `rgba()` function. A fourth value between `0` and `1`, including decimals, must be added to the function to identify the degree of opacity.

Our shade of orange as an HSLa color set to 50% opaque would be represented as `hsla(24, 100%, 50%, .5)`.

The HSL color value is the newest color value available within CSS. Due to its age and support within browsers, though, it isn’t as widely used as the other values.

## Lengths

Similar to colours, there are multiple different values for length, which are used for different purposes. Length units can be absolute or relative, each of which uses a different unit of measurement.

### Absolute lengths

Absolute length values are the simplest length values, as they are fixed to a physical measurement, such as inches, centimeters, or millimeters. The most popular absolute unit of measurement is known as the pixel and is represented by the `px` unit notation.

### Pixels

One pixel = 1/96th of an inch i.e. 96 pixels in an inch. The exact measurement of a pixel, however, may vary slightly between high-density and low-density viewing devices. With the changing landscape of viewing devices and their varying screen sizes, pixels have lost some of their popularity. As an absolute unit of measurement, they don’t provide too much flexibility. Pixels are, however, trustworthy and great for getting started.

### Relative lengths

Relative length values are not fixed units of measurement, they rely on the length of another measurement.

### Percentages

Percentages are one of the most popular relative values. Percentage lengths are defined in relation to the length of another object. For example, to set the `width` of an element to `50%`, we have to know the width of its parent element, the element it is nested within, and then identify `50%` of the parent element’s width.

### Em

The em unit, represented by the `em` unit notation, has its length calculated based on an element's font size. A single em unit is equivalent to an element's font size. If an element has a font size of `14` pixels and a `width` of `5em` then the width would equal `70` pixels (`14` pixels * `5`).

When a font size is not explicitly stated for an element, the em unit will be relative to the font size of the closest parent element with a stated font size. The em unit is often used for styling text, including font sizes, as well as spacing around text, including margins and paddings.