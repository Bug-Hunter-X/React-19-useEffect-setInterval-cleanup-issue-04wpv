# React 19 useEffect setInterval Cleanup Issue

This repository demonstrates a common error when using `setInterval` within a React 19 `useEffect` hook: forgetting to include a cleanup function to prevent memory leaks.  The `bug.js` file showcases the incorrect implementation, while `bugSolution.js` provides the corrected version.

## Bug Description

The `setInterval` function, when used without a cleanup function in `useEffect`, will continue to run even after the component unmounts. This leads to memory leaks and potential performance issues.

## Solution

The solution involves returning a cleanup function from `useEffect`. This function is automatically called when the component unmounts or when the effect's dependencies change.  The cleanup function should stop the interval using `clearInterval`.  See `bugSolution.js` for details.