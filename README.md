# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React applications: using `setInterval` within the `useEffect` hook without proper cleanup.  This leads to memory leaks and unpredictable behavior.

The `bug.js` file contains the problematic code.  The `bugSolution.js` file shows the corrected version.

## Problem
The original code uses `setInterval` to update a counter every second. However, it fails to clear the interval when the component unmounts, resulting in a memory leak.  The interval continues to run even after the component is no longer needed.

## Solution
The solution involves returning a cleanup function from `useEffect`. This function clears the interval when the component unmounts, preventing memory leaks.

## How to reproduce:
1. Clone the repository.
2. Navigate to the repository in your terminal.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.
5. Observe the memory usage of your browser.  The `bug.js` version will increase memory consumption over time, while the solution will not.