# Express.js 404 Error with Multiple Asynchronous Operations

This repository demonstrates a subtle bug in an Express.js server that can lead to 404 errors when handling multiple asynchronous requests concurrently.  The issue arises from the way asynchronous operations and request handling are managed within the server.

## Bug Description

The provided `bug.js` file contains an Express.js server setup with a single route. While seemingly simple, the server exhibits unexpected 404 errors when multiple requests arrive at approximately the same time. This demonstrates a race condition during request handling which can lead to inconsistent behaviour. 

## Bug Solution

The `bugSolution.js` file provides a solution to this problem, illustrating how to correctly handle async operations within an Express.js application.  It addresses the race condition.  The key is to ensure each request has its own isolated context and does not interfere with others. For example, if the asynchronous operation relies on a shared resource, proper synchronization must be employed.