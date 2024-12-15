# Express.js Route Handler Missing Error Handling

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  Specifically, the `/users/:id` route fails to handle cases where the `id` parameter is not a valid number or if no user with that ID exists.

The `bug.js` file shows the buggy code.  The `bugSolution.js` file provides a corrected version with comprehensive error handling.

## Bug
The original code attempts to parse the user ID as an integer without checking if the conversion is successful.  If the ID is not a number, `parseInt(userId)` will return `NaN`, causing the `find` method to fail silently or throw an error depending on the context.  Similarly, if no user matches the ID, a 404 error should be returned gracefully.