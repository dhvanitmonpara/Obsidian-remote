# Creating a string

```js
let MyName = "My name is Harry"
// or
let MyName = 'My name is Harry'
```

# Escape sequence characters

| Character    | Description     |
| ------------ | --------------- |
| `\n`         | New line        |
| `\'` or `\"` | Quotation       |
| `\r`         | Carriage return |
| `\t`         | ChatGPT                |

# String Methods

```js
let name = "Harry"

console.log(name.length)

console.log(name[0])
console.log(name[1])
console.log(name[2])
console.log(name[3])
console.log(name[4])

console.log(name.toUpperCase)
console.log(name.toLowerCase)
```

```js
let name = "Harry"

console.log(name.slice(2, 4)) // print index no. 2 to 4 but isn't included
console.log(name.slice(2)) // print the whole string from index no. 2
console.log(name.replace("Har", "Per")
```

```js
let friend1 = "Naman"
let friend2 = "Roshan"

console.log(friend1.concat(" is a friend of ", friend2, " ok "))
```

```js
let friend = "    meena   "

console.log(friend.trim())
```

```js
let name = "Harry" + "Shivika" + "Raman" // You can also write concat strings like this
```

# Template literals

```js
let friend1 = "Harry"
let friend2 = "Raman"

console.log(`${friend1} is a friend of ${friend2`)
```

**References:**
Visit [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) for more details about string methods.
Link to [String references](https://replit.com/@codewithharry/13Strings?v=1#.tutorial/13-strings.md)
Link [String methods](https://replit.com/@codewithharry/14StringMethods?v=1#.tutorial/14-string-module.md) 

Next topic is [[Study/Languages/Javascript/Arrays|Arrays]].