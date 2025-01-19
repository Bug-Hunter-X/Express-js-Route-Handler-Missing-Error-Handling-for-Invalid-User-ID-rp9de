# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of error handling for invalid input.  Specifically, the code attempts to parse a user ID as an integer without validating if the input is actually a number. This can lead to unexpected errors or crashes.

## Bug

The `bug.js` file contains the erroneous code.  The route handler for `/users/:id` attempts to find a user by ID. However, it doesn't handle the case where `req.params.id` is not a valid number, resulting in a potential `NaN` error or unexpected behavior.

## Solution

The `bugSolution.js` file provides a corrected version.  It adds input validation to ensure `req.params.id` is a number before attempting to parse it.  Appropriate error handling is included to return a 400 Bad Request status code for invalid input and a 404 Not Found status code if the user isn't found.