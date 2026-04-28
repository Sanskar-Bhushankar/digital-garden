---
{"dg-publish":true,"permalink":"/dump/yfitpage/redux/","dgPassFrontmatter":true,"dg-note-properties":{}}
---




## 🔹 What is Redux?

**Redux** is a state management library used with React.  
It helps manage and share **global state** across components.

> Think of Redux like a central store (or memory) where your app keeps data that needs to be used in many places.

---

## 🔹 Why use Redux?

- To avoid **prop drilling** (passing data through many levels).
    
- To share data globally (e.g., user info, cart items, theme).
    
- Works well when app state gets **complex** or **shared across components**.
    

---

## 🔹 Redux vs useState / useContext

|Feature|useState / useContext|Redux|
|---|---|---|
|Simpler apps|Good for small apps|Overkill for small apps|
|Global state|useContext does this|Built for global state|
|Debugging|Limited|Redux DevTools helps a lot|
|Structure|No strict structure|Structured using slices/store|

---

## 🔹 Redux Toolkit (RTK)

**Redux Toolkit** is the official, modern way to write Redux.  
It reduces boilerplate code and provides better patterns.

We mainly use 3 things from it:

1. `configureStore()` – to create a Redux store.
    
2. `createSlice()` – to create a slice of state + reducers.
    
3. `createAsyncThunk()` – to handle API calls (async logic).
    

---

## 🔹 What is a Slice?

A **slice** is:

- A part of the global state (e.g., user, products, cart).
    
- It contains:
    
    - Initial state
        
    - Reducers (functions to update state)
        
    - Action creators
        

✅ Created using `createSlice()`  
Example:

```js
// features/user/userSlice.js
import { createSlice } from '@reduxjs/toolkit';

const initialState = {
  user: null,
  isAuthenticated: false
};

const userSlice = createSlice({
  name: 'user',
  initialState,
  reducers: {
    loginSuccess: (state, action) => {
      state.user = action.payload;
      state.isAuthenticated = true;
    },
    logout: (state) => {
      state.user = null;
      state.isAuthenticated = false;
    }
  }
});

export const { loginSuccess, logout } = userSlice.actions;
export default userSlice.reducer;
```

---

## 🔹 Setting Up Redux (step-by-step)

### 1. Install Redux Toolkit and React Redux

```bash
npm install @reduxjs/toolkit react-redux
```

---

### 2. Create the Slice

Example: `userSlice.js` (see above)

---

### 3. Create the Store

```js
// app/store.js
import { configureStore } from '@reduxjs/toolkit';
import userReducer from '../features/user/userSlice';

export const store = configureStore({
  reducer: {
    user: userReducer
  }
});
```

---

### 4. Wrap App with `<Provider>`

```js
// index.js
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';
import { Provider } from 'react-redux';
import { store } from './app/store';

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById('root')
);
```

---

### 5. Use Redux in Components

#### Access state → `useSelector`

#### Update state → `useDispatch`

```js
import { useSelector, useDispatch } from 'react-redux';
import { loginSuccess, logout } from '../features/user/userSlice';

const LoginComponent = () => {
  const dispatch = useDispatch();
  const user = useSelector((state) => state.user.user);
  const isAuth = useSelector((state) => state.user.isAuthenticated);

  const handleLogin = () => {
    const fakeUser = { name: 'John', email: 'john@example.com' };
    dispatch(loginSuccess(fakeUser));
  };

  return (
    <div>
      {isAuth ? <p>Welcome {user.name}</p> : <p>Please log in</p>}
      <button onClick={handleLogin}>Login</button>
    </div>
  );
};
```

---

## 🔹 Redux for Login/Signup

Use Redux when:

- You want to keep user login info across the whole app.
    
- You want to access it from many components (like Navbar, Dashboard).
    
- You want the UI to react to login/logout status.
    

### What to store in Redux:

✅ User data (name, email, token)  
✅ isAuthenticated (true/false)  
❌ Never store password in Redux

---

### Example Login Flow with Redux:

1. User submits login form
    
2. Send API request (use `createAsyncThunk`)
    
3. On success → dispatch `loginSuccess(userData)`
    
4. Redux updates state → components reflect changes (like showing user profile)
    

---

## 🔹 When NOT to use Redux

- App is very small and local state is enough.
    
- You’re just managing a single component’s state.
    
- useContext + useReducer can also do the job for simpler global needs.
    

---

## 🔹 Summary Notes

|Concept|Description|
|---|---|
|Redux|Global state manager for React apps|
|Redux Toolkit|Modern, simpler way to use Redux|
|Slice|A section of Redux state + actions|
|Store|The complete Redux state container|
|useSelector|Read data from Redux|
|useDispatch|Send actions to Redux|
|Login Example|Save user + isAuth in userSlice|
|Good For|Auth, Cart, Dashboard, Filters, Settings|

---

Here’s a simple **Counter App** example using **React + Redux Toolkit**. This will help you understand how Redux works end-to-end with actions, reducers, and state.

---

## 🔹 App Flow (in simple terms)

- You have a counter value stored in Redux state.
    
- Two buttons: Increase and Decrease.
    
- When buttons are clicked, Redux updates the state and UI reacts.
    

---

## ✅ Step-by-Step Counter Example

### 1. Install Redux Toolkit and React-Redux

```bash
npm install @reduxjs/toolkit react-redux
```

---

### 2. Create a **slice** for the counter

```js
// src/features/counter/counterSlice.js

import { createSlice } from '@reduxjs/toolkit';

const initialState = {
  value: 0
};

const counterSlice = createSlice({
  name: 'counter',
  initialState,
  reducers: {
    increment: (state) => {
      state.value += 1;
    },
    decrement: (state) => {
      state.value -= 1;
    },
    reset: (state) => {
      state.value = 0;
    }
  }
});

export const { increment, decrement, reset } = counterSlice.actions;
export default counterSlice.reducer;
```

---

### 3. Create the **Redux store**

```js
// src/app/store.js

import { configureStore } from '@reduxjs/toolkit';
import counterReducer from '../features/counter/counterSlice';

export const store = configureStore({
  reducer: {
    counter: counterReducer
  }
});
```

---

### 4. Wrap your app with Redux `<Provider>`

```js
// src/main.jsx (or index.js)

import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';
import { Provider } from 'react-redux';
import { store } from './app/store';

ReactDOM.createRoot(document.getElementById('root')).render(
  <Provider store={store}>
    <App />
  </Provider>
);
```

---

### 5. Create the **Counter component**

```js
// src/components/Counter.jsx

import React from 'react';
import { useSelector, useDispatch } from 'react-redux';
import { increment, decrement, reset } from '../features/counter/counterSlice';

const Counter = () => {
  const count = useSelector((state) => state.counter.value);
  const dispatch = useDispatch();

  return (
    <div>
      <h1>Counter: {count}</h1>
      <button onClick={() => dispatch(increment())}>+ Increment</button>
      <button onClick={() => dispatch(decrement())}>- Decrement</button>
      <button onClick={() => dispatch(reset())}>Reset</button>
    </div>
  );
};

export default Counter;
```

---

### 6. Use the Counter in your App

```js
// src/App.jsx

import React from 'react';
import Counter from './components/Counter';

function App() {
  return (
    <div>
      <h2>Redux Counter Example</h2>
      <Counter />
    </div>
  );
}

export default App;
```

---

## 🔹 Summary

- `counterSlice` contains the state (`value`) and actions (`increment`, `decrement`, `reset`)
    
- `store.js` combines slices (even though we only have one now)
    
- `Counter` component uses `useSelector` to read and `useDispatch` to update state
    

---

Let me know if you want the same example but using async (e.g., delay counter using `createAsyncThunk`).