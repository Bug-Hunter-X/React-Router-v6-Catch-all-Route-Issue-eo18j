# React Router v6 Catch-all Route Unexpected Behavior

This repository demonstrates an uncommon issue in React Router v6 related to the catch-all route (`/*`).  The problem occurs when the catch-all route is defined after more specific routes.  Even though specific paths are defined earlier, the catch-all route intercepts all requests.

## Reproduction

1. Clone the repository.
2. Install dependencies: `npm install`
3. Run the app: `npm start`
4. Observe that navigating to `/` or `/about` results in the 404 Not Found component being displayed rather than Home or About.

## Solution

The solution involves ordering the routes correctly within the `Routes` component. The catch-all route (`/*`) should always be placed last. This ensures that it only catches routes that do not match any of the other defined routes.