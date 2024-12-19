# React setInterval Memory Leak

This repository demonstrates a common error in React components: using `setInterval` within `useEffect` without proper cleanup.  This can lead to memory leaks and unexpected behavior.

The `bug.js` file contains the flawed component. The `bugSolution.js` file shows the corrected version.

**Problem:** The `setInterval` function continues running indefinitely, even after the component unmounts. This creates a memory leak because the interval continues to update the state, even when the component is no longer rendered. 

**Solution:** The corrected version uses the return value of `useEffect` to clear the interval when the component unmounts, preventing the memory leak.