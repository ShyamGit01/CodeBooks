
# Node.js Interview Questions and Answers

## Basic Level Questions

### 1. What is Node.js?
 Node.js is an open-source, cross-platform JavaScript runtime environment that executes JavaScript code outside a web browser (server side). 
It uses Chrome's V8 JavaScript engine and enables building scalable network applications.
- not a language, framework

### 1.2 What is role of framework?
A framework is a pre-written set of tools, libraries, and best practices that provides a structured foundation for building software applications efficiently and consistently.
- works like wrapper over runtime env.
- providing additional feature lige mentioned below

| Role |        Description                |
| -----| --------------------------------------------------------------------- |
| **1. Structure & Organization** | Provides a consistent architecture (e.g., MVC – Model-View-Controller) to organize your code logically.     |
| **2. Code Reusability**         | Offers pre-built components and functions to avoid writing repetitive code.                                 |
| **3. Productivity Boost**       | Speeds up development by reducing boilerplate and giving ready-to-use features.                             |
| **4. Maintainability**          | Encourages best practices, making the codebase easier to maintain and scale.                                |
| **5. Security**                 | Many frameworks handle common security concerns like input validation, CSRF, XSS protection out-of-the-box. |
| **6. Community & Ecosystem**    | Comes with plugins, modules, and community support that expand its capabilities.                            |

### 1.3 Top Reasons Why Node.js Is Preferred ?
| Reason   | Explanation                                           |
| -------- | ----------------------------------------------------- |
| **1. JavaScript Everywhere**         | You can use **JavaScript on both frontend and backend**, reducing context switching and unifying your codebase.                                                                                 |
| **2. Non-blocking I/O & Event Loop** | Node.js uses an **asynchronous**, **non-blocking** model (via **libuv**) that handles **thousands of concurrent connections efficiently**, making it ideal for real-time and high-traffic apps. |
| **3. Lightweight & Fast**            | Built on **Google's V8 engine**, Node.js is highly optimized and faster in I/O-heavy operations compared to traditional, thread-blocking models like Java/PHP.                                  |
| **4. NPM Ecosystem**                 | The **Node Package Manager (NPM)** is the world’s largest open-source library repository — you get modules for almost everything.                                                               |
| **5. Microservices & APIs**          | Node.js is lightweight and modular, making it great for **microservice architectures** and **REST/GraphQL APIs**.                                                                               |
| **6. Real-time Apps**                | Perfect for apps like **chat, games, live dashboards** (thanks to libraries like `socket.io`). Java and PHP aren't as naturally suited for this.                                                |
| **7. Dev Speed & Startup Culture**   | Node's simplicity, fast iteration, and massive community make it a favorite for startups and rapid MVP development.                                                                             |

### 1.4 What is REPL in Node.js?
REPL stands for:
`Read – Eval – Print – Loop`

It is an interactive shell that allows you to:
- Run JavaScript code line-by-line
- Quickly test expressions, functions, or Node.js features
- Debug small snippets without creating files

### 2. What are the key features of Node.js?

- Asynchronous and Event Driven
- Single Threaded but Highly Scalable
- No Buffering
- Very Fast
- Package Manager (npm)
- Large and Active Community

### 2.2 what is Event, EventEmitter, Event Queue, Event Handler, Event Loop in node ?
Event : An event is a signal that something has happened.

For example:
- A file has been read
- A request has arrived
- A timer has completed

EventEmitter :  The EventEmitter class (in the events module) allows you to:
- Emit (trigger) custom events
- Listen for them with event handlers

Event Queue : The event queue is a queue where asynchronous tasks (callbacks, events, timers, etc.) are placed when they are ready to be executed.
- After the current call stack finishes, the event loop checks this queue.
- It processes one event at a time (non-blocking).

Event Handler : An event handler (or listener) is a function that gets executed when a specific event is emitted.

Event Loop : The event loop is the heart of Node.js. It handles:
- Asynchronous operations
- Callback execution
- Timer handling
- Non-blocking I/O

It continuously checks:
- Is the call stack empty?
- Are there events in the queue?
- If yes, it dequeues and runs the associated handler.

```
const EventEmitter = require('events');
const emitter = new EventEmitter();

emitter.on('message', (msg) => {
  console.log('Handled:', msg);
});

setTimeout(() => {
  console.log('Timer Done');
  emitter.emit('message', 'Hello World');
}, 1000);

console.log('Program Started');
```

Execution Flow:
- console.log('Program Started') runs immediately.
- setTimeout() is offloaded to the Timer API (not blocking).
- The event loop waits for tasks.
- After 1 second, the timer’s callback is placed in the event queue.
- The event loop pulls it in and executes:
    - console.log('Timer Done')
    - emitter.emit(...) emits the event
    - Event handler runs: console.log('Handled: Hello World')

### 2.3 what is event in node and how it woks ?
| Term              | Description                                                    |
| ----------------- | -------------------------------------------------------------- |
| **Event**         | Notification that something happened (e.g., `data`, `connect`) |
| **EventEmitter**  | Tool to emit and listen for events                             |
| **Event Queue**   | Queue of tasks waiting for execution                           |
| **Event Handler** | Function that executes when an event occurs                    |
| **Event Loop**    | Mechanism that processes the event queue in a non-blocking way |


### 2.4 what is Synchronous code, Microtasks, Macrotasks ?
Synchronous Code : Runs immediately, line-by-line, on the main thread.
Microtasks : Tasks that are scheduled to run right after synchronous code but before any macrotask.
- Examples of microtasks:
    - Promise.then(), catch(), finally()
    - await (code after await)
    - queueMicrotask()
    - process.nextTick() (Node.js only — executes even before Promises!)

Macrotasks : Scheduled to run after microtasks are cleared.
- Examples of macrotasks:
    - setTimeout, setInterval
    - setImmediate (Node.js)
    - I/O callbacks
    - UI rendering (in browsers)

### 3. What is npm?
 npm (Node Package Manager) is the default package manager for Node.js. 
It allows developers to install, share, and manage dependencies of Node.js projects.


### 4. What is package.json?
 package.json is a metadata file that contains information about a Node.js project including:
- Project dependencies
- Scripts
- Version information
- Project description
- Author details


### 5. What is the difference between Node.js and JavaScript?

JavaScript is a programming language, while Node.js is a runtime environment that allows JavaScript to be run outside the browser.
JavaScript runs on client-side, Node.js runs on server-side.


### 6. What is callback in Node.js?
A callback is a function that is called when an async operation completes. 
It's passed as an argument to another function and executed after the main function has finished execution.

- Example of callback
```
function example(callback) {
    setTimeout(() => {
        callback("Operation completed");
    }, 1000);
}
```

### 7. What is callback hell?
 Callback hell refers to heavily nested callbacks that make code hard to read and maintain.
It occurs when multiple asynchronous operations depend on each other.


### 8. What is the Event Loop in Node.js?
 The Event Loop is what allows Node.js to perform non-blocking I/O operations despite JavaScript being single-threaded.
It handles the execution of multiple chunks of your program over time.


### 9. What are Streams in Node.js?
 Streams are objects that let you read data from a source or write data to a destination continuously.
Types: Readable, Writable, Duplex, Transform


### 10. What is Buffer in Node.js?
 Buffer class is used to handle binary data.
It's similar to an array of integers but corresponds to raw memory allocation outside the V8 heap.


## Intermediate Level Questions

### 11. What is middleware in Node.js?
 Middleware functions are functions that have access to the request object, response object, 
and the next middleware function. They can execute any code, modify request/response objects, or end the request-response cycle.


### 12. What is Express.js?
 Express.js is a web application framework for Node.js.
It provides a robust set of features for web and mobile applications.


### 13. What is the purpose of module.exports?
 module.exports is used to expose functions, objects, or variables from one module to be used in other modules.
It helps in maintaining modular code.


### 14. What is the difference between require and import?
- require is CommonJS syntax
- import is ES6 syntax
- require is synchronous
- import can be asynchronous


### 15. What is clustering in Node.js?
 Clustering in Node.js allows you to create child processes (workers) that run simultaneously 
and share the same server port, enabling better use of multi-core systems.


### 16. What is the purpose of the process object?
 The process object provides information about, and control over, the current Node.js process.
It's a global object and can be accessed from anywhere.


### 17. What are Events in Node.js?
 Events in Node.js are handled through EventEmitter class.
It's the core of Node's asynchronous event-driven architecture.

- example of event emitter
```
const EventEmitter = require('events');

// Create custom event emitter class
class MyEmitter extends EventEmitter {}

// Initialize emitter instance
const myEmitter = new MyEmitter();

// Register event listener for 'userLoggedIn' event
myEmitter.on('userLoggedIn', (userId) => {
    console.log(`User ${userId} has logged in`);
});

// Register event listener for 'error' event
myEmitter.on('error', (err) => {
    console.error('Error occurred:', err);
});

// Register one-time event listener
myEmitter.once('welcome', (name) => {
    console.log(`Welcome ${name}! This message will show only once.`);
});

// Emit events
myEmitter.emit('userLoggedIn', 'user123');
myEmitter.emit('welcome', 'John');
myEmitter.emit('welcome', 'Jane'); // Won't trigger since listener was 'once'
myEmitter.emit('error', new Error('Something went wrong'));

// Multiple listeners for same event
myEmitter.on('notification', (message) => {
    console.log('First listener:', message);
});

myEmitter.on('notification', (message) => {
    console.log('Second listener:', message);
});

myEmitter.emit('notification', 'Hello World');
```

### 18. What is the purpose of setTimeout?
 setTimeout is used to schedule execution of a one-time callback after delay milliseconds.


### 19. What is the difference between setImmediate and process.nextTick?

- process.nextTick executes in the current iteration of the event loop
- setImmediate executes in the following iteration


### 20. What is Error-First Callback?
 Error-First Callback is a pattern where callbacks take an error as their first parameter.
null indicates no error, while any other value indicates an error occurred.

- Example of error-first callback pattern
```
function readFileWithCallback(filePath, callback) {
    fs.readFile(filePath, (error, data) => {
        if (error) {
            // Call callback with error as first parameter
            return callback(error, null);
        }
        // Call callback with null error and data
        callback(null, data);
    });
}

// Using the error-first callback
readFileWithCallback('example.txt', (error, data) => {
    if (error) {
        console.error('Error reading file:', error);
        return;
    }
    console.log('File contents:', data);
});
```
## Advanced Level Questions

### 21. What is Memory Leak in Node.js?
 Memory leak occurs when a program incorrectly manages memory allocations.
Common causes include global variables, callbacks, event listeners.


### 22. How do you debug Node.js applications?

- Using debugger statement
- Node.js debugger
- Chrome DevTools
- VS Code debugging


### 23. What is the purpose of NODE_ENV?
 NODE_ENV is an environment variable used to specify the environment in which an application is running
(development, production, testing, etc).


### 24. What are Worker Threads in Node.js?
 Worker Threads enable parallel execution of JavaScript code.
They're useful for CPU-intensive tasks.


### 25. What is the difference between readFile and createReadStream?

- readFile reads entire file into memory
- createReadStream reads file in chunks, better for large files


### 26. What is the purpose of the Buffer class?
 Buffer class is used to handle binary data directly.
It's particularly useful when dealing with TCP streams and file system operations.


### 27. What is the purpose of __dirname?
 __dirname represents the directory name of the current module.
It's a global variable provided by Node.js.


### 28. What is the purpose of process.env?
 process.env is an object containing the user environment.
It's commonly used to store configuration values.


### 29. What is the Event Emitter pattern?
 Event Emitter is a pattern that allows objects to communicate through events.
It's fundamental to Node.js's asynchronous nature.


### 30. What is the purpose of the crypto module?
 The crypto module provides cryptographic functionality including OpenSSL's hash, HMAC, cipher, decipher, sign, and verify functions.


## Security Questions

### 31. What are common security threats in Node.js applications?

- SQL Injection
- Cross-Site Scripting (XSS)
- CSRF attacks
- DOS attacks


### 32. How do you handle authentication in Node.js?
 Common methods include:
- JWT
- Passport.js
- Session-based auth
- OAuth


### 33. What is CORS?
 Cross-Origin Resource Sharing (CORS) is a mechanism that allows restricted resources to be requested from another domain.


## Performance Questions

### 34. How do you optimize Node.js application performance?

- Caching
- Using gzip compression
- Clustering
- Load balancing


### 35. What is load balancing in Node.js?
 Load balancing is distributing incoming network traffic across multiple servers
to ensure no single server bears too much load.


## Database Questions

### 36. How do you connect Node.js with MongoDB?
 Using Mongoose ODM or the native MongoDB driver.


### 37. What is the difference between SQL and NoSQL databases?

- SQL: Structured, predefined schema
- NoSQL: Flexible schema, better for unstructured data


## Testing Questions

### 38. What testing frameworks are available for Node.js?

- Mocha
- Jest
- Jasmine
- Chai


### 39. What is unit testing?
 Unit testing is testing individual components or functions in isolation.


### 40. What is integration testing?
 Integration testing tests how different parts of the application work together.


## Deployment Questions

### 41. How do you deploy Node.js applications?

- Heroku
- AWS
- Digital Ocean
- Docker containers


### 42. What is Docker and why is it useful?
 Docker is a platform for developing, shipping, and running applications in containers.
It ensures consistency across different environments.


## Error Handling Questions

### 43. How do you handle errors in Node.js?

- Try-catch blocks
- Error events
- Promise rejections
- Error-first callbacks


### 44. What is Error Handling Middleware?
 Middleware that handles errors in Express.js applications.
Takes four parameters: `(err, req, res, next)`


## Asynchronous Programming Questions

### 45. What are Promises?
 Promises represent a value that may be available now, or in the future, or never.
They help manage asynchronous operations.


### 46. What is async/await?
 async/await is syntactic sugar over promises, making asynchronous code look synchronous.


### 47. What is the difference between Promise and callback?

- Promises are more readable
- Better error handling
- Can be chained


## Architecture Questions

### 48. What is MVC architecture?
 Model-View-Controller is a design pattern that separates application logic into three components:
- Model (data)
- View (presentation)
- Controller (logic)


### 49. What is microservices architecture?
 Microservices architecture breaks down applications into small, independent services
that communicate through APIs.


### 50. What is REST API?
 REST (Representational State Transfer) is an architectural style for designing networked applications.
Uses HTTP methods GET, POST, PUT, DELETE.

- HTTP Methods:
    - GET: "Retrieves/reads data from server",
    - POST: "Creates/sends new data to server", 
    - PUT: "Updates/replaces entire resource on server",
    - PATCH: "Partially updates/modifies existing resource on server",
    - DELETE: "Removes/deletes resource from server"


## Additional Questions (51-100)

### 51. What is GraphQL?
 GraphQL is a query language for APIs that allows clients to request specific data.


### 52. What is WebSocket?
 WebSocket is a protocol providing full-duplex communication channels over a single TCP connection.


### 53. What is the difference between PUT and PATCH?

- PUT updates entire resource
- PATCH updates part of resource


### 54. What is JWT?
 JSON Web Token is a compact, URL-safe means of representing claims between parties.

```
const jwt = require('jsonwebtoken');

// Secret key for signing tokens - in production store this securely in environment variables
const SECRET_KEY = 'your-secret-key';

// Function to generate JWT token
function generateToken(userData) {
    // Create token with user data and expiration
    const token = jwt.sign(
        { userId: userData.id, email: userData.email },
        SECRET_KEY,
        { expiresIn: '24h' } // Token expires in 24 hours
    );
    return token;
}

// Middleware to verify JWT token
function verifyToken(req, res, next) {
    // Get token from Authorization header
    const authHeader = req.headers['authorization'];
    const token = authHeader && authHeader.split(' ')[1]; // Bearer TOKEN

    if (!token) {
        return res.status(401).json({ message: 'No token provided' });
    }

    try {
        // Verify token
        const decoded = jwt.verify(token, SECRET_KEY);
        req.user = decoded;
        next();
    } catch (err) {
        return res.status(403).json({ message: 'Invalid token' });
    }
}
```

### 55. What is OAuth?
 OAuth is an open standard for access delegation, commonly used for secure authorization.


### 56. What is rate limiting?
 Rate limiting controls the amount of incoming and outgoing traffic to or from a network.


### 57. What is caching?
 Caching stores frequently accessed data in memory for faster retrieval.


### 58. What is Redis?
 Redis is an in-memory data structure store, used as database, cache, message broker.


### 59. What is session management?
 Session management tracks user activity across requests using session IDs.


### 60. What is middleware chaining?
 Middleware chaining is executing multiple middleware functions in sequence.


### 61. What is the purpose of body-parser?
 body-parser parses incoming request bodies before handlers.


### 62. What is the difference between dependencies and devDependencies?

- dependencies required in production
- devDependencies only needed for development


### 63. What is npm shrinkwrap?
 npm shrinkwrap locks down dependency versions for publication.


### 64. What is package-lock.json?
 package-lock.json records exact versions of installed dependencies.


### 65. What is the purpose of .npmignore?
 .npmignore specifies files to exclude when publishing package to npm.


### 66. What is npx?
 npx executes npm package binaries without installing them globally.


### 67. What is the purpose of process.argv?
 process.argv contains command line arguments passed to the Node.js process.


### 68. What is the purpose of process.exit()?
 process.exit() terminates the Node.js process with specified exit code.


### 69. What is the purpose of process.on()?
 process.on() binds event handlers to process events.


### 70. Various predefined module in Node.js?
- child_process : enables spawning child processes.
- cluster : enables running multiple Node.js processes to handle load.
- os : provides operating system-related utility methods.
- path : provides utilities for working with file and directory paths.
- fs : enables interacting with the file system.
- http : creates HTTP servers and makes HTTP requests.
- https : is similar to http but for HTTPS.
- url : parses and resolves URLs.
- querystring : parses and formats URL query strings.
- util : provides utility functions for debugging and deprecation.
- net : provides an asynchronous network API.
- dns : enables name resolution functionality.
- tls : implements TLS and SSL protocols.
- assert : provides assertions for testing.
- vm : compiles and runs code within V8 Virtual Machine contexts.
- zlib : provides compression functionality.
- stream : provides interface for streaming data.
- readline : provides interface for reading data line by line.
- string_decoder : provides interface for decoding buffer objects into strings.
- timers : implements timer functions like setTimeout().
- repl : implements Read-Eval-Print-Loop functionality.
- punycode : is a character encoding scheme.
- domain : handles multiple different IO operations as a single group.
- console : provides debugging console similar to web browsers.
- cluster : allows running multiple Node.js processes to handle load.
- async_hooks : tracks asynchronous resources.
- inspector : enables debugging using Chrome DevTools.
- perf_hooks : enables performance measurements.
- trace_events : provides mechanisms to centralize tracing information.
- v8 : exposes APIs specific to the version of V8.
- worker_threads : enables using threads that execute JavaScript in parallel.

### 72. Which of the following is used for asynchronous iteration in Node.js?
The for...await...of loop is used to asynchronously iterate over an iterable object, such as an array of Promises, in Node.js.


### 73. Types of For loop in node.
1. Traditional for loop
    - Basic iteration over a sequence of numbers
    - Most straightforward loop control
```
for (let i = 0; i < array.length; i++) {
    // Loop body
}
```

2. for...in loop 
    - Iterates over enumerable properties of an object
    - Returns property names/keys
```
for (let key in object) {
    // Loop body using object[key]
}
```

3. for...of loop
    - Iterates over iterable objects (arrays, strings, etc)
    - Returns values directly
```
for (let value of iterable) {
    // Loop body using value
}
```

4. for...await...of loop
    - Asynchronously iterates over async iterable objects
    - Waits for promises to resolve
```
async function example() {
    for await (let value of asyncIterable) {
        // Loop body using value
    }
}
```
// Example of asynchronous iteration using for...await...of
```
async function readFiles(fileList) {
    const fs = require('fs').promises;
    
    for await (const file of fileList) {
        const content = await fs.readFile(file, 'utf8');
        console.log(content);
    }
}

// Example usage:
const files = ['file1.txt', 'file2.txt', 'file3.txt'];
readFiles(files);

```
5. forEach loop
    - Array method that executes callback for each element
    - Cannot break/continue
```
array.forEach((item, index) => {
    // Loop body
});
```


# 74. Creating a simple promise
```
const myPromise = new Promise((resolve, reject) => {
    // Simulating an async operation
    setTimeout(() => {
        const randomNum = Math.random();
        if (randomNum > 0.5) {
            resolve(`Success! Random number is ${randomNum}`);
        } else {
            reject(`Failed! Random number is ${randomNum}`);
        }
    }, 1000);
});
```
// Using the promise
```
myPromise
    .then((result) => {
        console.log(result);
    })
    .catch((error) => {
        console.error(error);
    })
    .finally(() => {
        console.log('Promise completed');
    });
```

// Promise chaining example
```
const chainedPromise = new Promise((resolve, reject) => {
    resolve(1);
})
    .then(result => {
        return result * 2;
    })
    .then(result => {
        return result * 3;
    })
    .then(result => {
        console.log(result); // 6
    });
```

// Promise.all example
```
const promise1 = Promise.resolve(3);
const promise2 = new Promise(resolve => setTimeout(() => resolve('foo'), 2000));
const promise3 = Promise.resolve(42);

Promise.all([promise1, promise2, promise3])
    .then(values => {
        console.log(values); // [3, "foo", 42]
    });
```

// Async/await usage with promises
```
async function asyncFunction() {
    try {
        const result = await myPromise;
        console.log(result);
    } catch (error) {
        console.error(error);
    }
}
```

# 104. Types of promiss
// 1. Basic Promise
```
const basicPromise = new Promise((resolve, reject) => {
    setTimeout(() => {
        resolve("Basic promise resolved");
    }, 1000);
});
```

// 2. Promise.resolve() - Creates already resolved promise
```
const resolvedPromise = Promise.resolve("Already resolved");
```

// 3. Promise.reject() - Creates already rejected promise
```
const rejectedPromise = Promise.reject(new Error("Already rejected"));
```

// 4. Promise.all() - Waits for all promises to resolve
```
const promise1 = Promise.resolve(1);
const promise2 = Promise.resolve(2);
const promise3 = Promise.resolve(3);

Promise.all([promise1, promise2, promise3])
    .then(values => console.log(values)) // [1, 2, 3]
    .catch(error => console.error(error));
```

// 5. Promise.race() - Resolves/rejects as soon as one promise settles
```
const promise4 = new Promise(resolve => setTimeout(() => resolve("First"), 1000));
const promise5 = new Promise(resolve => setTimeout(() => resolve("Second"), 500));

Promise.race([promise4, promise5])
    .then(result => console.log(result)) // "Second"
    .catch(error => console.error(error));
```

// 6. Promise.allSettled() - Waits for all promises to settle
```
const promise6 = Promise.resolve(1);
const promise7 = Promise.reject("Error");

Promise.allSettled([promise6, promise7])
    .then(results => console.log(results));
    // [{status: "fulfilled", value: 1}, 
    //  {status: "rejected", reason: "Error"}]
```

// 7. Promise.any() - Resolves when any promise resolves
```
const promise8 = Promise.reject("Error 1");
const promise9 = Promise.resolve("Success");
const promise10 = Promise.reject("Error 2");

Promise.any([promise8, promise9, promise10])
    .then(value => console.log(value)) // "Success"
    .catch(error => console.error(error));
```

// 8. Chained Promises
```
new Promise((resolve, reject) => {
    resolve(1);
})
.then(result => result * 2)
.then(result => result * 3)
.then(result => console.log(result)) // 6
.catch(error => console.error(error));
```

// 9. Promise with timeout
```
function promiseWithTimeout(promise, timeout) {
    const timeoutPromise = new Promise((_, reject) => {
        setTimeout(() => reject(new Error('Timeout')), timeout);
    });
    return Promise.race([promise, timeoutPromise]);
}
```

// 10. Async/await with Promise
```
async function asyncPromise() {
    try {
        const result = await new Promise((resolve) => {
            setTimeout(() => resolve("Async result"), 1000);
        });
        return result;
    } catch (error) {
        console.error(error);
    }
}
```

// How Node.js Works - Core Components and Flow

// 1. V8 Engine
// - Google's open source JavaScript engine
// - Compiles JavaScript code to machine code
const v8Example = "V8 compiles this JavaScript code";

// 2. Event Loop
// - Heart of Node.js asynchronous programming
// - Handles all callbacks and non-blocking operations
function eventLoopExample() {
    console.log('Start');
    
    setTimeout(() => {
        console.log('Timer callback');
    }, 0);
    
    Promise.resolve().then(() => {
        console.log('Promise callback'); 
    });
    
    console.log('End');
}

// 3. Libuv
// - Handles asynchronous operations
// - Manages thread pool for heavy operations
const fs = require('fs');
fs.readFile('file.txt', (err, data) => {
    // Uses libuv thread pool
    if (err) throw err;
    console.log(data);
});

// 4. Node.js Core Modules
// - Built-in modules like http, fs, path etc
const http = require('http');
const server = http.createServer((req, res) => {
    res.end('Hello World');
});

// 5. Event Emitter
// - Implements Observer pattern
// - Core of Node.js event-driven architecture
const EventEmitter = require('events');
class MyEmitter extends EventEmitter {}
const myEmitter = new MyEmitter();
myEmitter.on('event', () => {
    console.log('Event occurred');
});

// 6. Call Stack
// - Tracks function execution
function first() {
    second();
}
function second() {
    third();
}
function third() {
    console.log('Call stack example');
}

// 7. Callback Queue
// - Stores callback functions
setTimeout(() => {
    console.log('Callback queue example');
}, 1000);

// 8. Worker Threads
// - Handles CPU-intensive tasks
const { Worker } = require('worker_threads');
const worker = new Worker(`
    // CPU intensive task
    const result = fibonacci(100);
`);

// 9. Single Thread Event Loop Architecture
function nonBlockingExample() {
    // This won't block
    fs.readFile('large-file.txt', (err, data) => {
        if (err) throw err;
        console.log('File read complete');
    });
    
    // Code continues executing
    console.log('Reading file...');
}

// 10. Asynchronous Flow
async function asyncFlowExample() {
    console.log('Start');
    
    const promise = new Promise(resolve => {
        setTimeout(() => resolve('Async operation complete'), 1000);
    });
    
    await promise;
    console.log('End');
}