# Missing Error Handling in Express.js Route Handler

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling for invalid input.

The `bug.js` file shows a route handler that attempts to find a user based on their ID.  However, it fails to handle cases where the `userId` is not a valid number or if no user with that ID exists.

The `bugSolution.js` file provides a corrected version of the handler, adding comprehensive error handling to gracefully manage these scenarios.  This includes explicit checks for invalid input and returning appropriate HTTP status codes.

## How to reproduce the bug:

1. Clone this repository.
2. Run `npm install express`
3. Run `node bug.js`
4. Send a GET request to `/users/abc` (or any non-numeric ID).  The server will likely crash.

## How to use the solution:

1. Run `node bugSolution.js`
2. Try sending the same GET request to `/users/abc`. This time the server should respond with a 400 Bad Request error or 404 Not Found error instead of crashing.