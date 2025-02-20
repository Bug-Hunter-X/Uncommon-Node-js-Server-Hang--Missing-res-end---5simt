# Uncommon Node.js Server Hang: Missing res.end()

This repository demonstrates a subtle but common error in Node.js HTTP servers: forgetting to call `res.end()` to signal the end of the response.

## The Bug

The `bug.js` file contains a simple HTTP server that omits the crucial `res.end()` call.  This can lead to the server hanging or behaving unexpectedly because the client doesn't receive a proper response termination signal.

## The Solution

The `bugSolution.js` file provides the corrected code, adding the `res.end()` call to properly conclude the response and prevent the server hang.

## How to Reproduce

1. Clone this repository.
2. Run `node bug.js` and try to access `http://localhost:3000` in your browser or with a tool like `curl`.  Observe the unexpected behavior.
3. Run `node bugSolution.js` and repeat. The server should now respond correctly.

This example highlights a frequently overlooked aspect of Node.js HTTP server development. Always ensure that you properly end your responses using `res.end()` to avoid unexpected hangs and ensure smooth client-server communication.