# Classes, IDs and names

There are three ways to identify certain elements in HTML: classes, ids and names. Any element can use a `class` or `id` attribute. A variety of elements can use the `name` attribute and some elements can use all three at once.

## Classes

A `class` attribute identifies a set of page elements that will be styled consistently. Any number of elements can belong to the same class and any element can belong to more than one class. If an element belongs to multiple classes then the attribute names are all listed in a single `class` attribute, separated by spaces.

```html
<p class="molecular_biologist parasites">..</p>
```

Classes should have semantic names i.e. the names should describe the content rather than describe the styling. In CSS elements are selected by class using CSS class selectors (`.parasites`). Class selectors have lower CSS specificity than ID selectors but are higher than tag name selectors. In the example above the class selector `.molecular_biologist` would override the `p` selector.

## IDs

The `id` attribute should only be applied to important elements. You can't have multiple elements with the same `id` attribute value. One element can have multiple `id` attributes. `id` attributes should be given semantic names and are selected using CSS ID selectors (`#headline`). ID selectors have CSS higher specificity than class selectors.

```html
<h1 id="headline">Headline of page</h1>
```

```css
#headline {
  color: red;
  font-size: 20px;
}
```

## Names

The `name` attribute ties form elements to data on the server - it doesn't play a role in styling. For example, when a browser submits form data to the server the name/value pairs used come from the `name` attribute.

```html
<form method="get" action="#">
  <label for="first-name-field">First name:</label>
  <input type="text" name="first-name" id="first-name-field" />

  <label for="last-name-field">Last name:</label>
  <input type="text" name="last-name" id="last-name-field" />

  <input type="submit" value="Search" />
</form>
```

When the form is submitted, the browser will create the following query string:

```html
first-name=Joe&last-name=Jones
```

Because the `id` attribute value isn't sent to the server, it's accepted practice to use both a `name` and `id` attribute on form elements and use the same value for both:

```html
<form method="get" action="#">
  <label for="first-name">First name:</label>
  <input type="text" name="first-name" id="first-name" />

  <label for="last-name">Last name:</label>
  <input type="text" name="last-name" id="last-name" />

  <input type="submit" value="Search" />
</form> 
```

The `name` attribute is used to assign a name to a data element in a form and the server uses this attribute to obtain the value. Not all tags will accept the `name` attribute. Some other elements have a `name` attribute but it has a different meaning.

On form elements that accept a `name` attribute, a `name` attribute should always be used. Each name in a form should be unique to that form, except for radio buttons and checkboxes that belong to a single group. `name` values should be descriptive i.e. `first_name`. The `name` attribute shouldn't be used for CSS styling.