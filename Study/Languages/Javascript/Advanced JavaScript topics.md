# Date() function

- **Purpose:** 
  - Creates a new Date object that represents a specific point in time.
  - Used to work with dates and times in JavaScript.

- **Syntax:** 
  ```javascript
  let currentDate = new Date();
  ```
  - The `Date()` function can also take parameters to specify a particular date and time:
    ```javascript
    let specificDate = new Date(year, monthIndex, day, hour, minute, second, millisecond);
    ```

- **Return Value:**
  - A `Date` object representing the current date and time when no parameters are passed.
  - A `Date` object representing the specified date and time when parameters are provided.

- **Parameters:** 
  - `year` (optional): The year (e.g., 2022).
  - `monthIndex` (optional): The month, specified as a number from 0 (January) to 11 (December).
  - `day` (optional): The day of the month, from 1 to 31.
  - `hour` (optional): The hour, from 0 to 23.
  - `minute` (optional): The minute, from 0 to 59.
  - `second` (optional): The second, from 0 to 59.
  - `millisecond` (optional): The millisecond, from 0 to 999.

- **Methods:**
  - `getDate()`: Returns the day of the month (from 1 to 31).
  - `getDay()`: Returns the day of the week (from 0 for Sunday to 6 for Saturday).
  - `getMonth()`: Returns the month (from 0 for January to 11 for December).
  - `getFullYear()`: Returns the year (four digits).
  - `getHours()`: Returns the hour (from 0 to 23).
  - `getMinutes()`: Returns the minutes (from 0 to 59).
  - `getSeconds()`: Returns the seconds (from 0 to 59).
  - `getMilliseconds()`: Returns the milliseconds (from 0 to 999).
  - `toString()`: Returns a string representation of the date and time.
  - Many more methods for manipulating and formatting dates.

- **Examples:**
  ```javascript
  let currentDate = new Date();
  console.log(currentDate);
  // Output: Current date and time

  let specificDate = new Date(2022, 0, 1);
  console.log(specificDate);
  // Output: January 1, 2022

  console.log(specificDate.getMonth()); 
  // Output: 0 (January)

  console.log(specificDate.getDay()); 
  // Output: 6 (Saturday)
  ```

- **Note:**
  - Month indices are zero-based (0 for January, 11 for December).
  - Timezone considerations should be taken into account when working with dates.

```js
let currentDate = new Date();

let currentMonth = currentDate.getMonth();
console.log(currentMonth);
```

# Behaviour of `this` keyword

The `this` keyword in JavaScript behaves differently depending on how and where it is used. Here's an overview of its behavior:

1. **In Global Scope:**
   - In the global scope (outside of any function), `this` refers to the global object. In a web browser, the global object is `window`.

2. **In Function Scope:**
   - In a regular function (not in strict mode), `this` refers to the global object (`window` in a browser) when the function is called without an explicit context.
   - In strict mode, if a function is called without an explicit context, `this` remains `undefined`.

3. **In Object Methods:**
   - In an object method, `this` refers to the object that the method is called on. It allows the method to access and modify properties of the object.

4. **In Constructor Functions:**
   - In a constructor function (a function used with the `new` keyword to create objects), `this` refers to the newly created instance of the object.
   - When a constructor function is invoked with `new`, `this` inside the function points to the newly created object.

5. **In Event Handlers:**
   - In event handlers or callback functions attached to DOM elements, `this` typically refers to the element that triggered the event.
   - However, in modern JavaScript, using arrow functions in event handlers changes the behavior of `this`, making it lexically scoped (not bound to the element).

6. **Using Call, Apply, or Bind:**
   - The `call()`, `apply()`, and `bind()` methods allow you to specify the value of `this` explicitly when invoking a function.
   - `call()` and `apply()` immediately invoke the function, while `bind()` returns a new function with the specified `this` value bound, without invoking the function immediately.

7. **Arrow Functions:**
   - Arrow functions do not have their own `this` context. Instead, they inherit `this` from the enclosing lexical context (the context in which they are defined).

Understanding the behavior of `this` is crucial for writing correct and maintainable JavaScript code, especially in object-oriented and event-driven programming paradigms. It's important to pay attention to how `this` is used in different contexts to avoid unexpected behavior and bugs.

# IIFE

**Immediately Invoked Function Expressions (IIFE)**

- **Definition:**
  - An Immediately Invoked Function Expression (IIFE) is a JavaScript design pattern that executes a function immediately after it's created.

- **Syntax:**
  ```javascript
  (function() {
    // code to be executed immediately
  })();
  ```
  - Alternatively, you can wrap the entire function expression in parentheses to make it more readable: `(() => { /* code */ })();`

- **Purpose:**
  - Encapsulates code to avoid polluting the global scope.
  - Creates a new scope for variables, preventing them from conflicting with variables in other parts of the program.
  - Useful for initializing variables, defining utility functions, or executing setup code.

- **Benefits:**
  - Avoids naming collisions: Variables and functions declared within an IIFE are local to the function and do not pollute the global namespace.
  - Encapsulation: Helps maintain clean and modular code by encapsulating functionality within a private scope.
  - Self-contained: Allows the creation of modules that can be easily included in other scripts without causing conflicts.

- **Usage:**
  - Initializing variables:
    ```javascript
    (function() {
      var x = 10;
      console.log(x); // Output: 10
    })();
    ```
  - Avoiding global namespace pollution:
    ```javascript
    (function() {
      var utility = {
        // utility functions
      };
      // use utility functions internally
    })();
    ```

- **Parameter Passing:**
  - You can pass parameters to an IIFE:
    ```javascript
    (function(msg) {
      console.log(msg);
    })("Hello, World!"); // Output: Hello, World!
    ```

- **Common Mistake:**
  - Forgetting the parentheses around the function expression can lead to syntax errors:
    ```javascript
    // SyntaxError: Unexpected token (
    function() {
      // code
    }();
    ```

- **Use Cases:**
  - Modularizing code.
  - Creating isolated scopes.
  - Defining private variables and functions.
  - Bootstrapping applications.

- **Conclusion:**
  - IIFEs provide a convenient way to execute code immediately while maintaining a clean and encapsulated scope.
  - They are commonly used in JavaScript development to avoid global namespace pollution and create modular and maintainable code.

IIFEs are a powerful tool in JavaScript for creating self-contained and modular code, particularly in situations where you want to avoid polluting the global namespace or need to create isolated scopes.

# Destructuring assignments and spread operators

**Destructuring Assignments:**

- **Definition:**
  - Destructuring assignment is a convenient way of extracting multiple values from data stored in objects and arrays and assigning them to variables.

- **Syntax:**
  - Object Destructuring:
    ```javascript
    const { prop1, prop2 } = obj;
    ```
  - Array Destructuring:
    ```javascript
    const [item1, item2] = array;
    ```

- **Object Destructuring:**
  - Extracts values from objects based on their properties.
  - Variable names must match object property names to extract values.
  - Can provide default values.
  
- **Array Destructuring:**
  - Extracts values from arrays based on their positions.
  - Variables are assigned values based on their order in the array.
  - Can also provide default values.

- **Usage:**
  - Extracting values from function parameters.
  - Simplifying code by extracting values directly from objects or arrays.

- **Examples:**
  ```javascript
  const person = { name: 'John', age: 30 };
  const { name, age } = person;
  console.log(name, age); // Output: John 30

  const colors = ['red', 'green', 'blue'];
  const [firstColor, secondColor] = colors;
  console.log(firstColor, secondColor); // Output: red green
  ```

Visit [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment) for more syntaxes.

**Spread Operators:**

- **Definition:**
  - Spread operators allow an iterable (like an array or string) to be expanded into individual elements.

- **Syntax:**
  - Spread in Arrays:
    ```javascript
    const newArray = [...oldArray];
    ```
  - Spread in Objects:
    ```javascript
    const newObject = { ...oldObject };
    ```

- **Spread in Arrays:**
  - Copies elements from one array into another.
  - Can combine multiple arrays or add new elements.
  - Useful for creating shallow copies of arrays.

- **Spread in Objects:**
  - Copies properties from one object into another.
  - Can combine multiple objects or add new properties.
  - Useful for creating shallow copies of objects.

- **Usage:**
  - Copying arrays and objects without mutating the original.
  - Merging multiple arrays or objects into a single array or object.

- **Examples:**
  ```javascript
  const numbers = [1, 2, 3];
  const newNumbers = [...numbers, 4, 5];
  console.log(newNumbers); // Output: [1, 2, 3, 4, 5]

  const person = { name: 'John', age: 30 };
  const newPerson = { ...person, email: 'john@example.com' };
  console.log(newPerson); // Output: { name: 'John', age: 30, email: 'john@example.com' }
  ```

**Conclusion:**
- Destructuring assignments and spread operators are powerful features in JavaScript for working with objects and arrays.
- They provide concise syntax for extracting values and making copies without mutating the original data.
- Understanding and using these features can lead to more readable and maintainable code in JavaScript projects.

Visit [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax) for more syntaxes or watch video number [87](https://youtu.be/_BsE5kmJk6Q?si=SlE0ixAI6zq7JqTz) for better understanding.

# Scope in JavaScript

**Definition:**
- Scope refers to the visibility and accessibility of variables and functions within a program.

**Global Scope:**
- Variables/functions defined outside any function/block.
- Accessible from anywhere in the code.

**Local Scope:**
- Variables/functions declared within a function/block.
- Accessible only within the same function/block.

**Scope Behavior:**
- `var`: Function-scoped, hoisted to the top of its scope.
- `let`/`const`: Block-scoped, not hoisted.
- Inner scopes can access variables from outer scopes, but not vice versa.

**Importance:**
- Proper scope management prevents naming conflicts and unintended side effects.
- Helps maintain clean, modular, and bug-free code.

**Conclusion:**
- Understanding scope is fundamental for writing reliable and maintainable JavaScript code. It ensures variables and functions are used where and when they are intended, leading to more predictable program behavior.


# Hoisting

**Definition:**
- Hoisting is a JavaScript behavior where variable and function declarations are moved to the top of their containing scope during the compilation phase.

**Variables:**
- Variable declarations (using `var`, `let`, or `const`) are hoisted, but not their assignments.
- `var` declarations are hoisted to the top of their function scope or the global scope if declared outside any function.
- `let` and `const` declarations are hoisted to the top of their block scope, but they are not initialized until their declaration statement.

**Functions:**
- Function declarations are fully hoisted, including their definitions.
- Function expressions (assigned to variables) are not hoisted in the same way.

**Example:**
```javascript
console.log(x); // Output: undefined
var x = 10;

hoistedFunction(); // Output: "Function hoisted!"
function hoistedFunction() {
  console.log("Function hoisted!");
}

// Example with let
console.log(y); // Throws ReferenceError
let y = 20;
```

**Note:**
- Hoisting can lead to unexpected behavior if not understood properly.
- It's a feature of JavaScript's lexical scoping mechanism, but can sometimes be confusing if relied upon excessively.
- Best practice: Declare variables at the top of their scope and use functions before their declaration.


# Arrow function revisit

**Definition:**
- Arrow functions are a concise syntax for writing function expressions in JavaScript.

**Syntax:**
- Basic Syntax:
  ```javascript
  const functionName = () => {
    // function body
  };
  ```
- Shorter Syntax (for single expressions):
  ```javascript
  const functionName = () => /* expression */;
  ```

**Features:**
- Lexical `this`: Arrow functions do not have their own `this` context. They inherit `this` from the surrounding lexical scope.
- No `arguments` object: Arrow functions do not have their own `arguments` object. Instead, they inherit it from the containing function.
- Implicit return: Arrow functions automatically return the result of the expression without needing an explicit `return` statement for single expressions.

**Usage:**
- Callback functions: Concise syntax makes arrow functions ideal for use as callback functions.
- Method definitions: Often used for defining methods in objects.
- Avoiding `this` confusion: Provides a cleaner alternative to traditional function expressions when dealing with `this` context.

**Examples:**
```javascript
// Basic arrow function
const greet = () => {
  console.log("Hello!");
};

// Arrow function with parameters
const add = (a, b) => {
  return a + b;
};

// Arrow function with implicit return
const square = (x) => x * x;

// Arrow function as callback
const numbers = [1, 2, 3];
const doubledNumbers = numbers.map((num) => num * 2);
```

**Note:**
- Arrow functions are not suitable for all situations, particularly when dynamic `this` or `arguments` behavior is needed.
- Consider the lexical scoping behavior carefully, especially when using `this` inside arrow functions.


# Closures in JavaScript

**Definition:**
- A closure is a combination of a function and the lexical environment within which that function was declared. It allows a function to retain access to variables from its containing scope even after that scope has finished executing.

**Features:**
- Retention of scope: Inner functions have access to variables and parameters of their outer (enclosing) function even after the outer function has returned.
- Preservation of state: Allows functions to "remember" and maintain their own unique state across multiple invocations.

**Creation:**
- Closures are created whenever a function is defined within another function, and the inner function accesses variables from the outer function's scope.

**Usage:**
- Data privacy: Encapsulation of variables within a closure provides a way to create private variables and methods inaccessible from outside the closure.
- Functional programming: Closures enable the creation of higher-order functions and facilitate techniques such as currying and memoization.
- Event handlers and callbacks: Often used to maintain state or pass additional data to event handlers and callback functions.

**Example:**
```javascript
function outerFunction() {
  let outerVar = 'I am from outer function';

  function innerFunction() {
    console.log(outerVar);
  }

  return innerFunction;
}

const closure = outerFunction();
closure(); // Output: "I am from outer function"
```

**Considerations:**
- Be mindful of memory usage: Closures retain references to their enclosing scope, potentially leading to memory leaks if not managed properly.
- Understand the scope chain: Proper understanding of lexical scoping and closure behavior is crucial to avoid unexpected results.

**Conclusion:**
- Closures are a powerful and fundamental concept in JavaScript, enabling advanced programming techniques and providing a means to create encapsulated, reusable code. Understanding closures is essential for mastering JavaScript development.


Next topic is [[JavaScript on the server]].