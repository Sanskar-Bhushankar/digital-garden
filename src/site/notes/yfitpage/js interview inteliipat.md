---
{"dg-publish":true,"permalink":"/yfitpage/js interview inteliipat/","created":"2025-08-01T01:26:04.739+05:30"}
---


## 1. what is template literals

combination of `this backtick` and $ and {}to write executable code inside a string
a=10
console.log(`value of a is ${a}`)

---
## 2. what is hoisting
where var is declared or say hoisted like in js the running happens in 2 phase one is declaration or hoisting other is execution
for var when hoisted if we call we get undefined for const and let we get reference error without assigning value to them

---
## 3. var let and const
let and const is block scoped { } and var is function scope so we dont prefer using var use let or const 

---
## 4. types of datatypes
#### 1. primitive immutable or cannot be modified
   - number 
   - strings
   - boolean
   - symbol
   - undefined - default value provided to variable that has been declare but not assigned any valye
   - null - when we declare a value but we dont want to contain any value in it
#### 2. non primitive
- objects - collection of key valye pair
- arrays - 
- functions - block of code

---
## 5. what is array
- same datatype
- zero index
- group of similar data
- access using index

---
## 6. == vs ===
== is equality operator
=== is strict equality operator

example
```
'5'==5 is true
'5'===5 is false
```

type coersion 

---
## 7. what is isnan
check if its not a number
like `isNaN('sanskar')` is false
like `isNaN('123')` is true

---
## 8. what is null and undefined
null is where we dont wana assign value to variable
undefined is default value assigned to a var without value

---
## 9. use of typeof
dtype of typeof(42)

---
# medium module

## 11. what is map operator

```
a=[1,2,3,4,5]
double = a.map(n=>n*2)
console.log(a)
console.log(double)
```

used to create a new array with specific function to each element without mod existing array

---
## 12. what is event bubbling and event capturing

event bubbling - model where events are handled from inner most to outermost
event capturing where model events are captured from outermost to innermost

---
## 13.what are higher order function

function that can accept another function or return as an argument,
map is a higher order function

---
## 14. what is IIFE (Immediately invoked fuction expression)

without being called runs
```js
(fucntion(){
console.log("hell0 world")
})
```

---
## closures
function that remembers the env in which it was created even after the outer func has finished executing

---
## setTimeout ,setInterval,clearOnterval

```js
let a= 10

const time= setInterval(()=>{

    console.log(a--)

},1000)
setTimeout(()=>{

    clearInterval(time)

},10000)
```

---
## promises

async task (pending,fullfiled,rejected)

```js

```

---
## reduce

```js
const num=[1,2,3,4,5]
const sum =num.reduce((acc,curr)=>{
    return acc+curr
})
console.log(sum)
```