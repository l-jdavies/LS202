# Select and textarea

## `textarea` element

Lets a user input multiple lines of text. Differs to the `text` input because white space characters, such as carriage returns and newlines, aren't ignored. In a `textarea` element whitespace characters can be used to format the text into lines and paragraphs. Unlike other controls, `textarea` element doesn't use the `value` attribute to provide a value for the element, instead the text is placed between the opening and closing tags. As whitespaces are preserved, it's common practice to code the opening and closing `textarea` tags on the same line, unless the text content contains newlines.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Comment
      <textarea name="tweet">I got 20% off my first purchase at joesburgers.com! You can too!</textarea>
    </label>
  </fieldset>
</form>
```

![Select%20and%20textarea%20e8a8acb85f554aacbe50a53d7ea6fad4/Untitled.png](Select%20and%20textarea%20e8a8acb85f554aacbe50a53d7ea6fad4/Untitled.png)

### Rows and cols

`textarea` element used the attributes `rows` and `cols` to control the height and width of the text box. `rows` is the height in lines and `cols` is the width in characters. Neither measurement is precise and the browser might display more or fewer lines than stated, plus the attributes values are overridden by the CSS `width` and `height` properties. The `rows` values doesn't state the max number of input lines allowed, rather it's the number of visible lines. The text box will enable scrolling if the number of lines input by the user exceeds the number of visible lines. Most browsers enable the area of the `textarea` box to be increased by dragging a small triangle in the lower-right corner of the text box. This feature can be disabled with the CSS `resize` property.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Comment
      <textarea name="tweet" rows="5" cols="40">I got 20% off my first purchase at joesburgers.com! You can too!</textarea>
    </label>
  </fieldset>
</form>
```

![Select%20and%20textarea%20e8a8acb85f554aacbe50a53d7ea6fad4/Untitled%201.png](Select%20and%20textarea%20e8a8acb85f554aacbe50a53d7ea6fad4/Untitled%201.png)

## The `select` element

`select` creates a drop down list of options from which the user can select zero or more options. It has two possible child elements - `option` and `optgroup`. `select` uses the `name` attribute like other form elements and the `option` element is used to describe the values shown to the user and the values sent to the server (these can be different).

### The `option` element

Defines the choices a user can make in a `select` tag - without at least one `option` element the `select` tag is useless. The `option` element uses the `value` attribute as the value sent as the value of the `select` elements name. If an `option` doesn't have a `value` attribute, the browser sends the text contained by the `option` element instead.

`select` elements often have a placeholder `option` containing something like `choose one` which has a `value` attribute of an empty string in addition to the `disabled` and `selected` attribute. This means the user sees the text but cant select it as an option.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Colors
      <select name="color">
        <option value="" disabled selected>Choose one</option>
        <option value="#f00">Red</option>
        <option value="#0f0">Green</option>
        <option value="#00f">Blue</option>
      </select>
    </label>
  </fieldset>
</form>
```

By default `select` lets the user choose one option or leave the option unselected if it contains a `disabled selected` option. Adding the `multiple` attribute means the user can select more than one option. The `multiple` attribute should be used with `size` attribute to control the height of the selection box.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Choose Your Favorite Movies
      <select name="favorites" multiple size="4">
        <option value="" disabled selected>Select One or More</option>
        <option>2001: A Space Odyssey</option>
        <option>Arrival</option>
        <option>Close Encounters of the Third Kind</option>
        <option>District 9</option>
        <option>Guardians of the Galaxy</option>
        <option>Interstellar</option>
        <option>Serenity</option>
        <option>Silent Running</option>
      </select>
    </label>
  </fieldset>
</form>
```

![Select%20and%20textarea%20e8a8acb85f554aacbe50a53d7ea6fad4/Untitled%202.png](Select%20and%20textarea%20e8a8acb85f554aacbe50a53d7ea6fad4/Untitled%202.png)