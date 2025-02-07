# React: Memory Leak with setInterval in useEffect

This repository demonstrates a common mistake in React applications involving the use of `setInterval` within the `useEffect` hook, leading to memory leaks.  The provided `bug.js` file showcases the incorrect implementation, while `bugSolution.js` offers the corrected version.

## Problem

The `setInterval` function, when used without proper cleanup, continues to run even after the component that initiated it is unmounted. This results in a memory leak, especially if the component is frequently mounted and unmounted.

## Solution

The solution involves adding a cleanup function to the `useEffect` hook. This function, returned from the `useEffect` hook, is executed when the component unmounts. This cleanup function is responsible for clearing the interval using `clearInterval`, preventing the memory leak.

## How to reproduce

1. Clone the repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the console for any errors or warnings (in the incorrect example).
5. Compare the behavior of the original and corrected code.