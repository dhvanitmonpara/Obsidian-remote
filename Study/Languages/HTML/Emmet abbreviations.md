### HTML Abbreviations:

1. **Element Abbreviation**: Type the name of an HTML element to create it.
    
    - Example: `div` creates `<div></div>`.
2. **Element with Class**: Add a class to an element using a period (`.`).
    
    - Example: `div.container` creates `<div class="container"></div>`.
3. **Element with ID**: Add an ID to an element using a hash (`#`).
    
    - Example: `div#header` creates `<div id="header"></div>`.
4. **Nested Elements**: Use `>` to nest elements.
    
    - Example: `ul>li*3` creates:

```html
<ul>
  <li></li>
  <li></li>
  <li></li>
</ul>
```

5. **Siblings**: Use `+` to create sibling elements.

- Example: `div+p+a` creates:

```html
<div></div>
<p></p>
<a></a>
```

6. **Attributes**: Use `[attribute="value"]` to add attributes.
    
    - Example: `a[href="https://example.com"]` creates `<a href="https://example.com"></a>`.


7. **Nested list using Emmet Abbreviation:**

`ul>li*3>ul>li*2`

This abbreviation will generate a nested list structure with an unordered list (`<ul>`) containing three list items (`<li>`), and each list item containing a nested unordered list with two list items. Here's the HTML code it generates:

```html
<ul>
  <li>
    <ul>
      <li></li>
      <li></li>
    </ul>
  </li>
  <li>
    <ul>
      <li></li>
      <li></li>
    </ul>
  </li>
  <li>
    <ul>
      <li></li>
      <li></li>
    </ul>
  </li>
</ul>

```
This creates a hierarchical structure of nested lists, which can be useful for various types of content organization on a webpage. You can adjust the numbers and nesting levels as needed by modifying the numbers and structure within the Emmet abbreviation.

**Note:** `<div>` tag is the default element for emmet abbreviation, so if you type `.classroom` or `#classroom` complier will create `<div>` tag by default.

You can also create multiple classes and IDs at a time for example:

`.classroom.navbar.maindiv` will create multiple class or `#classroom#navbar#maindiv` will create multiple IDs.

8. **Lorem text:**

Lorem text is a **random text** for your web preview.

`lorem 7` means generate 7 random words.
`lorem*7` means generate 7 random paragraphs.

Visit [Emmet abbreviation cheat-sheet](https://docs.emmet.io/cheat-sheet/) for summary.


### CSS Abbreviations:

1. **Class and ID**: Use `.` for classes and `#` for IDs.
    
    - Example: `.container` generates `.container { }`.
2. **Nested Rules**: Nest rules using `>`.
    
    - Examp6le: `ul>li` generates:

```css
ul {
  li {
  }
}
```

1. **Grouping**: Separate multiple rules with a comma.
    
    - Example: `h1, h2, h3` generates `h1, h2, h3 { }`.
2. **Properties and Values**: Type property-value pairs.
    
    - Example: `bgc:red` generates `background-color: red;`.
3. **Shorthand Properties**: Use `margin` or `p` for shorthand properties.
    
    - Example: `m:10px` generates `margin: 10px;`.
4. **Child Selector (`>`)**: Use `>` for child selectors.
    
    - Example: `div>p` generates `div > p { }`.
5. **Adjacent Sibling Selector (`+`)**: Use `+` for adjacent sibling selectors.
    
    - Example: `h1+p` generates `h1 + p { }`.

Emmet abbreviations can save you a lot of time when writing HTML and CSS code. You can customize and expand on these examples to suit your specific needs in web development.