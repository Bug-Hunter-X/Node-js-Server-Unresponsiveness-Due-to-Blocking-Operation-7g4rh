# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a long-running operation in the request handler blocks the event loop, causing the server to become unresponsive.  The `bug.js` file shows the problematic code.  The solution is presented in `bugSolution.js`.

## Problem

Node.js is single-threaded.  If a request handler performs a long operation without yielding control to the event loop, all subsequent requests are blocked.  This leads to unresponsiveness and poor performance.

## Solution

The solution involves using asynchronous operations such as asynchronous functions or by offloading the long-running task to worker threads or another process. This ensures the event loop remains free to handle new requests while the long-running tasks complete. 