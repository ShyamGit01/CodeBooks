# Introduction to TypeScript 📘

## Content
1. [What is an Interface?](https://github.com/ShyamGit01/CodeBooks/edit/main/TypeScript/QnA.md#1-what-is-an-interface)


### 1. What is an Interface?
An interface in TypeScript is a way to define the shape of an object. It acts as a contract that enforces a specific structure for an object, ensuring type safety and better code maintainability.

#### Key Features of Interfaces
1. Defines Object Structure - Ensures objects have specific properties with defined types.
2. Optional and Readonly Properties - Properties can be marked as optional (`?`) or readonly (`readonly`).
3. Method Signatures - Defines function signatures within objects.
4. Extensibility - Supports inheritance using `extends`.

#### Example 1 (normal)
```
interface User {
  id: number;
  name: string;
  email?: string; // Optional property
  readonly isAdmin: boolean; // Readonly property
}

const user: User = {
  id: 1,
  name: "John Doe",
  isAdmin: false,
};

user.isAdmin = true; // ❌ Error: Cannot assign to 'isAdmin' because it is a read-only property.
```

#### Example 2 (Extended)
```
interface Person {
  name: string;
  age: number;
}

interface Employee extends Person {
  employeeId: number;
}

const employee: Employee = {
  name: "Bob",
  age: 30,
  employeeId: 101,
};
```
- `Employee` inherits properties from `Person` and adds `employeeId`.

####  Why Use Interfaces?
✅ Type Safety: Prevents errors by enforcing object structure.
✅ Code Readability: Makes it clear what shape an object should have.
✅ Extensibility: Easily extend existing interfaces.
✅ Works with Classes: Interfaces can be implemented by classes.


[move to Content](https://github.com/ShyamGit01/CodeBooks/blob/main/TypeScript/QnA.md#content)
