# Input attributes

The `input` tag supports a variety of attributes, some of them work with most input types, some only work with one.

## The `value` attribute

Most input controls can use the `value` attribute but the meaning changes depending on the `type`.

### Text

For text-based types (`text` `email` and `number`) the `value` assigns a default value for the control. If a default value isn't provided then the browser uses an empty string.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Phone
      <input type="tel" name="phone" value="503-555-1212" />
    </label>
  </fieldset>
</form>
```

![Input%20attributes%20c3cec03521404972b585ee41c661b5de/Untitled.png](Input%20attributes%20c3cec03521404972b585ee41c661b5de/Untitled.png)

`value` should be used when a value already exists, either loaded from a database or provided during a session.

### Boxes

`checkbox` and `radio` types use the `value` attribute to set the value that the form submits for the selected checkbox or radio group element.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      <input type="radio" name="color" value="red" />
      Red
    </label>
    <br />

    <label>
      <input type="radio" name="color" value="blue" checked />
      Blue
    </label>
    <br />

    <label>
      <input type="radio" name="color" value="green" />
      Green
    </label>
  </fieldset>
</form>
```

Technically, `radio` input types don't require the `value` attribute but that can lead to strange behaviour. It's best to always use a `name` value and use the same `name` on all radio buttons that belong together.  

### Buttons

Button types such as `submit` `reset` and the `button` type use the `value` attribute to specify the contents of the label displayed on the button.

```html
<form action="#" method="post">
  <fieldset>
    <input type="submit" value="Save" />
  </fieldset>
</form>
```

## `size` and `maxlength` attributes

These attributes can be used for most text-based input types.

The `size` attribute controls the size of an `input` element in characters. The width can also be controlled with the CSS `width` property but that doesn't support character measurements. `maxlength` is similar, this value can be more or less than the `size` value.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Phone
      <input type="tel" name="phone" size="10" maxlength="16" />
    </label>
    <br />
    <label>
      Cell Phone
      <input type="tel" name="cell-phone" size="20" maxlength="40" />
    </label>
  </fieldset>
</form>
```

`size` is an approximation for the width of the input box. The HTML5 standard requires that "the user agent should ensure that at least that many characters are visible"; in practice, you may see both more and fewer characters displayed. The CSS `width` overrides the `size` attribute in CSS-enabled browsers.

## The `placeholder` attribute

Lets you display some text in an empty field to demonstrate the expected input. Can be used with most text-based `input` types. Most browsers display the placeholder text in greyed out text, which is erased when a user starts typing.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Phone
      <input type="tel" name="phone" placeholder="###-###-####" />
    </label>
  </fieldset>
</form>
```

Don't use `placeholder` attribute instead of labels because this causes problems for screen readers.

## `disabled` attribute

Enables `input` elements to be disabled, which means the browser will render them but won't let the user interact with them. The rendering looks different for disabled attributes, usually using a grey colour. `disabled` also turns on the `:disabled` CSS pseudo-class while non-disabled elements set the `:enabled` pseudo-class.

Most applications handle the `disabled` attribute programmatically, either when the application generates the HTML or dynamically with JavaScript.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Email
      <input type="email" name="email" value="xyz@example.com" disabled />
    </label>
    <br />
    <input type="submit" value="Save" disabled />
  </fieldset>
</form>
```

## `required` attribute

Marks an `input` as required and won't let a user submit the form until the required fields are completed. Also switches on the `:required` CSS pseudo-class.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Home Phone
      <input type="text" name="home_phone" required />
    </label>
    <br />
    <label>
      Business Phone
      <input type="text" name="business_phone" />
    </label>
    <br />
    <input type="submit" value="Save" />
  </fieldset>
</form>
```

```css
input:required {
  background-color: yellow;
}
```

## `autocomplete` attribute

Can be used with most text-based `input` elements. This attributes prevents a browser from storing data for later re-use by the browsers `autocomplete` features. The attribute can be assigned the values `on` or `off` to explicitly switch autocomplete on or off for any given field. It doesn't affect the `password` input type.

```html
<input type="tel" value="123-456-7890" name="phone" autocomplete="off" /> 
```

## `autocapitalize` attribute

Some browsers recognize an `autocapitalize` attribute to turn `autocapitalization` on and off for the first letter of words or sentences. Browsers that recognize this tag default to `sentences`. Use `autocapitalize="none"` when expecting input that you don't want to capitalize. You can also specify `autocapitalize="words"` or `autocapitalize="characters"`.

```html
<input type="text" name="full-name" autocapitalize="words" />
```

`autocapitalize` is not part of the HTML standard, but an attribute provided by some mobile browsers, such as iOS Safari and Google Chrome. It does not affect desktop and laptop systems. The W3C HTML validator presently complains about `autocapitalize` since it is non-standard. 

## `autocorrect` attribute

Some browsers support an `autocorrect` attribute that turns automatic spelling correction on and off. You can disable this feature with `autocorrect="off"`; you should usually disable it with names, addresses, and other information where autocorrection would be a bother. As with `autocapitalize` this attribute is non-standard and associated with mobile browsers.

```html
<input type="text" name="full-name" autocorrect="off" />
```