# 2. Node.js & TypeScript [4-6 hours]

**Goal:** 
- Learn how to run a simple Node.js program and debug it. 
- Learn about the basic concepts required for web development. These are core fundamentals principles required to get started.
- Learn how to program using JavaScript and TypeScript.
- Understand how asynchronous code works. (**important**)


## Mandatory Materials:

**Videos:**
 - [Computer Science Concepts](https://www.youtube.com/watch?v=-uleG_Vecis)
 - [SSL, TLS, HTTPS](https://www.youtube.com/watch?v=j9QmMEWmcfo)
 - [Functional Programming Concepts](https://youtu.be/nuML9SmdbJ4)
 - [Async, Await](https://www.youtube.com/watch?v=vn3tm0quoqE) (Note that Node.js uses a [V8 Engine](https://nodejs.org/en/learn/getting-started/the-v8-javascript-engine) for the Event Loop)
 - [TypeScript](https://www.youtube.com/watch?v=zQnBQ4tB3ZA)

**Reading:**

 - [Node.js: Getting started](https://nodejs.org/en/docs/guides/getting-started-guide)
 - [Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
 - [Overview of HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)
 - [TypeScript in 5 minutes](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html)
 - [JavaScript Syntax](https://learnxinyminutes.com/docs/javascript/)

**Style Guide Reference (optional)**
- [TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html)
- [JavaScript Style Guide (Airbnb)](https://github.com/airbnb/javascript)

## Online Shop: 

 > Debug your code:
 > - Add a new `start:debug` npm script to your package.json. This script should execute `node index.js --inspect-brk `. The `inspect-brk` switch instructs Node.js to listen on a debugging port for the debugger and to not start code execution before the debugger attaches.
 > - Place a breakpoint in your code.
 > - If you are using VSCode, create a new VSCode debugging configuration (with the default `Node.js: Attach` settings) and start it.
 > - If you are using WebStorm, simply follow [this link](https://blog.jetbrains.com/webstorm/2018/01/how-to-debug-with-webstorm/).
 
## Further Resources:

- [Asynchronous programming in Node.js](https://codeforgeek.com/asynchronous-programming-in-node-js/)
- [Debugging in VSCode](https://code.visualstudio.com/docs/editor/debugging)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/basic-types.html)
- [JavaScript Tutorial: TheNewBoston](https://www.youtube.com/watch?v=yQaAGmHNn9s&list=PL46F0A159EC02DF82)
