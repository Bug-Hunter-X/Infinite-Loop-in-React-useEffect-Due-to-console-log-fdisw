# React useEffect Infinite Loop Bug

This repository demonstrates a subtle bug in a React component's `useEffect` hook that can lead to an infinite render loop. The issue arises from placing a `console.log` statement directly within the `useEffect`'s callback, without proper dependency management.

## Bug Description
The `MyComponent` uses `useState` to manage a count. The `useEffect` hook intends to log the count whenever it changes. However, because the `console.log` statement creates a new closure on every render, it unintentionally causes the effect to run repeatedly, resulting in an infinite loop and crashing the browser.

## Solution
The correct way is to move the `console.log` outside the useEffect or only include necessary dependencies in the dependency array.  See the `bugSolution.js` file for corrected code.