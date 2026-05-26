# Callback functions

- **Definition**: 
  In JavaScript, a callback function is a function that is passed as an argument to another function and is executed after the completion of some task or at a particular event.
<br>
- **Syntax**:
  ```javascript
function someFunction(callback) {
    // Task execution
    callback();
}
// focus on brackets, we passed a whole function as an argument
  someFunction(function() {
      // Callback function definition
  });
  ```
<br>
- **Asynchronous Nature**: 
  Callback functions are commonly used in asynchronous programming to handle tasks such as fetching data from a server or performing I/O operations without blocking the execution of other code.
<br>
- **Event Handling**:
  Callback functions are frequently utilized to respond to events triggered by user interaction or system events.  
  <br>

- **Error Handling**:
  Callbacks are also used for error handling, where the callback function is executed with an error parameter if an error occurs during the execution of the main function.
<br>
- **Example**:
  ```javascript
  function fetchData(url, callback) {
      // Simulate fetching data
      setTimeout(function() {
          const data = 'Data retrieved successfully';
          callback(null, data); // Pass error as null and data
      }, 2000);
  }

  fetchData('https://example.com/api/data', function(err, data) {
      if (err) {
          console.log('Error:', err);
      } else {
          console.log('Data:', data);
      }
  });
  ```

<br>

**Pros**:
  - Facilitates better code organization and readability, especially in asynchronous scenarios.
  - Promotes reusability of code.
<br>
**Cons**:
  - Can lead to callback hell, especially in deeply nested asynchronous operations.
  - Error handling can become cumbersome in complex callback chains.

<br>

```js
function loadScript(src, callback) {
  var script = document.createElement("script");
  script.src = src;
  script.onload = function () {
    console.log("Loaded script with SRC: " + src);
    callback(null, src);
  };

  script.onerror = function () {
    console.log("Error loading script with SRC: " + src);
    callback(new Error("Src got some error"));
  };
  document.body.appendChild(script);
}
```

## Extra info 

There are significant differences between callback functions and normal function calls in JavaScript:
<br>
1. **Execution Timing**:
   - In a normal function call, the function is executed immediately when it's invoked.
   - In a callback function, the function is passed as an argument to another function and is executed later, usually after some asynchronous task completes or upon the occurrence of a specific event.
<br>
2. **Asynchronous Nature**:
   - Callback functions are commonly used in asynchronous programming to handle tasks such as fetching data from a server or responding to user interactions without blocking the execution of other code.
   - Normal function calls are synchronous by default, meaning that the code execution will wait for the function to complete before moving on to the next line.
<br>
3. **Usage**:
   - Normal function calls are used for routine tasks and operations where immediate execution is desired.
   - Callback functions are used when you want to define behavior that should occur after a certain task is completed or when an event is triggered.
<br>
4. **Passing Functions**:
   - In a normal function call, you directly pass arguments to the function being called.
   - In a callback function, you pass a reference to a function as an argument to another function, which will later invoke that function.
<br>
5. **Error Handling**:
   - Error handling can be different between normal function calls and callback functions. In normal function calls, errors are typically handled within the function itself using try-catch blocks or conditional statements. In callback functions, errors are often passed as parameters to the callback function itself or handled within the callback function, depending on the specific use case.

In summary, while both callback functions and normal function calls involve invoking functions, callback functions are primarily used for asynchronous operations and event handling, providing a way to execute code at a later time or in response to specific events.

**.onload:**
```javascript
elem.onload = function() {
    console.log('Resource loaded successfully.');
};
```
Executes when the specified resource finishes loading without errors.

**.onerror:**
```javascript
elem.onerror = function() {
    console.error('Error loading resource.');
};
```
Triggers upon encountering an error during resource loading.

### Passing error to the callback funtion

```js
function loadScript(src, callback) {
  var script = document.createElement("script");
  script.src = src;
  script.onload = function() {
    console.log("Loaded script with SRC: " + src);
    // Call the callback function with null error and the src
    callback(null, src);
  }
  // Execute if there's an error loading the script
  script.onerror = function() {
    console.log("Error loading script with SRC: " + src);
    // Call the callback function with an error
    callback(new Error("Src got some error"));
  }
  document.body.appendChild(script);
}

// Callback function to greet good morning
function goodmorning(error, src) {
  // If there's an error loading the script
  if (error) {
    console.log(error);
    // Send an emergency message to the CEO
    sendEmergencyMessageToCeo();
    return;
  }
  // If script is loaded successfully, show alert
  alert('Good morning' + src);
}

// Load Bootstrap script with callback function
loadScript("https://cdn.jsdelivr.net/npm/bootstrap@5.2.1/dist/js/bootstrap.bundle.min.js", goodmorning);

```

# Promises

- **Definition:**
  - Promises are objects representing the eventual completion or failure of an asynchronous operation, and its resulting value.
<br>
- **States:**
  - **Pending**: Initial state, neither fulfilled nor rejected.
  - **Fulfilled (Resolved)**: Operation completed successfully.
  - **Rejected**: Operation failed.
<br>
- **Syntax:**
  ```javascript
  const myPromise = new Promise((resolve, reject) => {
      // Async operation
      if (/* operation successful */) {
          resolve(/* value */); // fulfilled
      } else {
          reject(/* reason */); // rejected
      }
  });
  ```
<br>

- **Methods:**
  - **.then()**: Used to handle fulfilled state.
  - **.catch()**: Used to handle rejected state.
  - **.finally()**: Executes code after promise resolves or rejects.
<br>
- **Chaining:**
  - Promises can be chained using `.then()` to handle sequential asynchronous operations.
<br>
- **Error Handling:**
  - Errors can be caught using `.catch()` to prevent unhandled rejections.
<br>
- **Example:**
  ```javascript
  const myAsyncFunction = () => {
      return new Promise((resolve, reject) => {
          setTimeout(() => {
              const success = true; // if it become false then it will throw an error which will caught by error handler
              if (success) {
                  resolve('Operation completed successfully');
              } else {
                  reject('Operation failed');
              }
          }, 2000);
      });
  };

  myAsyncFunction()
      .then((result) => {
          console.log(result);
      })
      .catch((error) => {
          console.error(error);
      });
  ```
<br>
- **Benefits:**
  - Improves code readability and maintainability in asynchronous operations.
  - Enables better error handling and control flow.
<br>
- **Compatibility:**
  - Supported in modern JavaScript environments, and widely used in modern web development.

Alternative syntax for `.catch` 

```js
myPromise.then((value)=>{
        console.log(value) 
},(error)=>{
        console.log(error)
})
```

```js
reject(new error('I am an error'))
```

You can get promise state as an object by writing variable name (in which you stored your `new promise`) for example:

```js
// js file

let myPromise = new promise((resolve, reject)=>{
// code
}) 

// In browser console
myPromise
```

## Promise chaining

```js
let p1 = new Promise((resolve, reject) => {
        setTimeout(() => {
                console.log("Resolved after 2 seconds")
                resolve(56)
        }, 2000)
})

p1.then((value) => {
        console.log(value)
        // return new promise to new .then
        return new Promise((resolve, reject) => {
                setTimeout(() => { resolve("Promise 2") }, 2000)
        }) 
}).then((value) => {
        console.log("We are done")
        return 2
}).then((value)=>{
        console.log("Now we are pakka done")
})

```
<br>
Here's an example:

```js
const loadScript = (src) => {
        return new Promise((resolve, reject) => {
                let script = document.createElement("script")
                script.type = "text/javascript"
                script.src = src
                document.body.appendChild(script)
                script.onload = (script) => {
                        resolve("Script has been loaded sir")
                }
                script.onerror = () => { reject(0) }
        })
}

let p1 = loadScript("https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js")
p1.then((value) => {
        console.log(value)
        return loadScript("https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js")
}).then((value) => {
        console.log("Second script ready")
}).catch((error) => {
        console.log("We are sorry but we are having problems loading this script")
})
```

You can also attach multiple event handler in a single promise, and it will execute parallelly.
Refer [this](https://replit.com/@codewithharry/57multiplehandlers?v=1#script.js) for better understanding.

## Promise API methods

**Promise API Methods:**
<br>
1. **Promise.resolve(value)**:
   Returns a Promise object that is resolved with the given value.
<br>
2. **Promise.reject(reason)**:
   Returns a Promise object that is rejected with the given reason.
<br>
3. **Promise.all(iterable)**:
   Takes an iterable of Promise objects and returns a single Promise that resolves when all of the promises in the iterable have resolved or one of them has rejected.
<br>
4. **Promise.race(iterable)**:
   Takes an iterable of Promise objects and returns a single Promise that resolves or rejects as soon as one of the promises in the iterable resolves or rejects, with the value or reason from that promise.
<br>
5. **Promise.allSettled(iterable)**:
   Takes an iterable of Promise objects and returns a single Promise that resolves after all of the promises in the iterable have either resolved or rejected, with an array of objects that each describe the outcome of each promise.
<br>
6. **Promise.any(iterable)**:
   Takes an iterable of Promise objects and returns a single Promise that resolves as soon as one of the promises in the iterable resolves, with the value from that promise. If all of the promises are rejected, it returns a Promise that is rejected with an AggregateError, a new subclass of Error that groups together individual errors.
<br>
7. **Promise.prototype.then(onFulfilled, onRejected)**:
   Appends fulfillment and rejection handlers to the Promise, and returns a new Promise resolving to the return value of the called handler.
<br>
8. **Promise.prototype.catch(onRejected)**:
   Appends a rejection handler callback to the Promise, and returns a new Promise resolving to the return value of the callback if it is called, or to its original fulfillment value if the Promise is instead fulfilled.
<br>
9. **Promise.prototype.finally(onFinally)**:
   Appends a handler to the Promise, and returns a new Promise resolving to the original promise's fulfillment value or rejection reason when the handler returns a promise.

These methods provide powerful tools for working with asynchronous operations and handling their results in a variety of scenarios.

# Async/Await

**Async/Await:**
<br>
- **Introduction:**
  - Async/Await is a syntactic sugar built on top of promises to simplify asynchronous code.
<br>
- **Async Function:**
  - An async function is a function declared with the `async` keyword, which enables the use of the `await` keyword within it.
  - Async functions always return a promise.
<br>
- **Await Operator:**
  - The `await` keyword is used within async functions to pause execution and wait for the promise to resolve before proceeding.
  - It can only be used inside async functions.
<br>
- **Syntax:**
  ```javascript
  async function myAsyncFunction() {
      try {
          const result = await somePromise;
          // Do something with result
      } catch (error) {
          // Handle error
      }
  }
  ```

- **Benefits:**
  - Improves readability by making asynchronous code appear more synchronous.
  - Simplifies error handling with try/catch blocks.
<br>
- **Error Handling:**
  - Errors thrown inside async functions are caught automatically by the surrounding async function or by the caller if not caught within.
  - Use try/catch blocks for explicit error handling within async functions.

**Try/Catch:**

- **Introduction:**
  - The `try` and `catch` blocks are used for error handling in JavaScript.
<br>
- **Try Block:**
  - The `try` block contains the code that may throw an error.
<br>
- **Catch Block:**
  - The `catch` block is executed if an error occurs within the try block.
  - It contains the code to handle the error.
<br>
- **Finally Block:**
  - The `finally` block executed in all cases.
<br>
- **Syntax:**
  ```javascript
  try {
      // Code that may throw an error
  } catch (error) {
      // Code to handle the error
  } finally {
	  // code to enclose things
  }
  ```

- **Error Object:**
  - The `error` object passed to the catch block contains information about the error, such as its message and stack trace.
<br>
- **Error Handling:**
  - Use try/catch blocks to handle synchronous errors.
  - Also used for handling errors in asynchronous code when combined with async/await.
<br>
- **Benefits:**
  - Provides a structured way to handle errors and prevent program crashes.
  - Allows for graceful degradation in case of unexpected issues.

These constructs are essential tools for managing errors and controlling the flow of execution in JavaScript applications, especially in asynchronous contexts.

## Error object

In JavaScript, when dealing with asynchronous operations using `async/await`, error handling is crucial. When an error occurs within an asynchronous function, an `Error` object is typically thrown. This object can have several properties that provide useful information about the error. Here are the common properties you might find in an `Error` object:

1. `err.name`: This property represents the name of the error. It usually provides a standardized string indicating the type of error. For example, it might be `"SyntaxError"`, `"TypeError"`, `"ReferenceError"`, etc. depending on the type of error encountered.

2. `err.message`: This property contains a human-readable description of the error. It provides more specific information about what went wrong. Developers often use this message for debugging or logging purposes.

3. `err.stack`: This property contains a stack trace, which is a list of function calls that were in progress when the error was thrown. It includes information about the call stack at the time the error occurred, such as the line numbers and filenames of the functions involved. This can be very useful for debugging, as it helps you trace the origins of the error.

Here's an example of how you might use these properties in practice:

```javascript
async function fetchData() {
  try {
    // some asynchronous operation that might throw an error
    const data = await fetch('https://example.com/data');
    const jsonData = await data.json();
    return jsonData;
  } catch (err) {
    console.error('Error name:', err.name);
    console.error('Error message:', err.message);
    console.error('Stack trace:', err.stack);
    // Handle the error accordingly
  }
}
```

In this example, if an error occurs during the asynchronous operation inside the `fetchData` function, it will be caught in the `catch` block, and information about the error will be logged using the properties of the `err` object.

### To throw new error

```js
throw new RefferenceError('Harry is not defined')	// to throw new custom error
```

There are multiple type of errors, check [MDN]() for all of them.

Next topic is [[Fetch API, Cookies and sessionStorage-LocalStorage]].