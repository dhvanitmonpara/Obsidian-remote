# JavaScript on the server

#### Introduction
- JavaScript is traditionally associated with client-side scripting for web browsers. However, with the advent of Node.js, JavaScript can now also be used for server-side programming.

#### Node.js
- Node.js is an open-source, cross-platform JavaScript runtime environment that executes JavaScript code server-side.
- It allows developers to build scalable network applications using JavaScript on the server side.

#### Benefits of JavaScript on the Server
1. **Unified Language**: Allows developers to use JavaScript both on the client and server sides, promoting code reuse and reducing context-switching.
2. **Event-Driven and Asynchronous I/O**: Leveraging non-blocking I/O operations allows for high concurrency and scalability.
3. **Rich Ecosystem**: Access to npm, the world's largest package ecosystem, provides a wide range of libraries and tools for server-side development.
4. **Performance**: Node.js is known for its high performance due to its event-driven architecture and efficient handling of I/O operations.

#### Use Cases
1. **API Development**: Node.js is commonly used to build RESTful APIs and microservices due to its lightweight and fast execution.
2. **Real-time Applications**: It's well-suited for building real-time applications like chat applications, multiplayer games, and live data streaming.
3. **Server-side Rendering (SSR)**: With libraries like React, Vue.js, and Angular, Node.js can perform server-side rendering to improve SEO and initial page load times.
4. **Command-line Tools**: Node.js can be used to build command-line tools and utilities, making it versatile beyond web development.

#### Popular Frameworks and Libraries
- **Express.js**: Minimal and flexible Node.js web application framework for building APIs and web applications.
- **Koa.js**: Next-generation web framework designed by the team behind Express, focusing on middleware composition.
- **Socket.io**: Library for real-time web applications, enabling bidirectional communication between web clients and servers.
- **GraphQL**: Query language for APIs, enabling clients to request only the data they need, often used with libraries like Apollo Server.

#### Conclusion
- JavaScript on the server with Node.js provides a powerful platform for building scalable, efficient, and real-time web applications.
- Its event-driven architecture, rich ecosystem, and unified language make it a compelling choice for modern web development.

Watch [Js on the server](https://youtu.be/CG-7dYcozwI?si=dfRrKVuEpJX75Uf3) for better understanding.
# npm (Node Package Manager) Notes

#### npm init
- `npm init`: Initializes a new Node.js project. It prompts the user to enter information about the project such as name, version, description, entry point, test command, git repository, keywords, author, and license.
- `npm init -y`: Initializes a new Node.js project with default values, skipping the prompts.

#### npm install
- `npm install`: Installs dependencies specified in the `package.json` file. It creates a `node_modules` folder and installs the dependencies listed in `package.json`.
- `npm install <package-name>`: Installs a specific package locally.
- `npm install -g <package-name>`: Installs a package globally, making it available as a command-line tool.

#### npm stands for Node Package Manager
- npm is the default package manager for Node.js, used to manage packages and dependencies for Node.js projects.
- It allows developers to easily install, share, and manage dependencies needed for their projects.

#### Using CommonJS and ES6 Modules
- If you're using CommonJS syntax (require and module.exports), you don't need to specify `"type": "module"` in your `package.json`.
- If you're using ES6 Modules (`import` and `export`), you need to specify `"type": "module"` in your `package.json` to indicate that your project uses ES6 module syntax.

#### npm install -g nodemon
- `nodemon` is a utility that monitors for changes in your Node.js application and automatically restarts the server.
- `npm install -g nodemon` installs nodemon globally, allowing you to use it as a command-line tool across your system.
- After installation, you can use `nodemon` to start your server instead of `node`. It provides a more convenient development experience by automatically restarting the server when changes are detected.

These are some basic notes on npm and its usage in Node.js development. Feel free to expand on these notes or ask for more details on any specific aspect.

Watch [npm and nodejs packages](https://youtu.be/nSFe1-kpfbQ?si=5y6BwO4-iFPUpR4W) for better understanding.
# Modules in JavaScript

#### Introduction
- Modules are a way to organize code into separate files or modules, making code more maintainable, reusable, and easier to understand.

#### Types of Modules
1. **CommonJS Modules**:
   - Used in Node.js for server-side JavaScript.
   - Syntax: `require()` to import modules and `module.exports` or `exports` to export variables, functions, or objects.

2. **ES6 Modules**:
   - Standardized module system introduced in ECMAScript 2015 (ES6).
   - Syntax: `import` to import modules and `export` to export variables, functions, or objects.

#### Benefits
1. **Encapsulation**: Modules encapsulate code, preventing pollution of the global namespace.
2. **Reusability**: Modules can be reused across different parts of an application or in multiple projects.
3. **Organization**: Modules facilitate better organization of code by separating functionality into distinct units.
4. **Dependency Management**: Modules allow managing dependencies by specifying what functionality is exposed externally.

#### CommonJS Syntax Example
```javascript
// Exporting module
const add = (a, b) => a + b;
module.exports = add;

// Importing module
const addFunction = require('./add');
console.log(addFunction(2, 3)); // Output: 5
```

#### ES6 Modules Syntax Example
```javascript
// Exporting module
export const add = (a, b) => a + b;

// Importing module
import { add } from './add';
console.log(add(2, 3)); // Output: 5
```

#### Browser Support
- ES6 Modules are natively supported in modern browsers but require server-side transpilation for broader compatibility.
- CommonJS Modules are primarily used in Node.js environments.

#### Conclusion
- Modules are a fundamental concept in JavaScript for organizing and structuring code.
- Whether using CommonJS or ES6 Modules, modular programming enhances code maintainability, reusability, and organization.

watch [modules in Js](https://youtu.be/wCkHbaLG5cw?si=YR96TIEUPp8tp2rW) for better understanding.

# Express.js

#### Introduction
- Express.js is a minimal and flexible Node.js web application framework that provides a robust set of features for building web and mobile applications.
- It's designed to make the process of building web applications and APIs in Node.js easier and more manageable.

#### Key Features
1. **Routing**: Express provides a powerful routing system to define routes for handling different HTTP requests (GET, POST, PUT, DELETE, etc.).
2. **Middleware**: Middleware functions in Express are functions that have access to the request, response, and next middleware function in the application's request-response cycle. Middleware functions can perform tasks such as logging, authentication, error handling, etc.
3. **Templating Engines**: Express supports various templating engines like EJS, Pug (formerly Jade), Handlebars, etc., to generate dynamic HTML content.
4. **Static File Serving**: Express can serve static files such as HTML, CSS, JavaScript, images, etc., using the `express.static` middleware.
5. **Error Handling**: Express provides mechanisms for handling errors gracefully, allowing developers to define error-handling middleware.
6. **Integration with Connect Middleware**: Express is built on top of Connect middleware, which provides a set of robust middleware for handling HTTP requests.
7. **RESTful API Development**: Express is commonly used for building RESTful APIs due to its simplicity and flexibility.
8. **Database Integration**: Express can be easily integrated with various databases such as MongoDB, MySQL, PostgreSQL, etc., using middleware like Mongoose, Sequelize, etc.

#### Example
```javascript
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Hello World!');
});

app.listen(3000, () => {
  console.log('Server is running on port 3000');
});
```

#### Installation
- You can install Express.js in your Node.js project using npm:
  ```
  npm install express
  ```

#### Conclusion
- Express.js is a powerful and lightweight web application framework for Node.js, widely used for building web servers, APIs, and full-stack applications.
- Its simplicity, flexibility, and robust feature set make it a popular choice among developers for building modern web applications in Node.js.

### Regular Expressions (Regex)

#### Introduction
- Regular expressions, often abbreviated as regex or regexp, are sequences of characters that define a search pattern, mainly for string matching.
- They provide a concise and flexible means for identifying patterns within text data.

#### Basic Syntax
- **Literals**: Characters that match themselves.
- **Metacharacters**: Characters with special meanings.
- **Modifiers**: Define how the search pattern should be applied.
- **Quantifiers**: Define the number of occurrences of a character or group in the pattern.

#### Common Metacharacters
1. **`.` (Dot)**: Matches any single character except newline.
2. **`^` (Caret)**: Matches the beginning of a line.
3. **`$` (Dollar)**: Matches the end of a line.
4. **`\` (Backslash)**: Escapes special characters to be treated as literals.
5. **`[]` (Character Class)**: Matches any single character within the brackets.
6. **`|` (Pipe)**: Alternation, matches either the pattern before or after the pipe.
7. **`()` (Grouping)**: Groups patterns together, allows applying quantifiers or modifiers to them as a whole.

#### Common Quantifiers
1. **`*` (Zero or more)**: Matches zero or more occurrences of the preceding character or group.
2. **`+` (One or more)**: Matches one or more occurrences of the preceding character or group.
3. **`?` (Zero or one)**: Matches zero or one occurrence of the preceding character or group.
4. **`{}` (Quantifier)**: Matches a specific number of occurrences of the preceding character or group.

#### Example Patterns
1. **Email Validation**:
   ```
   /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/
   ```
2. **URL Matching**:
   ```
   /^(https?:\/\/)?(www\.)?([a-zA-Z0-9-]+)\.([a-zA-Z]{2,})(\/\S*)?$/
   ```
3. **Phone Number Validation**:
   ```
   /^(\+\d{1,3}\s)?\(?\d{3}\)?[\s.-]?\d{3}[\s.-]?\d{4}$/
   ```

#### Use Cases
- **Data Validation**: Validate user input such as email addresses, phone numbers, passwords, etc.
- **Search and Replace**: Find and replace patterns within text data.
- **Text Parsing**: Extract specific information from text data.
- **URL Routing**: Define routes in web applications.

#### Tools and Resources
- Online Regex Testers: RegExr, Regex101, RegexPal.
- Regular Expressions Libraries: JavaScript (built-in RegExp), Python (re module), Java (java.util.regex).

#### Conclusion
- Regular expressions are powerful tools for pattern matching and text processing.
- Understanding regex syntax and mastering their usage can greatly enhance your ability to manipulate and analyze text data effectively.

Visit [regx](https://regexr.com/) for resources and watch [regular expressions](https://youtu.be/zeMPry3ak6Y?si=Gy89OaSNec0pLmel)for better understanding.

# Event Loop in JavaScript

#### Introduction
- The event loop is a crucial concept in JavaScript that allows asynchronous operations to be executed in a non-blocking manner.
- It's responsible for managing the execution of code, handling events, and maintaining the responsiveness of JavaScript applications.

#### Event Loop Phases
1. **Call Stack**:
   - The initial phase where synchronous code execution occurs.
   - Functions and their respective contexts are stacked as they're invoked.
   - Executes functions in a Last-In-First-Out (LIFO) manner.

2. **Callback Queue**:
   - Asynchronous operations such as timers, I/O operations, and events are processed here.
   - Upon completion, their associated callback functions are queued in the callback queue.

3. **Event Loop**:
   - Monitors the call stack and callback queue continuously.
   - If the call stack is empty, it moves callback functions from the callback queue to the call stack for execution.

#### Microtasks and Macrotasks
- **Microtasks**:
  - Microtasks have a higher priority than macrotasks.
  - Examples include Promise callbacks (`then`, `catch`, `finally`) and `process.nextTick()` in Node.js.
  - Microtasks are executed before the next macrotask begins.

- **Macrotasks**:
  - Macrotasks include tasks scheduled by setTimeout, setInterval, I/O operations, and UI rendering.
  - They're executed after the call stack is empty and there are no microtasks in the queue.

#### Example
```javascript
console.log('Start');

setTimeout(() => {
  console.log('Timeout callback');
}, 0);

Promise.resolve().then(() => {
  console.log('Promise resolved');
});

console.log('End');
```

#### Output Explanation
1. `'Start'` is logged to the console.
2. The `setTimeout` and `Promise.resolve().then()` are registered as asynchronous tasks.
3. `'End'` is logged to the console.
4. Microtask: `'Promise resolved'` is logged.
5. Macrotask: `'Timeout callback'` is logged.

#### Use Cases
- Handling asynchronous operations like fetching data from servers, reading files, or waiting for user input.
- Implementing responsive UIs without blocking the main thread.
- Writing server-side code in Node.js, where handling I/O operations asynchronously is crucial for scalability.

#### Conclusion
- Understanding the event loop is essential for writing efficient, non-blocking JavaScript code.
- It enables developers to handle asynchronous operations effectively and build responsive, performant applications across various environments, including web browsers and Node.js.

Watch [event loop in Js](https://youtu.be/vFJbKR6zfCE?si=Lf0DpmiGA-mprNNt) for better understanding.

Go to classwork folder and review some projects and exersices.