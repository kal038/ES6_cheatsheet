# 🖥️ Back-End (Node.js) – ES6+ Cheat Sheet

## 🛠️ Must-Know ES6+ for Back-End (Node.js, Express)

### 📦 1. Modules with ES6 Syntax (in ESM or transpiled)
```js
import express from 'express';
export const handler = () => { ... };
```

### 🧱 2. Async/Await for I/O
```js
app.get('/user', async (req, res) => {
  try {
    const user = await db.findUser(req.params.id);
    res.json(user);
  } catch (err) {
    res.status(500).send('Error');
  }
});
```

### 🧾 3. Destructuring Request
```js
const { id } = req.params;
const { name, email } = req.body;
```

### 📂 4. Object Spread for DB Updates
```js
const updated = { ...user, isActive: true };
```

### 🧪 5. Default Params in Routes or Helpers
```js
function getUser(id = 0) { ... }
```

### 🔒 6. Optional Chaining for Configs or Env Vars
```js
const port = process.env?.PORT ?? 3000;
```

### 💼 7. Classes (For Services / Error Handling)
```js
class AppError extends Error {
  constructor(message, statusCode) {
    super(message);
    this.statusCode = statusCode;
  }
}
```

### 📇 8. Arrow Functions to Preserve `this` in Classes
```js
class Service {
  fetch = async () => { ... }; // arrow keeps `this`
}
```

### 🌐 9. JSON Responses with Template Literals
```js
res.json({ msg: `User ${user.name} created.` });
```

### 🔁 10. Common Array/Obj Methods for Data Parsing
```js
users.filter(u => u.isActive).map(u => u.email);
Object.entries(obj).forEach(([key, val]) => ...);
```