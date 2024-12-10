# Unhandled Promise Rejection in Express.js Route Handler

This repository demonstrates a common error in Express.js applications: an unhandled promise rejection within a route handler.  The error is logged to the console, but no error response is sent to the client, leading to a silent failure.

The `bug.js` file contains the erroneous code. The `bugSolution.js` file provides a corrected version.

## Problem

The issue stems from an asynchronous operation within the route handler that may throw an error.  The `.catch()` block handles the error, but it only logs it to the console.  No response is sent back to the client, resulting in a poor user experience.

## Solution

The solution involves properly handling the rejection within the route handler and sending an appropriate error response to the client using `res.status()` and `res.send()` or `res.json()`. This provides better feedback and error handling.