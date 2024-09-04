## ✅ What is JS?
JavaScript is a single-threaded, non-blocking, asynchronous, concurrent programming language with lots of flexibility.

## ✅ Synchronous vs Asynchronous?
### Synchronous Part: 
The JavaScript engine maintains a stack data structure called function execution stack. The purpose of the stack is to track the current function in execution. In JS everything that happens inside the function execution stack is sequential. This is the Synchronous part of JavaScript. 

The function execution stack is also known as the *Call Stack*.

### Asynchronous Part:
Sometimes we may need to fetch data from the server or execute a function with a delay, something you do not anticipate occurring now. So, we want the code to execute asynchronously. We can classify most asynchronous JavaScript operations with two primary triggers:
1. **Browser API/Web API:** These events or functions. These include methods like setTimeout, or event handlers like click, mouse over, scroll, and many more. They rely on the callback function.
   - **Task Queue:** JavaScript maintains a queue of callback functions. It is called a callback queue or Task queue. A queue data structure is First-In-First-Out(FIFO). The item in the callback queue is called a macro task.
   - **Event Loop:** The engine creates a loop to look into the queue periodically to find what it needs to pull from there. It pulls a callback function from the queue to the call stack when it is empty. Now the callback function executes generally as any other function in the stack. The loop continues. This loop is famously known as the Event Loop.
2. **Promises:** A unique JavaScript object that allows us to perform asynchronous operations. We can create a promise using the Promise constructor. We need to pass an executor function to it. It contains two parameters: resolve (for successful) and reject (for thought error). After the promise is executed, we can handle the result using the .then() method and any errors with the .catch() method. We use promises every time we use the fetch() method to get some data from a store. The point here is that the JavaScript engine doesn't use the same callback queue we have seen earlier for browser APIs. It uses another special queue called the Job Queue.
   - **Job Queue:** Every time a promise occurs in the code, the executor function gets into the job queue. The event loop works, as usual, to look into the queues but gives priority to the job queue items over the callback queue items when the stack is free. The item in the job queue is called a microtask.
