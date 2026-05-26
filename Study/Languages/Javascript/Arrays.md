## 1. Introduction
- Arrays store collections of elements with unique indices starting at 0.
- They can hold various data types.

## 2. Creating Arrays
```javascript
let fruits = ['apple', 'orange', 'banana'];
let colors = new Array('red', 'green', 'blue');
```

## 3. Accessing Elements
```javascript
let firstFruit = fruits[0]; // 'apple'
```

## 4. Array Methods
- Adding: `push()`, `unshift()`
- Removing: `pop()`, `shift()`
- Others: `splice()`, `concat()`, `slice()`, `indexOf()`, `isArray()`

## 5. Array Properties
```javascript
let length = fruits.length;
```

## 6. Iterating Through Arrays
- **For Loop**
```javascript
for (let i = 0; i < array.length; i++) { /* access array[i] */ }
```
- **ForEach Method**
```javascript
array.forEach(function(element) { /* access element */ });
```

## 7. Multidimensional Arrays
```javascript
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
```

## 8. Array Destructuring
```javascript
let [a, b, c] = [1, 2, 3];
```

## 9. Common Patterns
- **Map**
```javascript
let doubled = array.map(function(element) { return element * 2; });
```
- **Filter**
```javascript
let evens = array.filter(function(element) { return element % 2 === 0; });
```
- **Reduce**
```javascript
let sum = array.reduce(function(accumulator, current) { return accumulator + current; }, 0);
```

## 10. Array Methods for Modification
- **Non-Mutating**: `map()`, `filter()`, `concat()`, `slice()`, spread operator (`...`)
- **Mutating**: `push()`, `pop()`, `shift()`, `unshift()`, `splice()`

## 11. Array Sorting
- `sort()`, `reverse()`

## 12. Array Searching
- `indexOf()`, `includes()`, `find()`, `findIndex()`

## 13. `Array.isArray()`
```javascript
Array.isArray(array); // true or false
```

These reference notes cover essentials for working with JavaScript arrays, from creation to manipulation and iteration.

**References:**
Visit [Replit](https://replit.com/@codewithharry) for more details.
Link to [Array references](https://replit.com/@codewithharry/16Arrays?v=1#.tutorial/16_arrays.md) 
Link to [Array methods](https://replit.com/@codewithharry/17Arraymethods1?v=1#.tutorial/17_arraymethods.md) and [more array methods](https://replit.com/@codewithharry/18Arraymethods2?v=1#.tutorial/18_array_methods2.md)
Link to [Array loops](https://replit.com/@codewithharry/19ArrayLoops?v=1#.tutorial/19_array_loops.md)
Link to [map, filter and reduce](https://replit.com/@codewithharry/20mapfilterreduce?v=1#.tutorial/20_map_filter.md) methods.

Next topic is [[In browser JavaScript]].