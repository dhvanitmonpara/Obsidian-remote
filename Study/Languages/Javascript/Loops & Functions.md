# Types of loops

1. For loop
2. for in loop
3. for of loop
4. while loop
5. do-while loop

# For loop

**Syntax of for loop:**
```javascript
for(initialization; condition; increment/decriment) {
	// code to be executed
}
```

**Example:**
```js
let num = prompt("Enter a value : ");

let sum = 0;
for(let i = 0; num>i; i++) {
    sum += (i+1);
}
```

# For-in loop

It uses for display objects and work with arrays.
```js
for(key in object) {
	// code to be executed
}
```

**Example:**
```js
let obj = {
    Harry: 90,
    shruti: 40,
    Harsh: 25,
    Manasvi: 37,
    Shradha: 70
}

// For-in loop
for(let a in obj) {
    console.log("Marks of " + a + " is " + obj[a])
}
```

# For-of loop

It uses for print an array. and note that object must be iterable.
```js
for(variable of iterable) {
	// code to be executed
}
```

**Example:**
```js
// For-of loop
for(let a of "Harry") {
    console.log(a)
}
```

# While loop

```js
while(condition) {
	// code to be executed
	// increment/decrement
}
```

# Do-while loop

It executed at least once.
```js
do{
	// code to be executed
} while(condition)
```

# Functions

```js
// without parameters

function MyFunc() {
	// code
}

// with parameter

function binalFunc(parameter-1,parameter-2) {
	// code
}
```

**Example:**

```js
function sum(x ,y) {
	return (x*y)
}

let a = 1
let b = 2
let c = 3

console.log("sum of " + a + " and " + b + " is " + sum(a, b))
console.log("sum of " + b + " and " + c + " is " + sum(b, c))
console.log("sum of " + c + " and " + c + " is " + sum(c, a))
```

# Use const instead

```js
// This is arrow function BTW
const sum = (x,y)=>{
	let c = x + y
	return c
}

let a = 3
let b = 7
console.log("The sum is " + sum(a,b))
```

Next topic is [[Strings]].