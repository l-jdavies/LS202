# Containing floats

There can be a problem with floats moving outside of their container. This is a typical issue with floats. This happens because the browser removes floats from the normal document flow, which means the container no longer contains the floated items. Therefore, the browser can't determine the container's dimensions, so it can't render the container correctly.

```html
<div id="columns">
  <div id="primary">
    <h1>Main Content</h1>
  </div>

  <div id="secondary">
    <h3>Sidebar Content</h3>
  </div>
</div>
```

```css
#columns {
  background-color: #e0e0e0;
  box-sizing: border-box;
  margin: 0 auto;
  padding: 20px;
  width: 780px;
}

#primary, #secondary {
  background-color: yellow;
}

#primary {
  float: left;
  width: 500px;
}

#secondary {
  float: right;
  width: 200px;
}
```

![Containing%20floats%203bc30ad0dee44b7f9824337dd9143cb8/Untitled.png](Containing%20floats%203bc30ad0dee44b7f9824337dd9143cb8/Untitled.png)

## Overflow

Floated elements and absolute or fixed position elements typically don't affect the dimensions of their parents. Because the browser removes the content from the flow, the rendering engine no longer cares about them. The floated or positioned elements can overwrite other content. To fix the problem, an `overflow` option needs to be added to the floated element's container or it needs to be wrapped in a clearfix.

The easiest way to clear a floated element is `overflow: hidden` or `overflow: auto`. Once this property is applied to the container element, the container will expand to wrap around the floated elements. 

```css
#columns {
  overflow: hidden;
}
```

![Containing%20floats%203bc30ad0dee44b7f9824337dd9143cb8/Untitled%201.png](Containing%20floats%203bc30ad0dee44b7f9824337dd9143cb8/Untitled%201.png)

`overflow` works in most cases but there are two edge cases:

1. `overflow: hidden` can clip any content that exceeds the allocated space for the text if the container has a set height or width.
2. `overflow: auto` can add unwanted scrollbars - this behaviour comes from the browser.

If either of those scenarios occurs, then a clearfix approach can be used instead.

`overflow` works by creating a block formatting context that contains everything inside the element to which it has been applied, and that includes floats.

## Clearfix

An alternative to using `overflow` is adding clearfix to a container. Clearfix is a standard pattern that is used to ensure a container doesn't lose its floated children. It employs an invisible block element as the last child element of the container and the `clear` property.

```css
#columns {
  /* overflow: hidden; */
}

#columns::after { /* This rule is the clearfix */
  clear: both;
  content: "";
  display: block;
}
```

![Containing%20floats%203bc30ad0dee44b7f9824337dd9143cb8/Untitled%202.png](Containing%20floats%203bc30ad0dee44b7f9824337dd9143cb8/Untitled%202.png)

Similar to `overflow`, applying clearfix to a container ensures the parent container wraps around the floated elements. This occurs because the `::after` pseudo-element creates a child element at the end of the selected element. The child is defined as a block element, which means it will render on a line by itself. The `content: ""` property sets the container of the child element to an empty string, which makes the clearfix child invisible. As the container can see the clearfix, it will stretch itself to enclose the clearfix and floated content.

`clear` takes values of `right`, `left`, or `both`. `right` and `left` refer to the type of floated element it will clear, while `both` clears any floated element that it finds. You can use any of these values with clear, but you should use `clear: both` unless you find that you need `clear: left` or `clear: right` for some reason.