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