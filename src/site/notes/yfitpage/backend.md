---
{"dg-publish":true,"permalink":"/yfitpage/backend/","created":"2025-08-01T05:43:28.358+05:30"}
---


## 1. **Node.js Basics**

### What is Node.js?

- Node.js is a **runtime environment** that allows JavaScript to run outside the browser.
    
- Built on Chrome's V8 engine.
    
- Used for **backend development**, real-time applications, APIs, etc.
    

### Key Features

- Non-blocking, event-driven architecture.
    
- Uses **single-threaded event loop**.
    
- Fast and scalable.
    

---

## 2. **Modules in Node.js**

### Types of Modules

- **Built-in modules**: `fs`, `http`, `path`, `url`, `crypto`, etc.
    
- **Custom modules**: Your own files (e.g., `require('./myModule')`).
    
- **Third-party modules**: Installed using NPM (e.g., `express`, `mongoose`, etc.).
    

### Module Systems

- **CommonJS (CJS)**
    
    - Used by default in Node.js.
        
    - `require()` and `module.exports`
        
- **ES Modules (ESM)**
    
    - Modern JavaScript module system.
        
    - Use `import` and `export`
        
    - Requires `"type": "module"` in `package.json`
        

---

## 3. **NPM (Node Package Manager)**

### Commands

- `npm init` / `npm init -y`: Initialize project.
    
- `npm install <package>`: Install a package.
    
- `npm install --save-dev <package>`: Dev dependency.
    
- `npm uninstall <package>`: Remove a package.
    

`package.json` file manages dependencies and project metadata.

---

## 4. **Express.js**

### What is Express?

- A **minimal and flexible** Node.js web application framework.
    
- Simplifies routing, middleware, request/response handling.
    

### Basic Setup

```js
const express = require('express');
const app = express();
const PORT = 3000;

app.listen(PORT, () => console.log(`Server running on port ${PORT}`));
```

---

## 5. **Basic API Structure (CRUD)**

```js
const express = require('express');
const app = express();

app.use(express.json()); // middleware to parse JSON

// CREATE
app.post('/items', (req, res) => {
  const item = req.body;
  // logic to save item
  res.status(201).send('Item created');
});

// READ
app.get('/items', (req, res) => {
  res.send(['item1', 'item2']);
});

// UPDATE
app.put('/items/:id', (req, res) => {
  const id = req.params.id;
  res.send(`Item ${id} updated`);
});

// DELETE
app.delete('/items/:id', (req, res) => {
  const id = req.params.id;
  res.send(`Item ${id} deleted`);
});

app.listen(3000);
```

---

## 6. **Middleware in Express**

### What is Middleware?

- Functions that run between request and response.
    
- Can modify `req` and `res` objects.
    
- Can end the request-response cycle or pass to next middleware.
    

### Types

- **Application-level middleware**: `app.use()` or route-specific.
    
- **Router-level middleware**: `router.use()`
    
- **Built-in middleware**: `express.json()`, `express.static()`
    
- **Error-handling middleware**: Takes 4 args `(err, req, res, next)`
    

### Example

```js
app.use((req, res, next) => {
  console.log('Time:', Date.now());
  next();
});
```

---

## 7. **Routing in Express**

```js
app.get('/', (req, res) => {
  res.send('Home');
});

app.get('/about', (req, res) => {
  res.send('About Page');
});
```

You can also use `express.Router()` for modular routes.

---

## 8. **Error Handling**

### Simple error handler middleware

```js
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).send('Something broke!');
});
```

---

## 9. **Environment Variables**

### Use `.env` file

Install `dotenv`

```bash
npm install dotenv
```

In your entry file:

```js
require('dotenv').config();
const PORT = process.env.PORT;
```

---

## 10. **Project Structure (Basic)**

```
project/
|-- node_modules/
|-- routes/
|   |-- itemRoutes.js
|-- controllers/
|   |-- itemController.js
|-- models/
|   |-- itemModel.js
|-- .env
|-- index.js
|-- package.json
```

---

This structure is clean and modular, good for scaling.

---

## 11. **Important Middlewares/Libraries to Know**

- `body-parser` (mostly replaced by `express.json()`)
    
- `cors` – handle cross-origin requests
    
- `helmet` – security headers
    
- `morgan` – logging HTTP requests
    
- `express-validator` – input validation
    
- `jsonwebtoken` – JWT token handling for auth
    

---

## 12. **Extra Concepts to Revise**

- RESTful API design
    
- HTTP methods: GET, POST, PUT, PATCH, DELETE
    
- HTTP status codes: 200, 201, 400, 401, 403, 404, 500
    
- Authentication: Sessions vs JWT
    
- Rate limiting and basic security
    
- Asynchronous operations (async/await, Promises)
    
- Connecting with MongoDB or SQL
    

---

End of One-Shot Notes.