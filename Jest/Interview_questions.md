### 🔹 Jest (JavaScript Testing Framework)

#### 📘 Common Interview Questions

1. What is Jest? Why is it used?
   - Jest is a JavaScript testing framework developed by Facebook, primarily used for testing React applications but works with any JS project.

2. How does Jest differ from other test frameworks like Mocha or Jasmine?
   - Jest comes with built-in assertions, test runners, mocks, and spies. Mocha requires integrating external libraries.

3. What are `describe`, `test`, and `it` in Jest?
   - `describe` groups related tests, `test` and `it` define individual test cases (they are interchangeable).

4. What is snapshot testing in Jest?
   - It compares the rendered output of a component with a previously saved snapshot. If it changes unexpectedly, the test fails.

5. How does mocking work in Jest?
   - Jest provides functions like `jest.fn()`, `jest.mock()`, and `jest.spyOn()` to mock modules, functions, or objects.

6. How do you mock a module in Jest?
   ```
   jest.mock('./api', () => ({
     fetchData: jest.fn(() => Promise.resolve({ data: 'mocked' }))
   }));
   ```
7. What is the difference between `beforeEach`, `afterEach`, `beforeAll`, and `afterAll`?
   - `beforeEach`/`afterEach`: Run before/after each test in a block.
   - `beforeAll`/`afterAll`: Run once before/after all tests in a block.

8. How can you run only a specific test in Jest?
  ```
  test.only('runs this test', () => { ... });
  ```
9. How do you test asynchronous code in Jest?
  - Using `async/await`, returning promises, or using done() callback.
    
10. How to set up code coverage in Jest?
    Run: `jest --coverage`
        Or
    configure in `jest.config.js`: `{ collectCoverage: true }`

11. How to test if a function throws an error?
  ```
function throwErr() { throw new Error('fail'); }

test('throws error', () => {
  expect(() => throwErr()).toThrow('fail');
});

  ```
12. Jest Lifecycle Methods
```
beforeAll(() => {});
beforeEach(() => {});
afterEach(() => {});
afterAll(() => {});
```
13. How to test React components with Testing Library and Jest?
```
import { render, screen } from '@testing-library/react';
test('renders button', () => {
  render(<Button />);
  expect(screen.getByText(/click/i)).toBeInTheDocument();
});
```
14. Hooks in jest
  In Jest, hooks are special functions used to set up and tear down conditions before and after tests run. They help manage test lifecycle logic and ensure consistency across your test suites.
- Hooks in Jest
  
| Hook             | Description                                             |
| ---------------- | ------------------------------------------------------- |
| `beforeAll(fn)`  | Runs once **before all tests** in the test suite.       |
| `afterAll(fn)`   | Runs once **after all tests** in the test suite.        |
| `beforeEach(fn)` | Runs **before each individual test** in the test suite. |
| `afterEach(fn)`  | Runs **after each individual test** in the test suite.  |

- When to Use
  - beforeAll / afterAll: Expensive operations like DB connections or server startup.
  - beforeEach / afterEach: Resetting mocks, clearing local variables, resetting database records, etc.









# 📘 Jest Key Terms and Concepts

This document lists essential terminology you should be familiar with when working with Jest.

---

## ✅ Core Concepts

| Term             | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Test Suite**   | A group of related tests, usually grouped with `describe()`.                |
| **Test Case**    | A single unit of test defined using `test()` or `it()`.                     |
| **Assertion**    | A statement that checks if a condition is true using `expect()` matchers.   |
| **Mock**         | A fake function or module used to isolate unit tests from dependencies.     |
| **Spy**          | A mock that tracks how a function is called (e.g., `jest.spyOn`).           |
| **Snapshot**     | A saved version of a rendered component or output for regression testing.   |
| **Coverage**     | Measurement of how much of your code is executed by tests.                  |
| **Matcher**      | Methods used with `expect()`, like `.toBe()`, `.toEqual()`, etc.            |
| **Hook**         | Setup/teardown functions like `beforeEach()`, `afterAll()` etc.             |
| **Watch Mode**   | Jest's mode for running tests automatically when files change.              |

---

## 🔸 Mocking Terminology

| Term                       | Description                                                   |
|----------------------------|---------------------------------------------------------------|
| `jest.fn()`                | Creates a mock function.                                      |
| `jest.mock()`              | Automatically mocks a module.                                 |
| `jest.spyOn()`             | Tracks calls to an existing method (partial mocking).         |
| `mockReturnValue()`        | Sets the return value for a mock function.                    |
| `mockResolvedValue()`      | Sets the resolved value for a mocked promise.                 |
| **Manual Mocks**           | Custom mocks created inside a `__mocks__` directory.          |

---

## 🧪 Test Result Terms

| Term       | Meaning                                                      |
|------------|--------------------------------------------------------------|
| **PASS**   | Test case passed.                                            |
| **FAIL**   | Test case failed.                                            |
| **SKIP**   | Test is skipped using `test.skip()`.                         |
| **ONLY**   | Only this test runs using `test.only()`.                     |
| **TODO**   | Placeholder for a future test using `test.todo()`.           |

---

## 📊 Code Coverage Terms

| Metric       | Description                                              |
|--------------|----------------------------------------------------------|
| **Statements** | % of code statements executed.                         |
| **Branches**   | % of conditional branches covered.                     |
| **Functions**  | % of functions executed.                               |
| **Lines**      | % of lines of code executed.                           |

---

## ⚙️ Configuration Terms

| Term                   | Description                                                    |
|------------------------|----------------------------------------------------------------|
| `jest.config.js`       | Jest’s main configuration file.                                |
| `setupFiles`           | Scripts run before the test framework is installed.            |
| `setupFilesAfterEnv`   | Scripts run after the test environment is set up.              |
| `testEnvironment`      | Defines the test environment (`node`, `jsdom`, etc).           |

---

### 📚 Recommended Resources

- [Jest Official Docs](https://jestjs.io/docs/getting-started)
- [Testing Library Docs](https://testing-library.com/)
- [Awesome Jest GitHub](https://github.com/jest-community/awesome-jest)

