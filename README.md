# React Native useRef Async Operation Crash on Unmount

This repository demonstrates a common error in React Native when using the `useRef` hook with asynchronous operations.  The problem arises when a component unmounts before an asynchronous operation (e.g., `setInterval`, `setTimeout`, or a network request) initiated within a `useRef` callback completes.  Attempting to update a component's state or access its properties after unmounting causes unexpected behavior or crashes.

The `bug.js` file contains the buggy code.  The `bugSolution.js` file provides a corrected version that prevents the crash by checking if the component is still mounted before updating the state or accessing its properties.  Always ensure to add cleanup logic in useEffect to avoid this.