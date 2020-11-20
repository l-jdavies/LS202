# Input types

## Type `text`

The type `text` creates a text entry field. The application should validate all input. The `maxlength` attribute can be used to specify the input's maximum length.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      First Name
      <input type="text" name="first_name" value="Tom" />
    </label>
  </fieldset>
</form>
```

## Type `password`

Creates a single-line text field in which the input is obscured. Also has a `maxlength` attribute.

```html
<form action="#" method="post">
  <fieldset>
    <label for="password">Password</label>
    <input type="password" name="password" id="password"
           value="" size="35" />
  </fieldset>
</form> 
```

![Input%20types%20fec42b860bc043c4aebc36af4a239d6b/Untitled.png](Input%20types%20fec42b860bc043c4aebc36af4a239d6b/Untitled.png)

## Type `email`

Renders a text box that accepts an email address in the `user@domain` format. This prevents incorrectly formatted email addresses being entered but the back-end of the application should still validate the address.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Email
      <input type="email" name="email" placeholder="username@domain" />
    </label>
  </fieldset>
</form>
```

![Input%20types%20fec42b860bc043c4aebc36af4a239d6b/Untitled%201.png](Input%20types%20fec42b860bc043c4aebc36af4a239d6b/Untitled%201.png)

## Type `tel`

Allows entry of a phone number. Isn't validated by the browser because there's so much variation in phone number formats.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Phone
      <input type="tel" name="phone" placeholder="(###) ###-####" />
    </label>
  </fieldset>
</form>
```

![Input%20types%20fec42b860bc043c4aebc36af4a239d6b/Untitled%202.png](Input%20types%20fec42b860bc043c4aebc36af4a239d6b/Untitled%202.png)

## Type `checkbox`

The `value` attribute is used to determine the value assigned to the data that is sent to the server when a box is checked. The `checked` attribute pre-selects checkboxes. The `name` attribute assigns a name to a group of related checkboxes. A user can select zero or more items in a set of checkboxes.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      <input type="checkbox" name="choice" value="search" />
      Sort search results
    </label>

    <label>
      <input type="checkbox" name="choice" value="google" checked />
      Search on Google
    </label>

    <label>
      <input type="checkbox" name="choice" value="recent" checked />
      Recent results (within last year)
    </label>
  </fieldset>
</form>
```

![Input%20types%20fec42b860bc043c4aebc36af4a239d6b/Untitled%203.png](Input%20types%20fec42b860bc043c4aebc36af4a239d6b/Untitled%203.png)

`checked` attribute is a boolean that marks a checkbox as selected when supplied in the `input` tag. The browser will send a `name=value` pair for each of the selected checkboxes and no value for the unchecked ones. In the example above `choice=google` and `choice=recent` will be sent to the server.

The `name` attribute can also be used without a `value` attribute:

```html
<form action="#" method="post">
  <fieldset>
    <label>
      <input type="checkbox" name="search" />
      Sort search results
    </label>

    <label>
      <input type="checkbox" name="google" checked />
      Search on Google
    </label>

    <label>
      <input type="checkbox" name="recent" checked />
      Recent results (within last year)
    </label>
  </fieldset>
</form>
```

In this example, the browser will send `google=on` and `recent=on` to the server. It's usually easiest to use separate `name` values.

Checked elements can be selected in CSS by using the `:checked` pseudo-class, which  can be used to change the appearance of checked radio buttons and checkboxes.

## Type `radio`

Lets a user select zero or one item from a list of options. The `value` attribute can be used to define the value submitted when an item is selected. The `checked` attribute can be used to mark a default radio button. If a default button isn't used then the `required` attribute can be used on all buttons in a group to enforce the selection of a button. The `name` attribute can be used to name a set of related radio buttons. A user can only select one radio button from each group.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      <input type="radio" name="color" value="red" />
      Red
    </label>

    <label>
      <input type="radio" name="color" value="green" checked />
      Green
    </label>

    <label>
      <input type="radio" name="color" value="blue" />
      Blue
    </label>
  </fieldset>
</form> 
```

![Input%20types%20fec42b860bc043c4aebc36af4a239d6b/Untitled%204.png](Input%20types%20fec42b860bc043c4aebc36af4a239d6b/Untitled%204.png)

The boolean `checked` works the same as for checkboxes.

Radio buttons are usually used for short lists (5-8 items) otherwise they can become unwieldy. The `select` list control can be used for longer lists.

## Type `submit`

Creates a button that the user can click to submit contents of a form to the server. The `action` attribute on the `form` tag usually provides the URL of the server but that can be overridden by using the `formaction` attribute with the `submit` tag.

```html
<form action="#" method="post">
  <fieldset>
    <input type="submit" value="Save" />
  </fieldset>
</form>
```

![Input%20types%20fec42b860bc043c4aebc36af4a239d6b/Untitled%205.png](Input%20types%20fec42b860bc043c4aebc36af4a239d6b/Untitled%205.png)

## Type `reset`

Creates a button that the user can click to reset the contents of a form to its default values. Clicking a `reset` button does not send a request to the server.

```html
<form action="#" method="post">
  <fieldset>
    <input type="reset" value="Clear Form" />
  </fieldset>
</form>
```