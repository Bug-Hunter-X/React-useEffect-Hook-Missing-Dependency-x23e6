# React useEffect Hook Missing Dependency

This example demonstrates a common error in React applications: a missing dependency in the `useEffect` hook.  The `useEffect` hook runs after every render.  If it depends on values outside of its dependencies array it will lead to unexpected behavior and potentially an infinite render loop.

**Bug:** In the `MyComponent` component, the `useEffect` hook logs a message after every render. However, it only includes `count` in the dependency array. This means that even if the `setCount` function changes the state internally and causes a re-render, the `useEffect` will not re-run and log the message.

**Solution:** Add `setCount` to the dependency array.