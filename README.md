# React Router v6 Nested Route Matching Bug

This repository demonstrates a common issue encountered when working with nested routes in React Router v6.  The problem arises when a parent route is defined *before* a more specific child route, resulting in the child route never matching.  This is due to the order in which React Router processes routes.

## Reproducing the Bug

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe that navigating to `/about` displays the `About` component, but navigating to `/about/something` still displays the `About` component, instead of the expected `AboutDetails` component.

## Solution

The solution is to order the routes correctly. More specific routes should be defined *before* their parent routes to ensure they match first.