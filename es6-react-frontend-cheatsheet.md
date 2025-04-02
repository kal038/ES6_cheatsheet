# ⚛️ Front-End (React) – ES6+ Cheat Sheet

## ✅ Must-Know ES6+ for React

### 📦 1. `import` / `export`
```js
import React from 'react';
export default function App() { ... }
```

### 📐 2. Arrow Functions + JSX
```js
const Button = ({ label }) => <button>{label}</button>;
```

### 📂 3. Destructuring Props
```js
const UserCard = ({ name, age }) => (
  <div>{name} - {age}</div>
);
```

### 🧬 4. Spread Operator (Props & State)
```js
const newUser = { ...user, age: 30 };
<Component {...props} />
```

### 🔧 5. useState Pattern
```js
const [count, setCount] = useState(0);
```

### 🪝 6. useEffect with Async Logic
```js
useEffect(() => {
  const fetchData = async () => {
    const res = await fetch('/api');
    const data = await res.json();
    setData(data);
  };
  fetchData();
}, []);
```

### 🧰 7. Short-Circuit + Ternary Operators
```js
{isLoading && <Spinner />}
{user ? <Dashboard /> : <Login />}
```

### 📭 8. Optional Chaining for Safe Access
```js
const username = user?.profile?.name ?? 'Guest';
```

### 🧱 9. Functional Component with Default Props
```js
const Welcome = ({ name = "Guest" }) => <p>Hello, {name}</p>;
```

### 🗃️ 10. Array Methods in JSX
```js
<ul>
  {items.map((item) => <li key={item.id}>{item.name}</li>)}
</ul>
```