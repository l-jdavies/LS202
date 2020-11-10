# Practice problems: semantics

1. Which of these tags are semantic, and which are not?

[Untitled](https://www.notion.so/93eedeca155b4fdaa6b14f9ea79e8331)

There are all semantic except for `<div>` and `<span>` as those tags are only for styling purposes.

2. Given the following HTML, would `<section>`, `<aside>`, `<article>`, or `<div>` be the most appropriate element for the tag shown as `<sometag>`?

```html
<sometag>
  <h1>Lincoln's Gettysburg Address</h1>
  <p>
    Four score and seven years ago our fathers brought forth on this
    continent, a new nation, conceived in Liberty, and dedicated to the
    proposition that all men are created equal.
  </p>
  <p>
    Now we are engaged in a great civil war, testing whether that nation,
    or any nation so conceived and so dedicated, can long endure. We are
    met on a great battle-field of that war. We have come to dedicate a
    portion of that field, as a final resting place for those who here gave
    their lives that that nation might live. It is altogether fitting and
    proper that we should do this.
  </p>
  <p>
    But, in a larger sense, we can not dedicate—we can not consecrate—we
    can not hallow—this ground. The brave men, living and dead, who
    struggled here, have consecrated it, far above our poor power to add or
    detract. The world will little note, nor long remember what we say
    here, but it can never forget what they did here. It is for us the
    living, rather, to be dedicated here to the unfinished work which they
    who fought here have thus far so nobly advanced. It is rather for us
    to be here dedicated to the great task remaining before us—that from
    these honored dead we take increased devotion to that cause for which
    they gave the last full measure of devotion—that we here highly
    resolve that these dead shall not have died in vain—that this nation,
    under God, shall have a new birth of freedom—and that government of
    the people, by the people, for the people, shall not perish from the
    earth.
  </p>
</sometag>
```

`<article>` would be appropriate because this content is self-contained.

3. Given the HTML from question 2, would it be appropriate to replace `<sometag>` with `<address>` or `<blockquote>`? If so, which one?

`<blockquote>` because the article is a quote from a speech. It would be better to use the `<blockquote>` tag within the `<article>` tag, rather than replace it.

4. Given the following HTML, would `<section>`, `<aside>`, `<article>`, or `<div>` be the most appropriate element for the tag shown as `<sometag>`?

```html
<sometag>
  <h3>Text-align Property</h3>
  <p>
    Given the width of the paragraph, the heading looks odd hanging out on
    the left side of the screen. Let's center it instead; we'll do this
    with the text-align property:
  <p>

  <pre>
    <h1 style="color: orange; text-align: center;">Hello, Internet!</h1>
  </pre>
</sometag>
```

`<section>` because it has it's own heading but isn't self-contained.

5. Given the following HTML, would `<aside>`, `<section>`, `<blockquote>`, or `<div>` be the most appropriate element for the tag shown as `<sometag>`?

```html
<h3>Hex Colors</h3>

<p>
  Most graphics and design applications like Photoshop and Pixelmator
  display colors in hexadecimal format, so it's easy to copy and paste
  color values you need from one program into your editor as a CSS
  property.
</p>

<sometag>
  <p>
    If you're unfamiliar with the hexadecimal numbering system, it uses 16
    different digits instead of the ten the decimal system uses. The hex
    digits are 0 through 9, as in the decimal system, but also include a
    through f (or A through F) as valid digits.
  </p>
</sometag>
```

`<aside>` because it's information that supplements the rest of the content.