# React useEffect Memory Leak: Missing Cleanup Function

This repository demonstrates a common error in React's `useEffect` hook: forgetting to include a return statement for cleanup. This can lead to memory leaks, especially when dealing with asynchronous operations like fetching data.

The `bug.js` file shows the problematic code, while `bugSolution.js` presents the corrected version.

**Problem:**
The `useEffect` hook in `bug.js` fetches data from an API, but lacks a return statement to properly clean up after itself.  This can cause problems if the component unmounts before the fetch completes, potentially leading to memory leaks and/or unexpected behavior.

**Solution:**
The `bugSolution.js` file corrects this by including a return statement within `useEffect`. The return statement contains a cleanup function that will abort any pending requests when the component unmounts.

This example highlights the importance of proper cleanup in `useEffect` for reliable and efficient React applications.