# React useEffect setInterval Memory Leak

This repository demonstrates a common mistake in React applications involving the `useEffect` hook and the `setInterval` function, leading to memory leaks.

## Problem

The `MyComponent` component uses `setInterval` within a `useEffect` hook to update a counter every second.  However, it fails to provide a cleanup function to clear the interval when the component unmounts, resulting in a memory leak.

## Solution

The `bugSolution.js` file shows the corrected code.  The cleanup function clears the interval using `clearInterval` when the component is unmounted, preventing the memory leak.

## How to Reproduce

1. Clone this repository.
2. Navigate to the project directory.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.
5. Observe the counter in the browser.  The memory leak will not be directly visible, but it's present.

## Learning Points

- Always include a cleanup function in `useEffect` when using functions like `setInterval` or `setTimeout`. This function will be called when the component unmounts or when the dependencies change.
- Memory leaks in React are subtle but can significantly impact performance.
- Careful attention to component lifecycle methods is crucial for building efficient and robust applications.