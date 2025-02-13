# React useEffect Cleanup Issue

This repository demonstrates a common issue with the `useEffect` hook in React 18 and 19 where the cleanup function doesn't work as expected, especially when using `setInterval`. The problem stems from an incorrect dependency array, leading to memory leaks and unexpected behavior.

## Problem

The provided `bug.js` file contains a `MyComponent` that uses `useEffect` to update a counter every second.  However, the cleanup function, which is supposed to clear the `setInterval`, doesn't function properly because of missing dependencies in the `useEffect`'s second argument. This results in multiple intervals running simultaneously, leading to performance issues and potential crashes. 

## Solution

The solution, provided in `bugSolution.js`, correctly includes `count` in the dependency array. This ensures that the cleanup function is called whenever the `count` changes or the component unmounts, thereby preventing memory leaks and ensuring proper cleanup.