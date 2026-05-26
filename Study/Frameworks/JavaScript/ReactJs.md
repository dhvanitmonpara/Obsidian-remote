## Introduction

- React.js is a JavaScript library for building user interfaces.
- It was developed and is maintained by Facebook.
- React uses a component-based architecture, where the UI is broken down into reusable components.

### Components

- Components are the building blocks of React applications.
- They are reusable and can encapsulate UI logic, state, and rendering.
- Components can be either functional or class-based.

```jsx
// Functional Component
import React from 'react';

const HelloWorld = () => {
  return <h1>Hello, World!</h1>;
};

export default HelloWorld;
```

```jsx
// Class Component
import React, { Component } from 'react';

class HelloWorld extends Component {
  render() {
    return <h1>Hello, World!</h1>;
  }
}

export default HelloWorld;
```

### JSX

- JSX is a syntax extension for JavaScript that allows you to write HTML-like code in your JavaScript files.
- It gets transpiled into regular JavaScript code using tools like Babel.

```jsx
const element = <h1>Hello, World!</h1>;
```

### State and Props

- **State** is an object that represents the internal data of a component. It is mutable and can be updated using `setState()`.
- **Props** are inputs passed to a component from its parent. They are immutable and should not be modified directly.

```jsx
import React, { Component } from 'react';

class Counter extends Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0,
    };
  }

  increment = () => {
    this.setState({ count: this.state.count + 1 });
  };

  render() {
    return (
      <div>
        <h1>Count: {this.state.count}</h1>
        <button onClick={this.increment}>Increment</button>
      </div>
    );
  }
}

export default Counter;
```

### Lifecycle Methods

- React components have lifecycle methods that are automatically called at different stages of the component's lifecycle.
- These methods can be used to perform actions at specific points, such as fetching data or updating the DOM.

```jsx
import React, { Component } from 'react';

class LifecycleExample extends Component {
  constructor(props) {
    super(props);
    this.state = {
      data: null,
    };
  }

  componentDidMount() {
    // Fetch data from an API
    fetch('/api/data')
      .then((response) => response.json())
      .then((data) => this.setState({ data }));
  }

  render() {
    const { data } = this.state;

    if (!data) {
      return <div>Loading...</div>;
    }

    return <div>{/* Render data */}</div>;
  }
}

export default LifecycleExample;
```

# React Hooks

- React Hooks were introduced in React 16.8 and provide a way to use state and lifecycle methods in functional components.
- Popular hooks include `useState`, `useEffect`, `useContext`, and `useReducer`.

```jsx
import React, { useState, useEffect } from 'react';

const HookExample = () => {
  const [count, setCount] = useState(0);

  useEffect(() => {
    // Update document title
    document.title = `Count: ${count}`;
  }, [count]);

  const increment = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <h1>Count: {count}</h1>
      <button onClick={increment}>Increment</button>
    </div>
  );
};

export default HookExample;
```

These are just the basics of React.js. There's much more to learn, including topics like routing, context, Redux, and advanced concepts like code-splitting, server-side rendering, and performance optimization.

Sure, here are some notes on the `useState` hook in React:

## `useState` Hook

The `useState` hook is a function provided by React that allows you to add state to functional components. Before the introduction of hooks, state could only be used in class components.

### Syntax

```jsx
const [state, setState] = useState(initialState);
```

- `state` is the current state value.
- `setState` is a function that updates the state with a new value.
- `initialState` is the initial value of the state.

### Example

```jsx
import React, { useState } from 'react';

const Counter = () => {
  const [count, setCount] = useState(0);

  const increment = () => {
    setCount(count + 1);
  };

  const decrement = () => {
    setCount(count - 1);
  };

  return (
    <div>
      <h1>Count: {count}</h1>
      <button onClick={increment}>Increment</button>
      <button onClick={decrement}>Decrement</button>
    </div>
  );
};

export default Counter;
```

In this example, we create a `count` state variable with an initial value of `0`. We define two functions, `increment` and `decrement`, that update the `count` state using the `setCount` function provided by `useState`.

### Multiple State Variables

You can use multiple `useState` hooks in the same functional component to manage different state variables.

```jsx
import React, { useState } from 'react';

const Form = () => {
  const [name, setName] = useState('');
  const [email, setEmail] = useState('');

  const handleNameChange = (event) => {
    setName(event.target.value);
  };

  const handleEmailChange = (event) => {
    setEmail(event.target.value);
  };

  const handleSubmit = (event) => {
    event.preventDefault();
    // Submit form data
    console.log(`Name: ${name}, Email: ${email}`);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="text"
        value={name}
        onChange={handleNameChange}
        placeholder="Enter your name"
      />
      <input
        type="email"
        value={email}
        onChange={handleEmailChange}
        placeholder="Enter your email"
      />
      <button type="submit">Submit</button>
    </form>
  );
};

export default Form;
```

In this example, we have two state variables, `name` and `email`, managed by separate `useState` hooks. We define event handlers to update these state variables when the input fields change.

### Initial State as a Function

You can also pass a function to `useState` as the initial state, which is useful if the initial state needs to be computed based on props or other values.

```jsx
const [count, setCount] = useState(() => {
  const initialCount = someExpensiveComputation();
  return initialCount;
});
```

By passing a function to `useState`, the function will only be called once, during the initial render, avoiding unnecessary computations on subsequent re-renders.

The `useState` hook is a powerful tool that allows you to add state to functional components in React, making it easier to manage and update the component's state and re-render the component when necessary.