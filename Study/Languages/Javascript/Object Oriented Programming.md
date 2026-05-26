### Prototype in JavaScript

In JavaScript, every object has a prototype. Prototypes are used for inheritance and to share properties and methods among objects. Understanding prototypes is fundamental for effective JavaScript programming.

#### Object Creation

Objects in JavaScript can be created using object literals or constructors.

```javascript
let obj = {}; // using object literal
let obj2 = new Object(); // using constructor
```

#### Prototype Chain

Each object in JavaScript has a prototype. When you access a property or method of an object, JavaScript first looks for it in that object. If it doesn't find it, it looks in the object's prototype, and continues up the prototype chain until it finds the property or method, or until it reaches the end of the chain (where the prototype is `null`).

```javascript
// Example of accessing properties through the prototype chain
let obj = {};
obj.toString(); // toString() is accessed via the Object prototype
```

#### `__proto__` Property

The `__proto__` property is a non-standard way of accessing an object's prototype. Although widely supported, it's not recommended for use in production code. Instead, `Object.getPrototypeOf()` and `Object.setPrototypeOf()` should be used.

```javascript
let obj = {};
console.log(obj.__proto__); // Accessing prototype via __proto__ (non-standard)
```

#### Constructor Functions and Prototypes

Constructor functions are used to create objects with a shared prototype.

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.sayHello = function() {
  console.log(`Hello, my name is ${this.name}`);
};

let person1 = new Person('Alice');
let person2 = new Person('Bob');

person1.sayHello(); // Outputs: Hello, my name is Alice
person2.sayHello(); // Outputs: Hello, my name is Bob
```

#### `Object.create()` Method

The `Object.create()` method creates a new object with the specified prototype object and properties.

```javascript
let protoObj = {
  greet: function() {
    console.log('Greetings!');
  }
};

let newObj = Object.create(protoObj);
newObj.greet(); // Outputs: Greetings!
```

#### Inheritance in JavaScript

In JavaScript, inheritance is achieved through prototypes. Objects inherit properties and methods from their prototypes.

```javascript
function Animal() {
  this.sound = ' ';
}

Animal.prototype.makeSound = function() {
  console.log(this.sound);
};

function Dog() {
  this.sound = 'Woof!';
}

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

let myDog = new Dog();
myDog.makeSound(); // Outputs: Woof!
```

Understanding prototypes is crucial for mastering JavaScript development, especially for implementing efficient inheritance and managing object properties and methods.

```js
let a = {
  name2: "Harry",
  language: "JavaScript",
  run: () => {
    alert("self run")
  }
}
console.log(a)


let p = {
  run: () => {
    alert("run")
  }
}

p.__proto__ = {
  name: "Jackie"
}

a.__proto__ = p
a.run()
console.log(a.name)
```

when you print any object, it returns an object in which prototypes are defined, use it for better understanding
You can create your own custom prototype:

```js
let a = () => {
	name: "harry",
	language: "Hindi"
}

let p = {
	run: () => {
		alert('run')
	}
}


a.__proto__ = p
a.run()
```

you can also assign a prototype to another prototype, search prototype chain for better understanding.

# Object Oriented Programming

### Object-Oriented Programming (OOP) in JavaScript

Object-Oriented Programming (OOP) is a programming paradigm centered around objects, which encapsulate data and behavior. JavaScript supports OOP principles, although its approach differs from classical OOP languages like Java or C++.

#### Objects

- **Objects**: In JavaScript, objects are collections of key-value pairs, where values can be data or functions (methods).

  ```javascript
  let obj = {
    key1: value1,
    key2: value2,
    method1: function() {
      // method body
    }
  };
  ```

#### Classes (Introduced in ECMAScript 2015)

- **Classes**: Classes in JavaScript provide a way to create objects based on a blueprint.

  ```javascript
  class Person {
    constructor(name, age) {
      this.name = name;
      this.age = age;
    }

    greet() {
      console.log(`Hello, my name is ${this.name} and I'm ${this.age} years old.`);
    }
  }

  let person = new Person('Alice', 30);
  person.greet(); // Outputs: Hello, my name is Alice and I'm 30 years old.
  ```

#### Constructor Functions

- **Constructor Functions**: Before the introduction of classes, constructor functions were used to create objects.

  ```javascript
  function Person(name, age) {
    this.name = name;
    this.age = age;
  }

  Person.prototype.greet = function() {
    console.log(`Hello, my name is ${this.name} and I'm ${this.age} years old.`);
  };

  let person = new Person('Bob', 25);
  person.greet(); // Outputs: Hello, my name is Bob and I'm 25 years old.
  ```

#### Inheritance

- **Inheritance**: JavaScript supports inheritance through prototype chaining.

  ```javascript
  class Animal {
    constructor(sound) {
      this.sound = sound;
    }

    makeSound() {
      console.log(this.sound);
    }
  }

  class Dog extends Animal {
    constructor() {
      super('Woof!');
    }
  }

  let dog = new Dog();
  dog.makeSound(); // Outputs: Woof!
  ```

#### Encapsulation and Abstraction

- **Encapsulation**: Encapsulation is the bundling of data and methods that operate on the data into a single unit (object).

- **Abstraction**: Abstraction is the concept of hiding complex implementation details and showing only the necessary features of an object.

#### Polymorphism

- **Polymorphism**: Polymorphism allows objects of different types to be treated as objects of a common superclass.

  ```javascript
  class Animal {
    speak() {
      console.log('Animal speaks');
    }
  }

  class Dog extends Animal {
    speak() {
      console.log('Woof!');
    }
  }

  class Cat extends Animal {
    speak() {
      console.log('Meow!');
    }
  }

  let dog = new Dog();
  let cat = new Cat();

  dog.speak(); // Outputs: Woof!
  cat.speak(); // Outputs: Meow!
  ```

JavaScript's flexibility and dynamic nature allow for the implementation of various OOP concepts, making it a powerful language for object-oriented programming paradigms. Understanding these concepts is essential for writing clean, maintainable, and scalable JavaScript code.

### Instanceof operator

Certainly! Here's an example block of code demonstrating the use of the `instanceof` operator in JavaScript:

```javascript
class Animal {
  // Animal class definition
}

class Dog extends Animal {
  // Dog class definition
}

let animal = new Animal();
let dog = new Dog();

console.log(dog instanceof Dog); // Outputs: true
console.log(dog instanceof Animal); // Outputs: true (since Dog extends Animal)

console.log(animal instanceof Dog); // Outputs: false
console.log(animal instanceof Animal); // Outputs: true
```

In this code:

- We define an `Animal` class and a `Dog` class which extends `Animal`.
- We create instances of `Animal` and `Dog` classes.
- We use the `instanceof` operator to check if an object is an instance of a particular class. It returns `true` if the object is an instance of the specified class or its subclasses, otherwise `false`.

### Method overloading

```js
class Employee {
  constructor(name) {
    console.log(`${name} - Employee's constructor is here`)
    this.name = name
  }
  login() {
    console.log(`Employee has logged in`);
  }

  logout() {
    console.log(`Employee has logged out`);
  }

  requestLeaves(leaves) {
    console.log(`Employee has requested ${leaves} leaves - Auto approved`)
  }
}

class Programmer extends Employee {
  constructor(name) {
    super(name)
    console.log(`This is a newly written constructor`)
  }
  // constructor(...args){ ---> If there is no constructor in the child class, this is created automatically
  //   super(...args)
  // }
  requestCoffee(x) {
    console.log(`Employee has requested ${x} coffees`)
  }
  requestLeaves(leaves) {
    super.requestLeaves(4)
    console.log("One extra is granted")
    // console.log(`Employee has requested ${leaves + 1} leaves (One extra)`)

  }
}

let e = new Programmer("Harry")
e.login()
e.requestLeaves(3)
```

## Cheat-sheet for OOP

#### Classes and Objects

```javascript
class MyClass {
  constructor(param1, param2) {
    this.property1 = param1;
    this.property2 = param2;
  }

  myMethod() {
    // Method body
  }
}

let myObject = new MyClass(value1, value2);
myObject.myMethod();
```

#### Constructors

```javascript
class MyClass {
  constructor(param1, param2) {
    this.property1 = param1;
    this.property2 = param2;
  }
}

let myObject = new MyClass(value1, value2);
```

#### Inheritance

```javascript
class ParentClass {
  // Parent class properties and methods
}

class ChildClass extends ParentClass {
  // Child class properties and methods
}

let childObject = new ChildClass();
```

#### Method Overloading

Method overloading is not directly supported in JavaScript. However, you can achieve similar behavior using conditional statements within methods.

```javascript
class MyClass {
  myMethod(param) {
    if (param === undefined) {
      // Method behavior without parameter
    } else {
      // Method behavior with parameter
    }
  }
}
```

#### Overriding Constructors

```javascript
class ParentClass {
  constructor(param) {
    this.property = param;
  }
}

class ChildClass extends ParentClass {
  constructor(param1, param2) {
    super(param1);
    this.property2 = param2;
  }
}
```

**Note:** You cannot use the `this` keyword before the `super()` keyword when invoking the constructor in a child class.
#### Static Methods

```javascript
class MyClass {
  static myStaticMethod() {
    // Static method body
  }
}

MyClass.myStaticMethod();
```

suggested to [visit replit](https://replit.com/@codewithharry/81staticmethods?v=1#script.js) for better understanding.

#### Getters and Setters

```javascript
class MyClass {
  constructor() {
    this._myProperty = 0;
  }

  get myProperty() {
    return this._myProperty;
  }

  set myProperty(value) {
    this._myProperty = value;
  }
}

let myObject = new MyClass();
myObject.myProperty = 10;
console.log(myObject.myProperty); // Outputs: 10
``` 

This cheatsheet summarizes key concepts from the provided JavaScript OOP tutorials. Each section provides a concise example to demonstrate the respective topic.

### References

[Video number 76](https://replit.com/@codewithharry/76classesandobjects?v=1#script.js) for Classes and objects.
[Video number 77 main](https://replit.com/@codewithharry/77Constructors?v=1#script.js) and [old one](https://replit.com/@codewithharry/77Constructors?v=1#script_old.js)for constructors.
[video number 78](https://replit.com/@codewithharry/78Inheritance?v=1#script.js) for Inheritance.
[Video number 79](https://replit.com/@codewithharry/79method-overriding?v=1#script.js) for Method overloading.
[Video number 80](https://replit.com/@codewithharry/80Overridingconstructors?v=1#script.js) for overriding constructors.
[Video number 81](https://replit.com/@codewithharry/81staticmethods?v=1#script.js) for Static methods.
[Video number 82](https://replit.com/@codewithharry/82gettersandsetters?v=1#script.js) for getters and setters.

Next topic is [[Advanced JavaScript topics]].