# Tutorial 2: getting to know HTML

## What are semantics?

Within HTML semantics is the practice of giving content on the page meaning and structure by using the proper element. Semantic code describes the value of content on a page, regardless of the style or appearance of that content. The benefits of using semantic elements include the fact they enable different devices, screen readers and search engines to read and understand the content of a webpage. Semantic HTML is easier to work with because it shows the purpose of each piece of content.

Two elements, `<div>` and `<span>` don't hold any semantic value - they exist for styling purposes only.

## Divisions and spans

Divisions, or `<div>`s, and `<span>`s are HTML elements that act as containers solely for styling purposes. As generic containers, they do not come with any overarching meaning or semantic value. Paragraphs are semantic in that content wrapped within a `<p>` element is known and understood as a paragraph. `<div>`s and `<span>`s do not hold any such meaning and are simply containers.

`<div>` and `<span>` are useful because they give the ability to apply targeted styles to a contained set of content. `<div>` is a block element commonly used to identify large grouping on content, which helps build a web page's layout and design. `<span>` is an inline element commonly used to identify smaller groupings of text within a block-level element. 

It's common to have `<div>` and `<span>` elements with `class` or `id` attributes for styling purposes. The value of attributes should refer to the content of the element, rather than the appearance.

## Comments within HTML and CSS

HTML comments:

```html
<!-- comment -->
```

CSS comments:

```css
/* comment */
```

## Using text-based elements

### Headings

Headings are block-level elements, and they come in six different rankings, `<h1>` through `<h6>`. Headings help to quickly break up content and establish hierarchy, and they are key identifiers for users reading a page. They also help search engines to index and determine the content on a page.

Headings should be used in an order that is relevant to the content of a page. The primary heading of a page or section should be marked up with an `<h1>` element, and subsequent headings should use `<h2>`, `<h3>`, `<h4>`, `<h5>`, and `<h6>` elements as necessary.

Each heading level should be used where it is semantically valued, and should not be used to make text bold or big—there are other, better ways to do that.

### Paragraphs

Paragraphs are defined using the `<p>` block-level element. Paragraphs can appear one after the other, adding information to a page as desired.

### **Bold text**

There are two ways of making text bold: `<strong>` and `<b>` . There are important semantic differences between the two. `<strong>` element is semantically used to give strong importance to text, whereas `<b>` means to stylistically offset text. Therefore, the choice depends on the importance of the words. For example:

```css
<!-- strong importance -->
<p><strong>Warning!</strong> Hazard ahead.</p>

<!-- stylistic offset -->
<p>Don't forget this <b>word</b>.</p>
```

### Italicise text

There are two ways of italicising text: `<em>` or `<i>`. Again, there are semantic differences between the two options. `<em>` is used semantically to place a stressed emphasis on text (most commonly used option). The `<i>` element is used to semantically convey text in an alternative voice or tone, similar to using quotation marks.

## Building structure

Prior to HTML5 the structure of a webpage was built using `<div>` elements. Because these elements don't provide semantic value, it was difficult to determine the intentions of these divisions. Now, there are structure based  elements, including the `<header>`, `<nav>`, `<article>`, `<section>`, `<aside>`, and `<footer>` elements.

These new elements give meaning to the organisational structure of webpages and improve structural semantics. They are all block-level elements with no implied position or style. All of the elements can be used several times per page, as long as each use reflects the proper semantic meaning.

![Tutorial%202%20getting%20to%20know%20HTML%20e36e6150cb0b4d8d93929da1e572cec8/Untitled.png](Tutorial%202%20getting%20to%20know%20HTML%20e36e6150cb0b4d8d93929da1e572cec8/Untitled.png)

### Headers

The `<header>` element identifies the top of a page, article, section or other segment of a page. In general the `<header>` element includes a heading, introductory text and navigation.

The `<header>` element shouldn't be confused with heading `<h1>` elements, or head `<head>`, as they have different semantic meanings. 

The `<header>` element is a structural element that outlines the heading of a segment of a page. It falls within the `<body>` element.

The `<head>` element is not displayed on a page and is used to outline metadata, including the document title, and links to external files. It falls directly within the `<html>` element.

Heading elements, `<h1>` through `<h6>`, are used to designate multiple levels of text headings throughout a page.

### Navigation

The `<nav>` element identifies a section of major navigational links on a webpage. This element should only be used for primary navigation sections, such as global navigation, table of contents, previous/ next links or other important groups of navigational links.

Usually, links within the `<nav>` element will link to other pages within the same website or parts of the same webpage. One-off links should not be wrapped within the `<nav>` element, they should use the anchor element `<a>`.

### Article

The `<article>` element identifies a section of independent, self-contained content. 

### Section

The `<section>` element is used to identify a thematic grouping of content, which generally, but not always, includes a heading. The grouping of content within the `<section>` element may be generic in nature, but it’s useful to identify all of the content as related.

The `<section>` element is commonly used to break up and provide hierarchy to a page.

### Choosing `<article>`, `<section>` or `<div>`

Both the `<article>` and `<section>` elements contribute to a document’s structure and help to outline a document. If the content is being grouped solely for styling purposes and doesn’t provide value to the outline of a document, use the `<div>` element.

If the content adds to the document outline and it can be independently redistributed or syndicated, use the `<article>` element.

If the content adds to the document outline and represents a thematic group of content, use the `<section>` element.

### Aside

The `<aside>` element holds content such as sidebars, inserts or brief explanations that is an 'aside' to the content surrounding the element. It can be used within an `<article>` element. Although the `<aside>` element can be thought of as an element that appears to the side of a page, all structural elements - including `<aside>` are block-level elements. This means they will appear on a new line and occupy the full available width of a page or their parent element.

### Footer

The `<footer>` element identifies the end of a page, section, article or other segment. It is found at the bottom of its parent. Content within the `<footer>` element should be relative information.