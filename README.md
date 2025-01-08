# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in the request handler blocks the event loop, causing the server to become unresponsive. The `server.js` file contains the buggy code, while `serverSolution.js` provides a solution using asynchronous operations.

## Bug

The server hangs because the `while` loop in the request handler runs synchronously for 5 seconds. This blocks the event loop, preventing other requests from being processed during this time.  This demonstrates a classic example of blocking I/O.

## Solution

The solution is to use asynchronous operations.  By offloading long-running tasks to separate threads or processes, the main event loop remains free to handle other requests, ensuring responsiveness.