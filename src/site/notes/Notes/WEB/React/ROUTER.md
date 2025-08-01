---
{"dg-publish":true,"permalink":"/Notes/WEB/React/ROUTER/","created":"2025-02-11T16:25:55.342+05:30"}
---


# Router in React

## APP.JSX
``` js
import { useState } from 'react'
import reactLogo from './assets/react.svg'
import viteLogo from '/vite.svg'
import './App.css'
import { RouterProvider, createBrowserRouter } from 'react-router-dom'
import Home from './components/Home'
import About from './components/About'
import Navbar from './components/Navbar'

function App() {
const router =createBrowserRouter([
  {
    path:"/home",
    element:<div><Navbar/><Home/></div>
  },
  {
    path:"/About",
    element:<div><Navbar/><About/></div>
  },
])
  return (
    <>
    <RouterProvider router={router} />      
    </>
  )
}

export default App

```


## Navbar.jsx
``` js
import React from 'react'
import { NavLink,Link } from 'react-router-dom'
import "./Navbar.css"

function Navbar() {

  return (
    <>
    <div>
    <ul>
        <li>
        <NavLink to="/Home" className={({isActive})=> isActive ? "active-link" : ""}>Homey</NavLink>
        </li>
        <li>
        <NavLink to="/About">About</NavLink>
        </li>
    </ul>
    </div>
    </>
  )
}

export default Navbar
```
# Why we use Navlink 
because it give us a function ` isActive` to use which can be used to set a css if we want to get the active navbar color

## Navbar.jsx
```js
import React from 'react'
import { NavLink,Link } from 'react-router-dom'
import "./Navbar.css"

function Navbar() {

  return (
    <>
    <div>
    <ul>
        <li>
        <NavLink to="/Home" className={({isActive})=> isActive ? "active-link" : ""}>Homey</NavLink>
        </li>
        <li>
        <NavLink to="/About">About</NavLink>
        </li>
    </ul>
    </div>
    </>
  )
}

export default Navbar
```

## Navbar.css
```js
.active-link {
    border: 2px solid red;
}


```

## Output

![](/img/user/Notes/WEB/React/attachments/Pasted image 20250104214433.png)


# useParams

## Main.jsx

```js
const router = createBrowserRouter([
  {
    path:"/",
    element:<Home/>
  },
  {
    path:"/About",
    element:<About/>
  },
  {
    path:"/student/:id",
    element:<Paramsid/>
  }

])
```

## Paramsid.jsx

``` js
import React from 'react'
import { useParams } from 'react-router-dom'

function Paramsid() {
    const {id} = useParams()
  return (
    <div>
        <h1>Paramsid {id}</h1>
    </div>
  )
}

export default Paramsid
```

## output
![](/img/user/Notes/WEB/React/attachments/Pasted image 20250104233332.png)


## Route PARAMETER

`abcd/user/xjkns`

## Key PARAMETER

`abcd/user/id=xjkns`

## Use navigation hook in button to use this with button

![](/img/user/Notes/WEB/React/attachments/Pasted image 20250104233715.png)

## to make herircical routes like /student/courses 

``` js

const router = createBrowserRouter([
  {
    path:"/",
    element:<Home/>
  },
  {
    path:"/About",
    element:<About/>,
    children:[
      {
        path:"courses",
        element:<Courses/>
      }
    ]
  },
  {
    path:"/student/:id",
    element:<Paramsid/>
  }

])
```

### but for giving child routes we need to specify `<outlet/>` in the parent jsx file here:

``` js
import React from 'react'
import { Outlet } from 'react-router-dom'

function About() {
  return (
    <div>
        <h1>this is about page</h1>
        <Outlet/>
    </div>
  )
}

export default About
```

