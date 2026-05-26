Javascript is a dynamic language.

# What is variables?

A variable is a container that stores a value.
A value of a javascript variable can be changed during execution of a program.


```javascript
var a = 7; // litral
var a = 7; // Declaring variable
```

The below code block represents var declaration, in which `'a'` is identifier and `'='` is an assignment operator.

# Rules for choosing variable names.

- letters, digits, underscores and `$ (sign)` allowed.
- Must begin with alphabet, `$`, `_`  or a letter.
- Javascript reserved words cannot be used as a variable name.
- Javascript is case sensitive.

# Var, let & const.

1. var is globally scoped while let & const are block scoped.
2. var can be updated & re-declared within its scope.
3. let can be updated but not re-declared.
4. const can be neither be updated nor be re-declared.
5. var (variables) are initialized with undefined whereas let and const variables are not initialized.
6. const must be initialized during declaration unlike let and const..

# Typecasting

```js
variable_name = new_var_type.parse_new_variable_type(new_var_name)
```

Example:

```js
age = Number.parseInt(age);
```

# Primitive Data-types & Objects

Primitive data types are a set of basic data types in javascript.
Object is a non-primitive data type in javascript.

These are the 7 primitive datatypes in javascript.

- Null
- Number
- String
- Symbol
- Boolean
- BigInt 
- Undefined

```javascript
let a = NULL; //Null
let b = 265; //Number
let c = "Harry"; //String
let d = symbol("I am good symbol"); //Symbol
let e = true; //Boolean
let f = BigInt(256) + BigInt(120); //BigInt
let g; //undefined
```

**Object:** An object in javascript can be created as follows.

```javascript
const A1 = {
	Name = "Harry",
	Section = 1,
	IsPrincipal = false
}

A1["Friend"] = "Shubham";
A1["Name"] = "Lovish";
```

A1 is a refrence not a object.
A1 = {...} means "Refrence = Object"
If the object will change still refrence does not matters of it.


```javascript
console.log(A1["Name"]);
console.log(A1.Name);
```

**Note:** Upper both statements are same with different format.

Next topic is [[Expressions & Conditions]].