# Node.js Server Hang During Long-Running Tasks

This repository demonstrates a common issue in Node.js where a long-running task in the main thread blocks the event loop, causing the server to become unresponsive. The `bug.js` file shows the problematic code, while `bugSolution.js` provides a solution using asynchronous operations.

## Problem

Node.js is single-threaded, meaning it uses only one thread to handle all events.  A long-running synchronous task can prevent Node.js from processing other requests, leading to a hang.

## Solution

The solution involves offloading the long-running task to an asynchronous operation or worker thread.  This ensures the main event loop stays responsive to incoming requests, preventing the server from hanging.