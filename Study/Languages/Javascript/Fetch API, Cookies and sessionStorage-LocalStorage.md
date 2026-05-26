# Fetch API

## Introduction
The Fetch API provides a modern, promise-based way to make HTTP requests in JavaScript. It offers a more powerful and flexible alternative to the older `XMLHttpRequest` object.

## Basic Syntax
```javascript
fetch(url)
  .then(response => {
    // Handle response
  })
  .catch(error => {
    // Handle error
  });
```

## Making GET Requests
```javascript
fetch(url)
  .then(response => response.json())
  .then(data => {
    // Handle data
  })
  .catch(error => {
    // Handle error
  });
```

## Making POST Requests
```javascript
const postData = {
  key: 'value'
};

const requestOptions = {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(postData)
};

fetch(url, requestOptions)
  .then(response => response.json())
  .then(data => {
    // Handle data
  })
  .catch(error => {
    // Handle error
  });
```

## Handling Responses
The `response` object returned by `fetch` contains information about the HTTP response, such as status code and headers. Use methods like `json()`, `text()`, or `blob()` to extract the response body.

## Error Handling
Use `.catch()` to handle errors that may occur during the request.

## Handling CORS
Cross-Origin Resource Sharing (CORS) can affect requests made using the Fetch API. Ensure that the server's CORS policy allows requests from your domain.

## Conclusion
The Fetch API simplifies making HTTP requests in JavaScript and provides a cleaner syntax compared to `XMLHttpRequest`. It's widely supported in modern browsers and can be polyfilled for older ones.

Take a look at [Fetch API](https://replit.com/@codewithharry/66FetchAPI?v=1#script.js) and [Post request](https://replit.com/@codewithharry/67POSTrequest?v=1#script.js) or you should watch video number [66](https://youtu.be/Atq7VjVbaA8?si=Gl6qaNMt8deccZAl) and [67](https://youtu.be/57SrCBCxdgc?si=bv1C0NXMFdhM0fzl) for better understanding.

# Working with Cookies in JavaScript

## Introduction
Cookies are small pieces of data stored on the client's browser. They are commonly used for session management, user preferences, and tracking. JavaScript provides methods for working with cookies to read, write, and delete them.

## Setting Cookies
```javascript
document.cookie = "key=value; expires=Fri, 31 Dec 9999 23:59:59 GMT; path=/";
```
- `key=value`: Sets a cookie with the specified key-value pair.
- `expires`: Sets the expiration date of the cookie. If not specified, the cookie is deleted when the browser session ends.
- `path`: Specifies the path for which the cookie is valid.

**Note:** use `decodeURIComponent` and `encodeURIComponent` to store cookie in a better way.

## Getting Cookies
```javascript
const cookies = document.cookie;
```
- `document.cookie` returns a string containing all cookies associated with the current document.

## Parsing Cookies
```javascript
function parseCookies() {
  const cookies = document.cookie.split(';');
  const cookieMap = {};
  cookies.forEach(cookie => {
    const [key, value] = cookie.trim().split('=');
    cookieMap[key] = decodeURIComponent(value);
  });
  return cookieMap;
}

const parsedCookies = parseCookies();
```
- `parseCookies()` function splits the `document.cookie` string and returns an object containing key-value pairs of cookies.

## Deleting Cookies
```javascript
function deleteCookie(key) {
  document.cookie = `${key}=; expires=Thu, 01 Jan 1970 00:00:00 GMT; path=/`;
}

deleteCookie('key');
```
- Setting a cookie with an expiration date in the past effectively deletes the cookie.

## Considerations
- **Security**: Avoid storing sensitive information in cookies as they can be accessed and modified by the client.
- **Size Limit**: Cookies have a size limit (usually 4KB per cookie), so avoid storing large amounts of data.
- **Domain and Path**: Cookies are associated with a specific domain and path. Be mindful of these attributes when setting or deleting cookies.

## Conclusion
Cookies are a fundamental part of web development for storing small pieces of data on the client's browser. JavaScript provides methods for working with cookies to manage user sessions and preferences effectively.

```js
// print coockies
console.log(document.cookie)

// coockie methods
// remember that these methods wil not overwrite coockies
// they will aligned with their keys like array or objects, In this examle "name" is a key "=" is a operator and "harry1122334400" is a value
document.cookie = "name=harry1122334400"
document.cookie = "name2=harry11223344002"
document.cookie = "name=harry"

let key = prompt("enter your key")
let value = prompt("enter your value")

// ecoding and decoding input for storing ";" (semicolon).
document.cookie = `${encodeURIComponent(key)}=${encodeURIComponent(value)}`
console.log(document.cookie)
```

Watch video number [68](https://youtu.be/sHrwueeeMmY?si=5SlufLcrh8IFUmtf) for better understanding.

# Working with localStorage in JavaScript

## Introduction
`localStorage` is a web storage API in JavaScript that allows developers to store key-value pairs locally within a user's browser. It provides a simple way to persistently store data across browser sessions.

## Setting Data
```javascript
localStorage.setItem('key', 'value');
```
- `setItem()` method sets the value of a specified key in the `localStorage` object.

## Getting Data
```javascript
const value = localStorage.getItem('key');
```
- `getItem()` method retrieves the value of the specified key from the `localStorage` object.

## Updating Data
Updating data in `localStorage` is similar to setting data. You can use `setItem()` to update an existing key-value pair.

## Removing Data
```javascript
localStorage.removeItem('key');
```
- `removeItem()` method removes the specified key and its corresponding value from the `localStorage` object.

## Clearing All Data
```javascript
localStorage.clear();
```
- `clear()` method removes all key-value pairs from the `localStorage` object, effectively clearing all stored data.

## Data Persistence
- Data stored in `localStorage` persists even after the browser is closed and reopened, as long as it's not cleared programmatically or by the user.
- Data stored in `localStorage` is specific to the domain and protocol of the website.

## Storage Limitations
- `localStorage` has a storage limit of about 5-10MB per domain, depending on the browser.
- Do not store sensitive information in `localStorage` as it is accessible to client-side JavaScript.

## Use Cases
- Storing user preferences or settings.
- Caching data for faster access.
- Implementing client-side caching for web applications.

## Considerations
- Always handle errors when working with localStorage, especially when setting or getting data.
- Be mindful of the storage limit and avoid storing excessive data in localStorage.

## Conclusion
`localStorage` is a useful feature in web development for storing small to moderate amounts of data locally within the user's browser. It provides a simple and efficient way to persist data across browser sessions without the need for server-side storage.

Watch video number [69](https://youtu.be/A98SPz5XLwY?si=MvPl7zVOcnxF0K_i) for better understanding.
# Working with sessionStorage in JavaScript

## Introduction
sessionStorage is a web storage API in JavaScript that allows developers to store key-value pairs locally within a user's browser for the duration of the page session. Data stored in sessionStorage is cleared when the page session ends, such as when the browser tab is closed.

## Setting Data
```javascript
sessionStorage.setItem('key', 'value');
```
- `setItem()` method sets the value of a specified key in the `sessionStorage` object.

## Getting Data
```javascript
const value = sessionStorage.getItem('key');
```
- `getItem()` method retrieves the value of the specified key from the sessionStorage object.

## Updating Data
Updating data in sessionStorage is similar to setting data. You can use `setItem()` to update an existing key-value pair.

## Removing Data
```javascript
sessionStorage.removeItem('key');
```
- `removeItem()` method removes the specified key and its corresponding value from the `sessionStorage` object.

## Clearing All Data
```javascript
sessionStorage.clear();
```
- `clear()` method removes all key-value pairs from the `sessionStorage` object, effectively clearing all stored data for the current session.

## Data Persistence
- Data stored in `sessionStorage` persists only for the duration of the page session.
- Closing the browser tab or navigating away from the page clears all `sessionStorage` data associated with that page.

## Use Cases
- Storing temporary user data during a session, such as form data or session identifiers.
- Implementing client-side caching for session-specific data.

## Considerations
- `sessionStorage` is limited to the current browser tab or window and is not shared between tabs or windows.
- Avoid storing sensitive information in `sessionStorage` as it is accessible to client-side JavaScript and is not secure for sensitive data.

## Conclusion
`sessionStorage` is a useful feature in web development for storing temporary data locally within the user's browser for the duration of a page session. It provides a simple and efficient way to persist data within a session without the need for server-side storage.

```js
// if storage get changed (storage event listening)
window.onstorage = (e) => {
        alert("changed")
        console.log(e)
}
```

## JavaScript Storage Event Listener.

```javascript
window.onstorage = (event) => {
  console.log(event);
}
```

- **Purpose:** Sets up a callback function to listen for changes in the storage area.
- **Usage:** When data in the storage (localStorage or sessionStorage) is modified by another document in the same domain, the callback function is triggered.
- **Event Object (`event`):**
  - Contains information about the storage event, including:
    - `event.key`: The key that was changed.
    - `event.oldValue`: The old value before the change.
    - `event.newValue`: The new value after the change.
    - `event.storageArea`: The storage object (localStorage or sessionStorage) where the change occurred.
- **Console Log:** Logs the storage event object to the console.

This code snippet allows you to monitor and respond to changes in the storage area within your web application.

Watch video number [70](https://youtu.be/rfSJeox61vA?si=X656UKrnkkMDFElY) for better understanding.

Next topic is [[Object Oriented Programming]].