# Timeout functions

### setTimeout()

Use `setTimeout()` for late execution of specific code.

```js
setTimeout(()=>{
// code
}, 2000) // time in miliseconds that means 1000 = 1 seconds
```

To instantly invoke `setTimeout()` function, just use:

```js
(setTimeout(()=>{

})() 
```

### setInterval()

```js
setInterval(()=>{
	// code
}) 
// it will continuously run function (use clearTimeout() to stop this)

another sytax for setTimeout is:

const sum = (a, b, c) => {
	console.log(a+b+c);
}
```

To use `setTimeout()` with arguments:

```js
setTimeout(sum, 1000, 2, 5, 4) // last 3 integers are arguments and it will be invoked after 1s(1000 mili seconds)
```

**Note:** You can also use this syntax for `setInterval()` to pass arguments.
### clearTimeout()

To clear a timeout, you can store the `setTimeout()` function in a variable and then pass that variable as an argument to `clearTimeout()`. Here's the corrected version:

```js
// Store setTimeout function in a variable
var timeoutVariable = setTimeout(function() {
    // code here
}, 5000);

// Clear the timeout using clearTimeout and passing the variable name
clearTimeout(timeoutVariable);

```
# HTML methods
### console.dir

```js
console.dir; // it will return tag as an object
```

### innerHTML & outerHTML

`innerHTML` will return HTML within selected element and `outerHTML` will return `innerHTML`+`selected element` with attributes.

```js
elem.innerHTML = "Hello world!";
elem.outerHTML = "<h1>Hello world!</h1>";
```

`document.body.textContent` will return selected element as a text
`elem.data` will do same thing.

```js
document.body.textContent;
elem.data;
```

You can use `hidden` as a attribute as `display=none` and change using:

```js
selectedElement.hidden = false;
```

`elem.getAttribute` to get attribute
`elem.hasAttribute` to check attribute
and use `elem.getAttribute.value` or `elem.hasAttribute.value` for get or check attribute value.

```js
elem.getAttribute;
elem.hasAttribute;

elem.getAttribute.value;
elem.hasAttribute.value;
```

`elem.setAttribute('attribute', 'value')` to set attribute
`elem.removeAttribute` to remove attribute
`elem.attributes` to get collection of attribute

```js
elem.setAttribute('attribute', 'value');
elem.removeattribute;
elem.attributes;
```

### insertAdjecentHTML

- `beforebegin`: Inserts the specified content immediately before the element itself.
- `afterbegin`: Inserts the specified content at the beginning of the element, before any existing content.
- `beforeend`: Inserts the specified content at the end of the element, after any existing content.
- `afterend`: Inserts the specified content immediately after the element itself.

```js
// there are four methods to insert adjecent in html

elem.insertAdjecentHTML('beforbegin', 'newcontent');
elem.insertAdjecentHTML('beforeend', 'newcontent');
elem.insertAdjecentHTML('afterbegin', 'newcontent');
elem.insertAdjecentHTML('afterend', 'newcontent');
```

Here's an example:

```js
elem.insertAdjacentHTML('beforeend', '<p>This is new content added before the end.</p>');
```

Use `elem.remove()` to remove node.

### appendChild in HTML

- `elem.before(a)`: Inserts the element 'a' before the element 'elem'.
- `elem.prepend(a)`: Inserts the element 'a' as the first child of the element 'elem'.
- `elem.appendChild(a)`: Inserts the element 'a' as the last child of the element 'elem'. (Note: The correct method name is `appendChild`, not `append.)
- `elem.after(a)`: Inserts the element 'a' after the element 'elem'.

Remember that `a` is an element or group of element which is stored in `const`.

```js
const a = document.createElement('div');	 // stored command for creating a new element
a.innherHTML = '<h1>Hello world!</h1>';	// adding inner HTML for created element

elem.before(a);
elem.prepend(a);
elem.appendChild(a);
elem.after(a);


selectedElement.replaceWith(a);	// for replacing element
```

Here's an example:

```js
const a = document.createElement('div');	// stored command for creating a new element
a.innherHTML = '<h1>Hello world!</h1>';  // adding inner HTML for created element

selectedElement.appendChild(a);  // for appending child after a selected element
```

### classList

- `classList.toggle():` Toggle a class in the class list of 'elem'.
- `classList.add():` Add a class to the class list of 'elem'.
- `classList.remove():` Remove a class from the class list of 'elem'
- `classList.contains():` Check if 'elem' contains a specific class

```js
elem.classList.toggle()
elem.classList.add()
elem.classList.remove()
elem.classList.contains()
```
# Event listener 

You can use `onclick` as a attribute in HTML document.

```js
// Basic syntax
elem.addEventListener('event', ()=>{
	// code
})
```

Here's an example:

```js
btn.addEventListener('click', ()=>{
	console.log('Hello world!');
})
```

### Event listener with arguments

```js
btn.addEventListener('click', (e)=>{
	e.target.style.background = "green";
})
```

In upper code `e` is `pointer event`, provided by browser. just print it using `console.log()` for better understanding.

You can use `elem.target` to access it. refer to [this](https://youtu.be/rFq0HVOdDo4?si=UQR7R6tU5l9Iahf_) video for better understanding.

you can also use `elem.removeEventListener()` to remove event listener.

```js
elem.removeEventListener();
```

Next topic is [[Callbacks, Promise and Async-Await]].