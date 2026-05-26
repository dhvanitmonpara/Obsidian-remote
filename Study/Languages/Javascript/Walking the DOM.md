DOM tree refers tot he HTML page where all the nodes are objects. There can be three main type of nodes in the DOM tree.

1. text node
2. element node
3. comment node

```js
// it changes HTML title

document.title = "Kuchh bhi"
```

And also note that It'll return a string not `<title>` tag that's why you can change it using `'='` sign (without using `innerHTML`)

```js
// it will return whole HTML document

document.documentElement
```

# DOM methods

visit chapter-7 of codewithharry cpp playlist for better revision.

### Selecting Elements:
```javascript
// Select by ID
document.getElementById('elementId');

// Select by class name (returns NodeList)
document.getElementsByClassName('className');

// Select by tag name (returns NodeList)
document.getElementsByTagName('tagName');

// Select by CSS selector (returns NodeList)
document.querySelectorAll('selector');

// Select the first element matching the selector
document.querySelector('selector');
```

Remember that `getElementByClassName` and `getElementsByClassName` are different, first one returns an element whereas second one returns NodeList. 

### Modifying Elements:
```javascript
// Accessing element content
element.innerHTML = 'New content'; // Replaces inner HTML
element.textContent = 'New text'; // Replaces text content

// Modifying attributes
element.getAttribute('attributeName');
element.setAttribute('attributeName', 'value');
element.removeAttribute('attributeName');

// Modifying styles
element.style.property = 'value';

// Adding/Removing CSS classes
element.classList.add('className');
element.classList.remove('className');
element.classList.toggle('className'); // Add/remove based on existence

// Creating new elements
const newElement = document.createElement('tagName');

// Appending elements
parentElement.appendChild(newElement);
parentElement.insertBefore(newElement, referenceElement);

// Removing elements
parentElement.removeChild(childElement);
element.remove();
```

### Event Handling:
```javascript
// Add event listener
element.addEventListener('eventName', eventHandlerFunction);

// Remove event listener
element.removeEventListener('eventName', eventHandlerFunction);

// Event types: click, mouseover, mouseout, keydown, etc.
```

### Traversing the DOM:
```javascript
// Parent
element.parentNode;
element.parentElement;

// Children
element.childNodes; // Includes all nodes
element.children; // Only elements
element.firstElementChild;
element.lastElementChild;

// Siblings
element.previousElementSibling;
element.nextElementSibling;

// Descendants
element.querySelectorAll('selector');
```

In execution upper functions, `childNodes` looks like array but it is a HTML collection, You have to convert it into an array by using `Array.from()` function in 
order to use array methods.

```js
console.log(Array.from(document.body.childNodes));
```

It's also worth noting that the following statements are always true:

```js

// You can also use index to select a specific element
element.childNodes[0] === element.firstChild;
element.childNodes[element.childNodes.length - 1] === element.lastChild;
```

### Window and Document:
```javascript
// Window dimensions
window.innerWidth;
window.innerHeight;

// Document dimensions
document.documentElement.clientWidth;
document.documentElement.clientHeight;

// Scrolling
window.scrollTo(x, y);
window.scrollBy(x, y);
element.scrollIntoView();
```

# Table in DOM

## Table Links

Certain DOM elements may provide additional properties specific to their type for convenience. The `table` element supports the following properties:

- **table.rows**: Returns a live HTMLCollection of all the **rows** in the table.
- **table.caption**: Returns the **caption** element of the table.
- **table.tHead**: Returns the **thead** element of the table.
- **table.tFoot**: Returns the **tfoot** element of the table.
- **table.tBodies**: Returns a live HTMLCollection of all the **tbody** elements in the table.

Similarly, the `tr` element supports the following properties:

- **tr.cells**: Returns a live HTMLCollection of all the **cells** in the row.
- **tr.sectionRowIndex**: Returns the index of the row in the current section (thead, tbody, or tfoot).
- **tr.rowIndex**: Returns the index of the row in the table.

the `td` element also support the some properties inlcluding:

- **td.cellIndex**: Returns the index of the cell in the row.

You can also combine multiple of these like `t.tBodies[0].rows` or `t.tHead.firstElementChild` or `t.rows[0].rowIndex`, where t is:

```js
let t = document.body.firstElementChild.firstElementChild; // the first element child of the body is container div, and its own first child is the table   
```
To see these properties in action, you can run the following code snippet in your browser console:

```js
let t = document.body.firstElementChild.firstElementChild;

for (let i = 0; i < t.rows.length; i++) {      
	let row = t.rows[i];      
	console.log(row)  
	}   
```

This will print all the rows in the table. You can also try to print the cells in the first row by running the following code snippet:

```js  
let t = document.body.firstElementChild.firstElementChild;

let row = t.rows[0];  

for (let i = 0; i < row.cells.length; i++) {      
	let cell = row.cells[i];      
	console.log(cell)  
	}   
```

# Input tag value

```js
// it'll access input value given by user from HTML doc.
selectedInputTag.value
```

Next topic is [[Events and DOM properties]].