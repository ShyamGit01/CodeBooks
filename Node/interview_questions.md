
# Node.js Interview Questions and Answers

# Basic Level Questions

# 1. What is Node.js?
 Node.js is an open-source, cross-platform JavaScript runtime environment that executes JavaScript code outside a web browser. 
It uses Chrome's V8 JavaScript engine and enables building scalable network applications.


# 2. What are the key features of Node.js?

- Asynchronous and Event Driven
- Single Threaded but Highly Scalable
- No Buffering
- Very Fast
- Package Manager (npm)
- Large and Active Community


# 3. What is npm?
 npm (Node Package Manager) is the default package manager for Node.js. 
It allows developers to install, share, and manage dependencies of Node.js projects.


# 4. What is package.json?
 package.json is a metadata file that contains information about a Node.js project including:
- Project dependencies
- Scripts
- Version information
- Project description
- Author details


# 5. What is the difference between Node.js and JavaScript?

JavaScript is a programming language, while Node.js is a runtime environment that allows JavaScript to be run outside the browser.
JavaScript runs on client-side, Node.js runs on server-side.


# 6. What is callback in Node.js?
 A callback is a function that is called when an async operation completes. 
It's passed as an argument to another function and executed after the main function has finished execution.


# Example of callback
function example(callback) {
    setTimeout(() => {
        callback("Operation completed");
    }, 1000);
}

# 7. What is callback hell?
 Callback hell refers to heavily nested callbacks that make code hard to read and maintain.
It occurs when multiple asynchronous operations depend on each other.


# 8. What is the Event Loop in Node.js?
 The Event Loop is what allows Node.js to perform non-blocking I/O operations despite JavaScript being single-threaded.
It handles the execution of multiple chunks of your program over time.


# 9. What are Streams in Node.js?
 Streams are objects that let you read data from a source or write data to a destination continuously.
Types: Readable, Writable, Duplex, Transform


# 10. What is Buffer in Node.js?
 Buffer class is used to handle binary data.
It's similar to an array of integers but corresponds to raw memory allocation outside the V8 heap.


# Intermediate Level Questions

# 11. What is middleware in Node.js?
 Middleware functions are functions that have access to the request object, response object, 
and the next middleware function. They can execute any code, modify request/response objects, or end the request-response cycle.


# 12. What is Express.js?
 Express.js is a web application framework for Node.js.
It provides a robust set of features for web and mobile applications.


# 13. What is the purpose of module.exports?
 module.exports is used to expose functions, objects, or variables from one module to be used in other modules.
It helps in maintaining modular code.


# 14. What is the difference between require and import?

- require is CommonJS syntax
- import is ES6 syntax
- require is synchronous
- import can be asynchronous


# 15. What is clustering in Node.js?
 Clustering in Node.js allows you to create child processes (workers) that run simultaneously 
and share the same server port, enabling better use of multi-core systems.


# 16. What is the purpose of the process object?
 The process object provides information about, and control over, the current Node.js process.
It's a global object and can be accessed from anywhere.


# 17. What are Events in Node.js?
 Events in Node.js are handled through EventEmitter class.
It's the core of Node's asynchronous event-driven architecture.


# 18. What is the purpose of setTimeout?
 setTimeout is used to schedule execution of a one-time callback after delay milliseconds.


# 19. What is the difference between setImmediate and process.nextTick?

- process.nextTick executes in the current iteration of the event loop
- setImmediate executes in the following iteration


# 20. What is Error-First Callback?
 Error-First Callback is a pattern where callbacks take an error as their first parameter.
null indicates no error, while any other value indicates an error occurred.


# Advanced Level Questions

# 21. What is Memory Leak in Node.js?
 Memory leak occurs when a program incorrectly manages memory allocations.
Common causes include global variables, callbacks, event listeners.


# 22. How do you debug Node.js applications?

- Using debugger statement
- Node.js debugger
- Chrome DevTools
- VS Code debugging


# 23. What is the purpose of NODE_ENV?
 NODE_ENV is an environment variable used to specify the environment in which an application is running
(development, production, testing, etc).


# 24. What are Worker Threads in Node.js?
 Worker Threads enable parallel execution of JavaScript code.
They're useful for CPU-intensive tasks.


# 25. What is the difference between readFile and createReadStream?

- readFile reads entire file into memory
- createReadStream reads file in chunks, better for large files


# 26. What is the purpose of the Buffer class?
 Buffer class is used to handle binary data directly.
It's particularly useful when dealing with TCP streams and file system operations.


# 27. What is the purpose of __dirname?
 __dirname represents the directory name of the current module.
It's a global variable provided by Node.js.


# 28. What is the purpose of process.env?
 process.env is an object containing the user environment.
It's commonly used to store configuration values.


# 29. What is the Event Emitter pattern?
 Event Emitter is a pattern that allows objects to communicate through events.
It's fundamental to Node.js's asynchronous nature.


# 30. What is the purpose of the crypto module?
 The crypto module provides cryptographic functionality including OpenSSL's hash, HMAC, cipher, decipher, sign, and verify functions.


# Security Questions

# 31. What are common security threats in Node.js applications?

- SQL Injection
- Cross-Site Scripting (XSS)
- CSRF attacks
- DOS attacks


# 32. How do you handle authentication in Node.js?
 Common methods include:
- JWT
- Passport.js
- Session-based auth
- OAuth


# 33. What is CORS?
 Cross-Origin Resource Sharing (CORS) is a mechanism that allows restricted resources to be requested from another domain.


# Performance Questions

# 34. How do you optimize Node.js application performance?

- Caching
- Using gzip compression
- Clustering
- Load balancing


# 35. What is load balancing in Node.js?
 Load balancing is distributing incoming network traffic across multiple servers
to ensure no single server bears too much load.


# Database Questions

# 36. How do you connect Node.js with MongoDB?
 Using Mongoose ODM or the native MongoDB driver.


# 37. What is the difference between SQL and NoSQL databases?

- SQL: Structured, predefined schema
- NoSQL: Flexible schema, better for unstructured data


# Testing Questions

# 38. What testing frameworks are available for Node.js?

- Mocha
- Jest
- Jasmine
- Chai


# 39. What is unit testing?
 Unit testing is testing individual components or functions in isolation.


# 40. What is integration testing?
 Integration testing tests how different parts of the application work together.


# Deployment Questions

# 41. How do you deploy Node.js applications?

- Heroku
- AWS
- Digital Ocean
- Docker containers


# 42. What is Docker and why is it useful?
 Docker is a platform for developing, shipping, and running applications in containers.
It ensures consistency across different environments.


# Error Handling Questions

# 43. How do you handle errors in Node.js?

- Try-catch blocks
- Error events
- Promise rejections
- Error-first callbacks


# 44. What is Error Handling Middleware?
 Middleware that handles errors in Express.js applications.
Takes four parameters: (err, req, res, next)


# Asynchronous Programming Questions

# 45. What are Promises?
 Promises represent a value that may be available now, or in the future, or never.
They help manage asynchronous operations.


# 46. What is async/await?
 async/await is syntactic sugar over promises, making asynchronous code look synchronous.


# 47. What is the difference between Promise and callback?

- Promises are more readable
- Better error handling
- Can be chained


# Architecture Questions

# 48. What is MVC architecture?
 Model-View-Controller is a design pattern that separates application logic into three components:
- Model (data)
- View (presentation)
- Controller (logic)


# 49. What is microservices architecture?
 Microservices architecture breaks down applications into small, independent services
that communicate through APIs.


# 50. What is REST API?
 REST (Representational State Transfer) is an architectural style for designing networked applications.
Uses HTTP methods GET, POST, PUT, DELETE.


# Additional Questions (51-100)

# 51. What is GraphQL?
 GraphQL is a query language for APIs that allows clients to request specific data.


# 52. What is WebSocket?
 WebSocket is a protocol providing full-duplex communication channels over a single TCP connection.


# 53. What is the difference between PUT and PATCH?

- PUT updates entire resource
- PATCH updates part of resource


# 54. What is JWT?
 JSON Web Token is a compact, URL-safe means of representing claims between parties.


# 55. What is OAuth?
 OAuth is an open standard for access delegation, commonly used for secure authorization.


# 56. What is rate limiting?
 Rate limiting controls the amount of incoming and outgoing traffic to or from a network.


# 57. What is caching?
 Caching stores frequently accessed data in memory for faster retrieval.


# 58. What is Redis?
 Redis is an in-memory data structure store, used as database, cache, message broker.


# 59. What is session management?
 Session management tracks user activity across requests using session IDs.


# 60. What is middleware chaining?
 Middleware chaining is executing multiple middleware functions in sequence.


# 61. What is the purpose of body-parser?
 body-parser parses incoming request bodies before handlers.


# 62. What is the difference between dependencies and devDependencies?

- dependencies required in production
- devDependencies only needed for development


# 63. What is npm shrinkwrap?
 npm shrinkwrap locks down dependency versions for publication.


# 64. What is package-lock.json?
 package-lock.json records exact versions of installed dependencies.


# 65. What is the purpose of .npmignore?
 .npmignore specifies files to exclude when publishing package to npm.


# 66. What is npx?
 npx executes npm package binaries without installing them globally.


# 67. What is the purpose of process.argv?
 process.argv contains command line arguments passed to the Node.js process.


# 68. What is the purpose of process.exit()?
 process.exit() terminates the Node.js process with specified exit code.


# 69. What is the purpose of process.on()?
 process.on() binds event handlers to process events.


# 70. What is the purpose of child_process module?
 child_process module enables spawning child processes.


# 71. What is the purpose of cluster module?
 cluster module enables running multiple Node.js processes to handle load.


# 72. What is the purpose of os module?
 os module provides operating system-related utility methods.


# 73. What is the purpose of path module?
 path module provides utilities for working with file and directory paths.


# 74. What is the purpose of fs module?
 fs module enables interacting with the file system.


# 75. What is the purpose of http module?
 http module creates HTTP servers and makes HTTP requests.


# 76. What is the purpose of https module?
 https module is similar to http but for HTTPS.


# 77. What is the purpose of url module?
 url module parses and resolves URLs.


# 78. What is the purpose of querystring module?
 querystring module parses and formats URL query strings.


# 79. What is the purpose of util module?
 util module provides utility functions for debugging and deprecation.


# 80. What is the purpose of net module?
 net module provides an asynchronous network API.


# 81. What is the purpose of dns module?
 dns module enables name resolution functionality.


# 82. What is the purpose of tls module?
 tls module implements TLS and SSL protocols.


# 83. What is the purpose of assert module?
 assert module provides assertions for testing.


# 84. What is the purpose of vm module?
 vm module compiles and runs code within V8 Virtual Machine contexts.


# 85. What is the purpose of zlib module?
 zlib module provides compression functionality.


# 86. What is the purpose of stream module?
 stream module provides interface for streaming data.


# 87. What is the purpose of readline module?
 readline module provides interface for reading data line by line.


# 88. What is the purpose of string_decoder module?
 string_decoder module provides interface for decoding buffer objects into strings.


# 89. What is the purpose of timers module?
 timers module implements timer functions like setTimeout().


# 90. What is the purpose of repl module?
 repl module implements Read-Eval-Print-Loop functionality.


# 91. What is the purpose of punycode module?
 punycode module is a character encoding scheme.


# 92. What is the purpose of domain module?
 domain module handles multiple different IO operations as a single group.


# 93. What is the purpose of console module?
 console module provides debugging console similar to web browsers.


# 94. What is the purpose of cluster module?
 cluster module allows running multiple Node.js processes to handle load.


# 95. What is the purpose of async_hooks module?
 async_hooks module tracks asynchronous resources.


# 96. What is the purpose of inspector module?
 inspector module enables debugging using Chrome DevTools.


# 97. What is the purpose of perf_hooks module?
 perf_hooks module enables performance measurements.


# 98. What is the purpose of trace_events module?
 trace_events module provides mechanisms to centralize tracing information.


# 99. What is the purpose of v8 module?
 v8 module exposes APIs specific to the version of V8.


# 100. What is the purpose of worker_threads module?
 worker_threads module enables using threads that execute JavaScript in parallel.

# 101. Which of the following is used for asynchronous iteration in Node.js?
The for...await...of loop is used to asynchronously iterate over an iterable object, such as an array of Promises, in Node.js.


# 102. Types of For loop in node.
// 1. Traditional for loop
// - Basic iteration over a sequence of numbers
// - Most straightforward loop control
for (let i = 0; i < array.length; i++) {
    // Loop body
}

// 2. for...in loop 
// - Iterates over enumerable properties of an object
// - Returns property names/keys
for (let key in object) {
    // Loop body using object[key]
}

// 3. for...of loop
// - Iterates over iterable objects (arrays, strings, etc)
// - Returns values directly
for (let value of iterable) {
    // Loop body using value
}

// 4. for...await...of loop
// - Asynchronously iterates over async iterable objects
// - Waits for promises to resolve
async function example() {
    for await (let value of asyncIterable) {
        // Loop body using value
    }
}

// 5. forEach loop
// - Array method that executes callback for each element
// - Cannot break/continue
array.forEach((item, index) => {
    // Loop body
});

// Example of asynchronous iteration using for...await...of
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


# 103. Creating a simple promise
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