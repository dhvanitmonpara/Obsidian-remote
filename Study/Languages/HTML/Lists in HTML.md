**Index of the documentation:**
[[Lists in HTML#^a02513]]
[[Lists in HTML#^47fbc1]]
[[Lists in HTML#^cec419]]
[[Lists in HTML#^84261f]]
# Unordered list

^a02513

- In HTML, **unordered lists** are represented using the `<ul>` element. 
  **Example:**
  ```html
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
  </ul>
  ```

##### Type Attribute

The `type` attribute represents **different types of list item markers** such as `circle`, `square`, and `disc`, with `disc` being the default marker/bullet type.

**Example:**
```html
<ul type="circle">
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

The output of the above code will display with circle bullet points. The attribute value `none` displays the list without any bullet point. You can also add an *image or icon* as a bullet point using CSS with class declaration.

For more information about unordered lists, visit [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul).

# Ordered list

^47fbc1

- In HTML, **ordered lists** are represented using the `<ol>` element. 
  **Example:**
  ```html
  <ol>
    <li>item 1</li>
    <li>item 2</li>
    <li>item 3</li>
  </ol>
  ```

#### Type Attribute

The `type` attribute represents **different types of order** in an ordered list, such as `1 (numeric)`, `a (alphabetical)`, `i (Roman)`, with `1 (numeric)` being the default order type.

**Example:**
```html
<ol type="1">
  <li>item 1</li>
  <li>item 2</li>
  <li>item 3</li>
</ol>
```

#### Start Attribute

It represents the **starting value of a list order**. This means the list will start from a specific number, alphabet, or Roman numeral. For example:

```html
<ol start="7">
  <li>item 1</li>
  <li>item 2</li>
  <li>item 3</li>
</ol>
```

#### Reverse Attribute

It represents the **reverse order** of numbers. It does not support other order types like Roman numerals or alphabets. For example:

```html
<ol reverse>
  <li>item 1</li>
  <li>item 2</li>
  <li>item 3</li>
</ol>
```

Visit [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol) for more information about ordered lists.

# Definition list

^cec419

In HTML, a **Description or Definition list** is a type of list that is useful for multi-layered data, such as terms and their corresponding definitions.

1. The `<dl>` tag defines the start of the list.
2. The `<dt>` tag defines a term.
3. The `<dd>` tag defines the term's definition (description).

`<dl>` is a parent element, and the others are child elements in the syntax.

Let's take an example:

```html
<dl>
	<dt>HTML</dt>
	<dd>Hyper Text Markup-Language</dd>
	
	<dt>CSS</dt>
	<dd>Cascading stylesheet</dd>
	
	<dt>JS</dt>
	<dd>Javascript</dd>
</dl>
```

Visit [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl) for more information about definition lists.

# Detail list

^84261f

In HTML, `<details>` is a disclosure widget in which information is visible only when the widget is toggled into an *"open"* state.

`<details>` represents a *toggle description* that includes the <b>main text</b> and <b>subtext or a description of the main text</b>.

The basic syntax of the detail list involves `<details>` as the parent element, `<summary>` as a child element, and other elements like `<p>` or `<span>` serving as the **description part**.

```html
<details>
	<summary>WD</summary>
	<p>Web design</p>
	<span>format anything</span>
</details>
```

You can use *any type of tags* in the description for formatting text.

Visit [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details) for more information about detail lists.

# Nested or Custom list

