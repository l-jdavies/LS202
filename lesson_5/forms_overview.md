# Forms overview

Forms display information to a user, performs optional rudimentary validation then sends the form data to a server. They don't update information on the server, that is handled by back-end software, which accepts the form data from the browser. Most web applications use JavaScript to pre-validate forms before sending the data to the server.

## The `form` tag

The `form` tag is the parent for all tags related to forms. The information in these tags instruct the browser where and how to send the data. The most important attributes are `action` and `method.`

A form should contain at least one `input`, `textarea` or `select` tag. The terms **control**, **widget** and **input** are used to informally refer to all of these elements collectively.

### The `method` attribute

The `method` attribute is used to state if the form data should be sent to the server using the HTTP GET or HTTP POST method. Although HTTP supports other methods, these are the only ones supported by HTML. JavaScript needs to be used to access the other HTTP methods.

### `action` and `formaction` attributes

`action` provides the URL to which the browser sends requests. Individual action items (`button` and `input type='submit'` elements) can override the form's `action` value by using the `formaction` attribute.

## The `fieldset` tag

`fieldset` is an optional tag that groups together form content as a set of related data. This provides useful semantic data and can be used as a CSS selector. One form can have multiple `fieldset` tags.

```html
<form action="/login" method="post">
  <fieldset>
    <input type="text" name="username" />
    <input type="password" name="password" />
  </fieldset>
  <fieldset>
    <input type="submit" value="Save" />
    <input type="submit" value="Forgot Password" formaction="/forgot" />
  </fieldset>
</form>
```

## The `input` tag

`input` describes a widget, which is a mechanism that enables a user supply information or a request to the application on the server. Each `input` requires a `type` attribute, which has a large number of valid values. Each `type` attribute value indicates the type of widget required. For example, `type="text"` will render a text box that a user can enter text into; `type="submit"` renders a button that submits the form to the server.

Most `input` controls require a `name` attribute, which specifies the name of each item. The browser uses these names to identify each data item in the form and the back-end application uses the names to identify the value associated with an item.

```html
<input type="text" name="city" />
<input type="password" name="password" />
<input type="submit" value="Save" />
```

Note that `input` is a self-closing tag.

## The `label` tag

The `label` tag provides of associating identifying text with an input field. For example, associating the label `Phone` with the field `phone_number`:

```html
<label for="phone">Phone</label>
<input type="text" id="phone" name="phone_number" />
```

The browser uses the `for` attribute in the `label` tag and the `id` attribute in the `input` tag to associate these two items. One benefit is that when a user clicks on the label, the cursor will jump into the associated field.

A `label` tag can be used as a container, which eliminates the need for the `for` and `id` attributes but it can make styling more difficult:

```html
<label>
  Phone
  <input type="text" name="phone" />
</label>
```

## Example of a form

```html
<form action="#" method="post">
  <fieldset>
    <h1>Log In</h1>
    <fieldset>
      <label for="username">Username</label>
      <input type="text" name="username" id="username" />
    </fieldset>

    <fieldset>
      <label for="password">Password</label>
      <input type="password" name="password" id="password" />
    </fieldset>

    <fieldset>
      <input type="submit" value="Log In" />
      <input type="submit" value="Delete account"
             formaction="/account/delete" />
      <input type="submit" value="Forgot password"
             formaction="/account/password" />
      <input type="reset" value="Reset" />
    </fieldset>
  </fieldset>
</form>
```

By default a border will be drawn around the form, that can be disabled:

```css
fieldset {
  border: none;
}
```