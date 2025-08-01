---
{"dg-publish":true,"permalink":"/Notes/WEB/React/1 React basics/","created":"2024-12-30T20:40:42.580+05:30"}
---


### React Overview:

**React** is a JavaScript **library** used for building user interfaces, primarily for single-page applications (SPAs). It allows developers to build UI components and manage the state of their app in a declarative and efficient way. React uses a virtual DOM to optimize updates to the actual DOM, resulting in better performance.

---
### What is a Library?
A **library** is a collection of pre-written code that provides specific functionality or utilities that developers can use within their own applications. You can call a library's functions when needed, and it helps you accomplish particular tasks more easily.

- **Example:**  
    **React** itself is a library because you call its functions to create UI components and manage state. You are in control of how and when you use it.

---
### Difference Between Library and Framework:

|Feature|**Library**|**Framework**|
|---|---|---|
|**Control Flow**|You are in control of the flow of the app.|The framework controls the flow of the app.|
|**Usage**|A set of functions you can call when needed.|A full solution that dictates how your app is structured.|
|**Inversion of Control**|You call the library's functions.|The framework calls your code at specific points.|
|**Example**|React, Lodash, jQuery|Angular, Django, Spring|

---
### Difference Between Next.js and React:

|Feature|**React**|**Next.js**|
|---|---|---|
|**Type**|Library for building UIs.|Full-stack framework for React applications.|
|**Routing**|No built-in routing; you must implement it manually (e.g., React Router).|Built-in routing using file-based structure.|
|**Server-Side Rendering (SSR)**|Not built-in; you need to implement SSR manually (e.g., with a custom server).|Built-in support for SSR and static site generation.|
|**Setup**|Requires more setup to handle routing, SSR, etc.|Provides automatic setup for routing, SSR, static generation, etc.|
|**Use Case**|Use for building dynamic UIs in SPAs.|Use for building both static and dynamic pages with React.|
|**Example**|React can be used in SPAs (Single Page Apps).|Next.js is used for both SPAs and static sites, with enhanced features like SSR.|

---
### Similarities Between React and Next.js:

1. **React-based:** Both use React for building user interfaces, meaning React components, hooks, and JSX are used in both.
2. **Component-Based Architecture:** Both follow a component-based architecture, making it easy to break down the UI into reusable components.
3. **JavaScript/TypeScript Support:** Both support JavaScript and TypeScript for writing components and application logic.
4. **UI Rendering:** Both React and Next.js can render dynamic UI components based on state and props.

### Summary:

- **React** is a library for building UIs and requires additional tools or setup for routing and SSR.
- **Next.js** is a full-stack framework built on React that provides built-in features like server-side rendering, static site generation, and routing, making it easier to build complex React applications.

---
## React life cycle
The **React lifecycle** refers to the series of phases a React component goes through during its existence. Each component's lifecycle has specific methods or hooks that React invokes at particular stages, enabling developers to add functionality at key points.
### **Lifecycle Phases**

1. **Mounting**: When a component is created and added to the DOM.
2. **Updating**: When a component's state or props change, triggering a re-render.
3. **Unmounting**: When a component is removed from the DOM.
4. **Error Handling**: When an error occurs in the rendering or lifecycle methods.

---
## What does package.json contain

1. name of project
2. version
3. dependencies -> testing libs, react, react-dom, react-scripts
4. scripts {
	   "start": "react-scripts start"
	   "build": "react-scripts build"
	   "test": "react-scripts test"
	   }
5. browserlist -> where the app works like last 1 chrome version or last 1 firefox version

> [!NOTE]
> when we create app using 
> `create react app` it gets localhost:3000
> but when we do it using vite
> `create vite@latest` it gets localhost:5173
> 

---
## what is vite why we use it ?
We use **Vite** for making React projects because it provides a faster and smoother development experience compared to traditional tools like **Create React App (CRA)**. Here's why:
1. **Fast Startup:** Vite uses ES modules and a lightweight dev server, allowing your React app to start almost instantly, even for large projects.
    
2. **Hot Module Replacement (HMR):** Changes in your React code are updated in the browser instantly without a full reload, making development faster and more productive.

---
## What is the difference between js and jsx ?
### JSX:
- **Full Form:** JavaScript XML.
- **Purpose:** Used in React to write HTML-like syntax directly in JavaScript files.
- **Syntax:** Looks similar to HTML but gets transpiled to JavaScript using tools like Babel.
- **Example:**
    
    ```jsx
    const element = <h1>Hello, World!</h1>;
    ```
    
- **Usage:** JSX allows embedding HTML with JavaScript logic, making it easier to create React components.

### JS:
- **Full Form:** JavaScript.
- **Purpose:** General-purpose programming language used for building logic, interactivity, and applications.
- **Syntax:** Pure JavaScript without any embedded HTML.
- **Example:**
    
    ```js
    const message = "Hello, World!";
    console.log(message);
    ```
    
- **Usage:** Used for implementing logic, algorithms, and backend/frontend functionality.

### Key Difference:

- JSX is **syntactic sugar** for React `createElement()` calls, enabling HTML-like readability in JavaScript.
- JS is the core programming language JSX is built on.

---
## so when we create react app using cra we get app.js and main.js but in vite we get app.jsx and main.jsx why ?

The difference in file extensions (`.js` vs. `.jsx`) when creating a React app using **CRA** and **Vite** is based on conventions and how the tools handle JSX files.
### Why CRA uses `.js`:

- **Simpler Convention:** CRA assumes `.js` files can contain JSX by default, as Babel (used under the hood) transpiles JSX regardless of the file extension.
- **Ease of Use:** By using `.js`, developers don’t need to worry about different extensions, simplifying the setup for beginners.

### Why Vite uses `.jsx`:

- **Explicitness:** Vite uses `.jsx` for files containing JSX to explicitly indicate they include React or JSX syntax.
- **Readability:** It helps differentiate between regular JavaScript files and those using JSX.
- **Customization:** Vite prioritizes modern standards and flexibility, and `.jsx` is a widely accepted convention in advanced setups.

### Bottom Line:

Both work the same because JSX is transpiled to JavaScript in both CRA and Vite. The file extension choice is just a convention—CRA opts for simplicity with `.js`, while Vite emphasizes clarity with `.jsx`.

---

## What is use of packagelock.json ?
### Definition:
`package-lock.json` ensures all developers working on a project use the exact same versions of dependencies, preventing unexpected issues caused by version mismatches.
### Example Scenario:
1. You run `npm install react@^17.0.0`.
    - The latest compatible version, `react@17.0.1`, is installed and recorded in `package-lock.json`.
2. You share the project with a friend.
    - Without `package-lock.json`: Your friend runs `npm install` and might get `react@17.0.2` if it was released in the meantime, causing potential bugs or differences in behavior.
    - With `package-lock.json`: Your friend gets the same `react@17.0.1`, ensuring consistency and avoiding version-related issues.


## Explain working of react with the DOM. How it changes the webpage data without reloading the whole webpage?

so in react we use the concept of dom (document object model) It represents the structure of an HTML document as a tree of objects
where each component is object of a tree where when we build a react app the react compares the reactdom with the browser dom and changes only the required particular parts of the web page without reloading the webpage
In React we have react dom and we have only one html div which is `root`
![](/img/user/Notes/WEB/React/attachments/Pasted image 20241231134702.png)

there are 2 main files in react one is app.jsx and main.jsx we write all the code in app.jsx which is inside function App() where is return and render all the html 
![](/img/user/Notes/WEB/React/attachments/Pasted image 20241231134811.png)

But the App function  is nothing but the dom the div which is called by react which contains the root div which is in the main.jsx
![](/img/user/Notes/WEB/React/attachments/Pasted image 20241231135104.png)

**ReactDOM** is a library in React that bridges React components with the actual DOM. It provides methods to render React elements into the DOM and manage updates efficiently.


## What is strict Mode in react ?

**React Strict Mode** is a development tool in React that helps you identify potential problems in your application. It doesn't affect the behavior of your app in production but provides warnings and additional checks during development to ensure better coding practices.
### Key Features:

1. **Identifies Unsafe Lifecycles:** Warns about deprecated or unsafe lifecycle methods.
2. **Highlights Side Effects:** Helps detect unexpected side effects in components.
3. **Warns About Legacy API Usage:** Alerts you when using outdated React APIs.
4. **Ensures Strict Rendering:** Triggers additional re-renders in development to identify rendering issues.
### How to Use It:

Wrap your component tree with `<React.StrictMode>` in `index.js`:

```javascript
import React from "react";
import ReactDOM from "react-dom";
import App from "./App";

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById("root")
);
```


## Why we write all the html or logic in app.jsx and not in main.jsx ?
 We can write the html or the return <> </ > in the main.jsx but it wouldnt be considered as best practices of react of keeping the code modular, maintainable, and organized.
 In React the main.jsx is considered as the entry point of the dom in html
See the main.jsx file 
![](/img/user/Notes/WEB/React/attachments/Pasted image 20241231140202.png)
 it just calls the dom `root` and renders the <App/> function we wrote in app.jsx 
 now see the index.html
 ![](/img/user/Notes/WEB/React/attachments/Pasted image 20241231140305.png)
 Here the < script > tag is calling the main.jsx to render the components and not the app.jsx 
 Its just the best practice to keep the dom entry point and the html return code different we can call the app.jsx in here to by calling the dom in the app.jsx 
 `createRoot(document.getElementById('root')).render`
 it works fine but make code cluttered

> [!Best Practices]
> Write the funtion name in capital letters in react , it is considered as best practices

==<> </> this is called as fragment which is use to wrap all the html elements inside one element because react allows only one html element to return . This works like div which contains all other html element inside one single div element==


## Why does the function `changeMarks` run immediately when called with parentheses `changeMarks()` but only run on click when passed without parentheses in the `onClick` event handler like `<button onClick={changeMarks}>`?

When you use `changeMarks()` with parentheses, the function runs immediately during render. Without parentheses, as in `<button onClick={changeMarks}>`, you're passing a reference to the function, which gets called only when the button is clicked.
### Example:

```jsx
// Correct way to attach the function to an onClick event:
<button onClick={changeMarks}>Change Marks</button>
```

- **Here**: `changeMarks` is passed as a function reference and will be invoked only when the button is clicked.

```jsx
// This immediately runs the function when the component renders
<button onClick={changeMarks()}>Change Marks</button>
```

- **Here**: `changeMarks()` is immediately invoked during render, and the result of that function call (if any) is passed as the `onClick` handler, rather than the function itself.

### for calling a function in button you can do it in 2 ways

#### 1
```
import react from "react"
import {useState} from "react"

function App(){
  const[count,setcount]=useState(0);
  const upd=()=>{
    setcount(count+1)
  }
  return(
    <> 
    <h1> this is sanskar</h1>
    <h1>{count}</h1>
    <button onClick={()=>{upd()}}>click</button>
    </>
  )
}

export default App
```

#### 2
```
import react from "react"
import {useState} from "react"

function App(){
  const[count,setcount]=useState(0);
  const upd=()=>{
    setcount(count+1)
  }
  return(
    <> 
    <h1> this is sanskar</h1>
    <h1>{count}</h1>
    <button onClick={upd>click</button>
    </>
  )
}

export default App
```

---
## What is react fibre ? 
Note:- Earlier react used to use the concept of virtual dom but now it uses fibre
### React Fiber (Simplified)

React Fiber is like an upgrade to React's "brain" (reconciliation algorithm), making React smarter and faster. It helps React efficiently update the screen, especially for big apps or apps with animations and user interactions
### Why React Fiber?

Imagine React is a chef cooking a big meal.

- Before Fiber: The chef (React) finishes cooking one dish (component tree) before starting the next. If the meal is huge, it takes a long time.
- With Fiber: The chef can take a break, check on other dishes (tasks), and return to finish the current dish later. This makes cooking (updating the UI) smoother and faster.
### Key Features:

1. **Prioritized Updates**: React focuses on what's important first (e.g., user clicks or typing).  
    _Example:_ A button click updates instantly, while a background animation might wait.
    
2. **Asynchronous Rendering**: React can pause rendering and continue later if needed.  
    _Example:_ Rendering a long list of items happens in chunks instead of freezing the page.
    
3. **Concurrency**: React can juggle multiple tasks, like animations and data fetching, without slowing down.  
    _Example:_ Smooth scrolling while a network request loads data.
### Example:
#### Without Fiber (Old Way):
If React needs to update a long list (e.g., 10,000 items), the screen might freeze because React processes everything in one go.
#### With Fiber:
React breaks the list into smaller parts and updates them one by one. This prevents the screen from freezing and makes it feel smooth.
### Summary:

React Fiber makes React apps faster and smoother by prioritizing tasks, pausing updates when needed, and handling multiple tasks efficiently. It’s why React feels modern and responsive today.


---
## Problem 1 : change background color using the button for each button there should be different color

solution

``` js
import react from "react"
import {useState} from "react"

function App(){
  const [color,setcolor]=useState("red")
  const changeclr=(e)=>{
    setcolor(e)
  }
  return(
    <>
    <div className=" w-full h-screen" style={{backgroundColor:color}}>
    <button onClick={()=>{changeclr("yellow")}}>Red</button>
    {/* <button onClick={changeclr("yellow")}>Yellow</button>
    <button onClick={changeclr("green")}>Green</button>
    <button onClick={changeclr("blue")}>Blue</button> */}
    </div>
    </>
  )
}

export default App
```


---
# Password Generator

``` js
import react from "react"
import {useState, useCallback,useEffect} from "react"

function App(){
  const [length,setlength]= useState(8)
  const [numallowed,setnumallowed]= useState(false)
  const [charallowed,setcharallowed]= useState(false)
  const[password,setpassword]=useState("")

  const passgen =useCallback(()=>{
    let str="ABCDEFGHIJKLMNOPQRSTUVWXYZabcedfghijklmnopqrstuvwxyz"
    let pass=""
    if(numallowed){
      str+="1234567890"
    }
    if(charallowed){
      str+="!@#$%"
    }
    for(let i=0;i<=length;i++){
      let a=Math.floor(Math.random()*str.length+1)
      pass+=str.charAt(a)
    }
    setpassword(pass)
  },[length,numallowed,charallowed,setpassword])


  useEffect(()=>{
    passgen()
  },[length,numallowed,charallowed,setpassword])


  return(
    <>
    <h1>Password gen</h1>
    <input type="text" value={password} placeholder="password" readOnly></input>
    <button onClick={()=>(passgen)}>Generate password</button>

    <label>lenght:{length}</label>
    <input type="range" min={8} max={25} onChange={(e)=>{setlength(e.target.value)}} value={length}></input>

    <label>NUMBER</label>
    <input type="checkbox" onChange={()=>{setnumallowed((prev)=>!prev)}}></input>

    <label>CHARACTER</label>
    <input type="checkbox" onChange={()=>{setcharallowed((prev)=>!prev)}}></input>      
    </>
  )
}

export default App
```

---
# TIMER IN REACT

```js
function App() {
  const [count,setcount]= useState(0)
  useEffect(()=>{
    const intervalid=setInterval(()=>{
      setcount(prevcount=>prevcount+1)
    },1000)

    return ()=>{
      clearInterval(intervalid)
    }
  },[])

  return (
    <>
      <h1>Hi</h1>
      <h1>{count}</h1>
      <button>ADD</button>
    </>
  )
}

export default App
```


---
