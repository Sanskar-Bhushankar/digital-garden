---
{"dg-publish":true,"permalink":"/dump/yfitpage/js-one-shot/","dgPassFrontmatter":true,"dg-note-properties":{}}
---

#### primitive data types

1. string
2. number (1,1.5)
3. true /false
4. boolean
5. undefined - **default** value for uninitialized variables
6. null - **intentional** absence of value set by the develope

example of undefined
```
let w
console.log(w)
```

example of null
```
let obj ={}
console.log(obj.key)
```

```
function test(){}
console.log(test())
```

```
let b = null;
console.log(typeof b); // "object" (this is a historical bug in JS)
```

never do x= undefined as it is by default undefined and its not a good practice

---
### why js is dynamic lang
JavaScript is called a **dynamic language** because **you don’t have to declare variable types** — types are determined **at runtime**, not in advance. This gives JavaScript flexibility, but also introduces potential bugs.

```
let x = 5;       // x is a number
x = "hello";     // now x is a string
x = true;        // now x is a boolean
```
 
 **Functions Are First-Class and Dynamic**
- You can create, pass, and change functions at runtime.
```
function greet() {
  return "Hello";
}

greet = "Now I'm a string!";
console.log(greet); // Outputs: Now I'm a string!

```

---
### reference types
```
let courses ={
	title:"java",
	desc:"project",
	ratings:3
}

console.log(courses.title)
or
console.log(courses['title'])
```

---
### value types vs reference types

> [!NOTE]
> primitive / value types
>  String, number, boolean, undefined, null, symbol
> 
> reference types 
> objects, arrays, function
> so what happens is when u reference a primitive data type like y=x then the value is copied so even if we changed x value the y value will contain the old x value and not new x value and when u reference a ref data type then the reference is copied not value so if the object or array chages it changes for both x and y 

```
let x="sanskar"
let y=x
let x ="sw"

console.log(x)
console.log(y)

--------output------
x: sw
y: sanskar
```

but now 

```
a=[1,2,3]
b=a

a=[4,5,6]

--------output------
a=[4,5,6]
b=[1,2,3]
```
here even its a reference var the b is pointing to old object in memory and a point to new object
so if we dont want to point or create new obj 


```
a=[1,2,3]
b=a

a.push(4)

--------output------
a=[1,2,3,4]
b=[1,2,3,4]
```

---
## object
An object in JavaScript is a dynamic collection of unordered properties defined as key-value pairs.
in JavaScript, **all reference data types are objects**, or **derived from objects**.


### How JavaScript Code is Executed

==Execution Context==

Every time a JavaScript program runs, an **execution context** is created. Initially, this is the **Global Execution Context (GEC)**.  
Every time a function is created or called, a new **Function Execution Context** is also created.

Before executing the actual code, JavaScript performs a setup step called the **memory allocation phase**.  
After that, it executes the code line by line — because JavaScript is **single-threaded**.

So, an execution context has **2 phases**:

1. **Memory Allocation Phase (Variable Environment)**  
    All variables and functions are allocated memory.
    
    - Variables are set to `undefined`.
        
    - Function declarations are fully stored.
        
2. **Code Execution Phase (Thread of Execution)**  
    The code runs top to bottom, and actual values are assigned to variables, and functions are executed.
    

---

### Example Code

```js
a = 10;
console.log(a);
```

When this code runs:

1. **Memory Allocation Phase**
    
    - `a` is allocated in memory and initialized as `undefined`.
        
    - You can see this if you inspect the global scope in browser dev tools (Sources > Scope).
        
    - Under the global scope, `a: undefined` appears — this is the variable being hoisted.
        
2. **Code Execution Phase**
    
    - Line 1: `a = 10` → now `a` holds the value `10`.
        
    - Line 2: `console.log(a)` → prints `10`.
        

---

### Concept: Hoisting

This behavior — where variables are moved to the top of their scope and initialized with `undefined` — is called **hoisting**.

- Only `var` declarations and function declarations are hoisted.
    
- `let` and `const` are hoisted too, but **not initialized** — they remain in a **Temporal Dead Zone (TDZ)** until the line where they're defined.
    

---

### Summary

- JavaScript code runs inside **execution contexts**.
    
- Each context goes through:
    
    1. **Memory allocation** (hoisting happens here).
        
    2. **Code execution** (actual values are assigned).
        
- The **Global Execution Context** is created first.
    
- New contexts are pushed to a **call stack** when functions are called.
    

This model helps explain how things like hoisting, closures, and scoping work in JavaScript.

---

### let, const, var

> [!important]
> const and let are more strict than var they dont allow global dec of un def
> avoid using var
> use const where the value will not change

![](/img/user/attachments/Pasted%20image%2020250730034203.png)

so in global whben we use let it goes as undefined when u use var or const we get error but if we have values like var a =10 or const a =10 then in global the values are lke 
`a: <value unavailable>` 
it gets initiazled for the phase one of memory alloc only if values are there

---
## temporal dead zone

The **Temporal Dead Zone (TDZ)** is a behavior in JavaScript that refers to the period between:
1. When a variable is **declared** using `let` or `const`
2. And when it is **initialized** (assigned a value)
During this "zone", the variable **exists** but **cannot be accessed** — doing so throws a **ReferenceError**.

like example 
accessing before declaration
```
console.log(x); // ReferenceError: Cannot access 'x' before initialization
let x = 10;
```

or same scope
```
{
  console.log(a); // ReferenceError
  let a = 5;
}

```

#### 🔁 What You Already Know (Summarized):

|Keyword|Hoisted?|Initialized on hoist?|Accessible before line?|TDZ Exists?|
|---|---|---|---|---|
|`var`|Yes|Yes (as `undefined`)|Yes|No|
|`let`|Yes|**No**|No (ReferenceError)|Yes|
|`const`|Yes|**No**|No (ReferenceError)|Yes|
🔍 Let's Go Deep: Why This Happens

**1. All Declarations Are Hoisted**

Yes — `var`, `let`, and `const` **are all hoisted**.

But the **difference is how the JavaScript engine handles them during hoisting**:

 ✅ `var` Hoisting Behavior:

```js
console.log(x); // undefined
var x = 5;
```

Here’s what JS engine does behind the scenes:

```js
var x;          // declaration hoisted and initialized to undefined
console.log(x); // undefined
x = 5;          // assignment
```

So `var` is **hoisted AND initialized to `undefined` immediately**, which is why there's **no TDZ**.

---

❌ `let` / `const` Hoisting Behavior:

```js
console.log(y); // ReferenceError
let y = 10;
```

Here's what JS does internally:

```js
// y is hoisted, BUT not initialized
// TDZ starts here
console.log(y); // Error: cannot access 'y' before initialization
let y = 10;     // only here it's initialized
```

So `let` and `const` **are hoisted**, but **not initialized**. Until they are initialized, they are in the **Temporal Dead Zone**.

---

🔐 Why JavaScript Created TDZ for `let` and `const`

### Main reasons:

1. **To avoid bugs caused by hoisting and undefined variables**
    
2. `let` and `const` are meant to provide **block scoping** (more predictable)
    
3. Encourages **declaration-before-use**, which is better for clean, safe code
    

---

 ⚠️ Why `var` Is Allowed but Risky

```js
console.log(a); // undefined
var a = 10;
```

This is **allowed**, but **dangerous** because:

- You **think** you're using `a`, but it's just `undefined`.
    
- It can cause silent bugs and hard-to-debug behavior.
    

That's why ES6 introduced `let` and `const` with TDZ — to **prevent accidental misuse**.

---
 🧪 A Quick Visual (Execution Context)

When JS runs code, it creates a **"memory phase"** and an **"execution phase"**.

During the **memory phase**:

- `var` is added to memory and **initialized to `undefined`**.
    
- `let` and `const` are added to memory but **not initialized** — they are **uninitialized bindings**.
    

During the **execution phase**:

- You assign values.
    
- Trying to access an uninitialized `let` or `const` before this point causes a ReferenceError (TDZ).
    
🔚 Summary

| Feature             | `var`                    | `let` / `const`                    |
| ------------------- | ------------------------ | ---------------------------------- |
| Hoisted?            | Yes                      | Yes                                |
| Initialized early?  | Yes, to `undefined`      | **No** (uninitialized)             |
| Access before line? | Yes, gets `undefined`    | **No**, throws **ReferenceError**  |
| Why allowed?        | Old behavior, but unsafe | Modern behavior, safer and cleaner |
| TDZ present?        | No                       | **Yes**, to enforce safe coding    |

---
## scope - block and function scope

1. function scope
2. block scope

#### function scope
A variable has **function scope** if it is accessible **only within the function** it is declared in.
- `var` (only `var` is function-scoped)
```
function test() {
  var x = 10;
  console.log(x); // 10
}

console.log(x); // ❌ Error: x is not defined
```

#### block scope

A variable has **block scope** if it is accessible **only within the nearest pair of curly braces `{}`** it is declared in.
- let
- const

```
{
  let a = 20;
  const b = 30;
  console.log(a); // 20
  console.log(b); // 30
}

console.log(a); // ❌ Error: a is not defined
console.log(b); // ❌ Error: b is not defined
```

### difference

```
if (true) {
  var x = 1;
  let y = 2;
  const z = 3;
}

console.log(x); // ✅ 1 (function scoped)
console.log(y); // ❌ Error (block scoped)
console.log(z); // ❌ Error (block scoped)
```


## var and let difference

``` js
function a(){

    let b=123
    function d(){
        console.log(b);
        let c=12
    }
    d(); // This will log 123
    console.log(c); // This will throw a ReferenceError because c is not defined in this scope
}
a();
```

![|500](/img/user/attachments/Pasted%20image%2020250730123132.png)

![|600](/img/user/attachments/Pasted%20image%2020250730131430.png)

---
## Lexical Scoping

Lexical scoping means that the scope of a variable is determined by its position in the source code at the time the function is defined.

In JavaScript, functions are **lexically scoped**, meaning:

- A function can access variables from its outer scope.
    
- The scope chain is determined at the time of function definition, not at the time of execution.
    

Example:

```js
let a = 10;

function outer() {
    let b = 20;

    function inner() {
        console.log(a); // 10
        console.log(b); // 20
    }

    inner();
}

outer();
```

In the above example, `inner()` has access to both `a` and `b`, even though `a` is outside both `outer()` and `inner()` — because of lexical scoping.

---

## Closure

A closure is created when:

- A function is defined inside another function.
    
- The inner function accesses variables from the outer function even after the outer function has finished executing.
    

Closures allow functions to "remember" the environment in which they were created.

Example:

```js
function outer() {
    let count = 0;

    return function inner() {
        count++;
        console.log(count);
    };
}

const increment = outer();

increment(); // 1
increment(); // 2
increment(); // 3
```

Here, the function `inner()` forms a closure. It keeps access to `count` even after `outer()` has returned. Each time `increment()` is called, it remembers the last value of `count`.

This is useful for maintaining state, data privacy, and function factories.

---
## callbacks

```js
function fth(callbck){
	setTimeout(()=>{
		data="fetched data"
		callbck(data)
	},5000)
}

function handleData(data,error){
	if (error){
		console.log(error)
	}else{
		console.log(data)
	}
}

console.log("statrt")
fth(handleData)
```


----
## callback hell and promises

### What is a callback?

A **callback** is a function passed as an argument to another function, usually to run **after** some operation finishes (like reading a file or making an API call).

Example:

```js
function greet(name, callback) {
    console.log("Hello " + name);
    callback();
}

greet("Sanskar", () => {
    console.log("Welcome!");
});
```

---

### What is Callback Hell?

When multiple asynchronous operations depend on each other and are written using **nested callbacks**, it becomes deeply nested and hard to read or manage. This is called **callback hell**.

Example:

```js
getUser(userId, (user) => {
    getProfile(user, (profile) => {
        getPosts(profile, (posts) => {
            getComments(posts, (comments) => {
                console.log(comments);
            });
        });
    });
});
```

This is:

- Hard to **read**
    
- Hard to **debug**
    
- Hard to **handle errors**
    
- Hard to **maintain**
    

This pattern is also called the "Pyramid of Doom".

---

## How Promises Helped

Promises were introduced in ES6 to **solve callback hell** by:

- Making async code look more linear
    
- Handling errors more cleanly
    
- Flattening nested structures
    

A **promise** represents a value that may be available **now**, **later**, or **never**.

### Basic structure of a promise:

```js
let promise = new Promise((resolve, reject) => {
    // async task
    if (success) {
        resolve(result);
    } else {
        reject(error);
    }
});
```

### Using `.then()` and `.catch()`:

```js
getUser(userId)
.then(user => getProfile(user))
.then(profile => getPosts(profile))
.then(posts => getComments(posts))
.then(comments => console.log(comments))
.catch(err => console.error(err));
```

- Code is **flat**
    
- Easy to **read**
    
- Easy to **handle errors**
    

---

## Summary

|Concept|Description|
|---|---|
|Callback Hell|Nested callbacks that become hard to manage|
|Cause|Sequential async operations using callbacks|
|Problem|Hard to read, debug, scale, or handle errors|
|Promises|Flatten and simplify async logic, better error handling|

---

## Async/Await

`async/await` is **syntactic sugar** introduced in ES2017 (ES8) to write asynchronous code that looks like synchronous code.

It’s built on top of **promises**, but makes code easier to read, write, and debug.

---

### How it works

- `async` keyword is used before a function to turn it into an async function.
    
- `await` is used to pause the function until a promise is resolved.
    
- You can only use `await` inside an `async` function.
    

---

### Example using Promises:

```js
getUser(userId)
.then(user => getProfile(user))
.then(profile => getPosts(profile))
.then(posts => getComments(posts))
.then(comments => console.log(comments))
.catch(err => console.error(err));
```

---

### Same Example using Async/Await:

```js
async function main() {
    try {
        const user = await getUser(userId);
        const profile = await getProfile(user);
        const posts = await getPosts(profile);
        const comments = await getComments(posts);
        console.log(comments);
    } catch (error) {
        console.error(error);
    }
}

main();
```

---

### Benefits of Async/Await

|Feature|Benefit|
|---|---|
|Flat structure|Avoids `.then()` chains|
|Cleaner error handling|Uses `try...catch` block|
|Easier to debug|Stack traces are more readable|
|Looks like sync code|Reduces mental overhead|

---

### Summary

|Technique|Notes|
|---|---|
|Callback|Starts simple but becomes messy quickly|
|Promises|More manageable with `.then()` and `.catch()`|
|Async/Await|Cleanest, best for readability and debugging|
