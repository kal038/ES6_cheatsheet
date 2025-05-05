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
# 🧠 TypeScript Generics & Utility Types Cheat Sheet

## 🔷 Basic Generics

### `Array<T>`
```ts
const nums: Array<number> = [1, 2, 3]; // same as number[]
```

### `Promise<T>`
```ts
const fetchUser = (): Promise<User> => { ... };
```

### `Set<T>` / `Map<K, V>`
```ts
const tags: Set<string> = new Set(["react", "ts"]);
const userMap: Map<string, User> = new Map();
```

---

## 🛠️ Utility Types (Built-in)

### `Partial<T>`
> Makes all properties in T optional.
```ts
type User = { name: string; age: number };
type UserDraft = Partial<User>; // { name?: string; age?: number }
```

### `Required<T>`
> Opposite of `Partial` — makes all properties required.
```ts
type User = { name?: string; age?: number };
type StrictUser = Required<User>;
```

### `Pick<T, K>`
> Create a type with only selected properties.
```ts
type User = { id: number; name: string; email: string };
type PublicUser = Pick<User, 'id' | 'name'>;
```

### `Omit<T, K>`
> Create a type by omitting specific properties.
```ts
type User = { id: number; name: string; email: string };
type NoEmail = Omit<User, 'email'>;
```

### `Record<K, T>`
> Create a type with specific keys of type `K` and values of type `T`.
```ts
type ErrorMessages = Record<'404' | '500', string>;
```

### `Readonly<T>`
> Makes all properties of type `T` immutable.
```ts
type Config = Readonly<{ port: number; env: string }>;
```

### `ReturnType<T>`
> Get the return type of a function.
```ts
function getUser() { return { id: 1, name: 'Khoi' }; }
type User = ReturnType<typeof getUser>;
```

### `Parameters<T>`
> Extract the parameter types of a function as a tuple.
```ts
function log(msg: string, level: number): void { ... }
type LogParams = Parameters<typeof log>; // [string, number]
```

---

## ✨ Custom Generic Example

```ts
function identity<T>(arg: T): T {
  return arg;
}

const str = identity<string>("hello"); // "hello"
const num = identity<number>(42);      // 42
```

---

## 🧠 TL;DR

| Utility Type    | What it does                          |
|-----------------|----------------------------------------|
| `Partial<T>`    | All fields optional                    |
| `Required<T>`   | All fields required                    |
| `Pick<T, K>`    | Select subset of fields                |
| `Omit<T, K>`    | Remove specific fields                 |
| `Record<K, V>`  | Object with typed keys & values        |
| `Readonly<T>`   | Immutable object                       |
| `ReturnType<T>` | Infer function return type             |
| `Parameters<T>` | Infer function parameters as tuple     |
