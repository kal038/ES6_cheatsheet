# 🧠 JavaScript ES6+ Cheat Sheet

## 🟢 1. `let` and `const`
```js
let counter = 0; // reassignable
const name = 'Khoi'; // cannot be reassigned
```

## ⚡ 2. Arrow Functions
```js
const add = (a, b) => a + b;
const greet = () => console.log('Hello!');
```

## 🎁 3. Destructuring
```js
const user = { name: 'Khoi', age: 25 };
const { name, age } = user;

const [first, second] = [10, 20];
```

## 🧬 4. Spread & Rest
```js
// Spread
const arr1 = [1, 2];
const arr2 = [...arr1, 3]; // [1, 2, 3]

// Rest
function sum(...nums) {
  return nums.reduce((a, b) => a + b, 0);
}
```

## 📝 5. Template Literals
```js
const greeting = `Hello, ${name}! You are ${age} years old.`;
```

## ⚙️ 6. Default Parameters
```js
function greet(name = 'Stranger') {
  console.log(`Hello, ${name}`);
}
```

## 📦 7. Enhanced Object Literals
```js
const age = 25;
const user = {
  name: 'Khoi',
  age,
  greet() {
    console.log('Hi!');
  }
};
```

## 🧱 8. Classes & Inheritance
```js
class Animal {
  constructor(name) {
    this.name = name;
  }
  speak() {
    console.log(`${this.name} makes a noise`);
  }
}

class Dog extends Animal {
  speak() {
    console.log(`${this.name} barks`);
  }
}
```

## 📤 9. Modules
```js
// math.js
export const add = (a, b) => a + b;

// app.js
import { add } from './math.js';
```

## ⏳ 10. Promises + Async/Await
```js
const fetchData = async () => {
  try {
    const res = await fetch('/api/data');
    const data = await res.json();
    console.log(data);
  } catch (err) {
    console.error(err);
  }
};
```

## ✨ Bonus: Optional Chaining & Nullish Coalescing
```js
const user = { profile: { name: 'Khoi' } };
const username = user?.profile?.name ?? 'Guest';
```

## 🛠️ Common Array Methods
```js
arr.map(fn)
arr.filter(fn)
arr.reduce(fn, initial)
arr.find(fn)
arr.some(fn)
arr.every(fn)
```