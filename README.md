# Unhandled Error in Asynchronous Node.js HTTP Server

This repository demonstrates a subtle bug in a Node.js HTTP server where an unhandled error in an asynchronous operation causes the server to hang without any clear indication of failure. The bug arises from missing error handling within the callback function of `http.createServer`. 

## Bug Description
The `bug.js` file contains a simple HTTP server that simulates an asynchronous operation (using `setTimeout`).  Half the time, it simulates a successful operation. The other half, it simulates an error but lacks proper error handling, causing the server to hang and not send a response to the client.

## Solution
The `bugSolution.js` file provides a solution to this problem by adding comprehensive error handling to the asynchronous operation. The solution includes a `catch` block to handle potential errors and ensures a proper response is sent back to the client even in the case of failure.