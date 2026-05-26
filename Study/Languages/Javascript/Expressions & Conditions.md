# Operators in Js

**Arithmetic Operators:**

```javascript
+ Addition
- Subtraction
* Multiplication
** Exponentiation
/ Division
% Modulus
++ Increment
-- Decrement
```

**Assignment Operators:**

```javscript
= x=y
+= x=x+y
-= x=x-y
*= x=x*y
/= x=x/y 
**= x=x**y
```

**Comparison Operators:**

```javascript
== equal to
!= not equal
=== equal to value and type
!== not equal value or not equal type
> greater than
< less than
>= greater than or equal to
<= less than or equal to
? ternary operator
```

**Logical Operator:**

```javascript
&& logical and
|| logical or
! logical not
```

These are operators, a value which is operated is called operands and the value which is execute is called result.

# Conditional statements

- If statement
- If... else statement
- if... else if... else statement

**Example 1:** Age checker.
```javascript
let age = prompt("What is your age?");

if(age>10 && age<20) {
    console.log("Your age lies between 10 and 20")
} else {
    console.log("Your age does not lies between 10 and 20")
}
```

**Example 2:** Divisibility checker.
```javascript
let num = prompt("Enter yur nmber here:");
num = Number.parseInt(num);

console.log(typeof(num));

if(num%2==0 && num%3==0) {
    console.log("Yes, the number is divisable by 2 and 3");
} else {
    console.log("No, the number isn't divisable by 2 and 3");
}
```

# Switch Operator

Switch case operator is If... else alternative.

**Example:** Age checker.
```javascript
let age = prompt("What is your age?");
age = Number.parseInt(age)

switch(age) {
    case 12:
        console.log("Your age is 12");
        break
    case 13:
        console.log("Your age is 13");
        break
    case 14:
        console.log("Your age is 14");
        break
    case 15:
        console.log("Your age is 15");
        break
    default:
        console.log("Your age is not special");
}
```

# Ternary Operator

**Syntax of ternary operator.**

```javascript
condition ? Iftrue : IfnotTrue
```

**Example:** Age checker.
```javascript
let age = 12;

let a = age > 18 ? "You can drive" : "You cannont drive"
console.log(a)
```

Next topic is [[Loops & Functions]].