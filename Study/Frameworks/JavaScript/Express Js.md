---
sticker: lucide//chevron-up
---
## Introduction
Express.js is a minimalist web application framework for Node.js. It provides a robust set of features for building web and mobile applications.

## Installation
To install Express.js, you need to have Node.js installed on your system. You can install Express.js using npm, the Node.js package manager.

```bash
npm install express
```

## Creating a Simple Server
To create a simple server using Express.js, create a JavaScript file (e.g., `app.js`) and require Express module.

```javascript
const express = require('express');
const app = express();

const PORT = 3000;

app.get('/', (req, res) => {
  res.send('Hello, Express!');
});

app.listen(PORT, () => {
  console.log(`Server is running on port ${PORT}`);
});
```

Save the file and run it using Node.js:

```bash
node app.js
```

Now, you can visit `http://localhost:3000` in your web browser to see the message "Hello, Express!".

## Routing
Express.js provides a simple and effective way to define routes for your application.

```javascript
app.get('/about', (req, res) => {
  res.send('About Us');
});

app.post('/contact', (req, res) => {
  res.send('Contact Us');
});
```

## Middleware
Middleware functions are functions that have access to the request object (`req`), the response object (`res`), and the next middleware function in the application’s request-response cycle.

```javascript
// Middleware function
const logger = (req, res, next) => {
  console.log(`Request: ${req.method} ${req.url}`);
  next();
};

// Using middleware
app.use(logger);
```

## Template Engines
Express.js supports several template engines for generating HTML dynamically. Some popular ones include EJS, Handlebars, and Pug.

```javascript
// Set view engine
app.set('view engine', 'ejs');

// Render a view
app.get('/profile', (req, res) => {
  res.render('profile', { name: 'John Doe', age: 30 });
});
```

## Conclusion
Express.js is a powerful framework for building web applications with Node.js. This guide covers only the basics; there's a lot more to explore and learn. Check out the [official documentation](https://expressjs.com/) for more detailed information.

Feel free to experiment with different features and modules to build amazing web applications!

## Mongoose
Refer [mongoose documentation](https://www.npmjs.com/package/mongoose)  for better understanding.

1. download and import mongoose
2. connect to mongoDB
3. create schema
4. export model
5. import model in anoher file
6. use mongoDB queries

**Note:** If it gives an error then use async-await fuction to resolve it

```js
const mongoose = require('mongoose')

mongoose.connect('mongodb://127.0.0.1:27017/newDatabaseName')
const userSchema = mongoose.Schema({
	username: String,
	city: String,
	age: Number
})

module.exports = mongoose.model('newCollectionName', userSchema)
```

# NPM modules

Visit [here](https://www.npmjs.com/package/package) for npm modules with their documentations.

- [nodemon](https://www.npmjs.com/package/nodemon)
- [cookie-parser](https://www.npmjs.com/package/cookie-parser)
- [express-session](https://www.npmjs.com/package/express-session)
- [connect-flash](https://www.npmjs.com/package/connect-flash)
- [mongoose](https://www.npmjs.com/package/mongoose)