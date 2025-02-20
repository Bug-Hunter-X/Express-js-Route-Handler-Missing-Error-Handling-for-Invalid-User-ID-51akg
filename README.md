# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  lack of error handling for invalid or unexpected input.  Specifically, this example shows a route that fetches a user by ID but fails to handle cases where the ID is not a valid number.

## Bug
The `bug.js` file contains an Express.js route that fetches a user by ID.  It attempts to parse the ID as an integer using `parseInt()`, but doesn't check if the parameter is actually a number.  If a non-numeric ID is provided, `parseInt()` returns `NaN`, leading to a potential crash or unexpected behavior.

## Solution
The `bugSolution.js` file demonstrates the corrected code. It includes error handling to check if the `userId` is a number and returns a 400 Bad Request if it's not. It also handles the case where the user is not found, returning a 404 Not Found response.