# React 19 useEffect Infinite Loop Bug
This repository demonstrates a common error in React 19's `useEffect` hook: an infinite loop caused by a missing dependency in the dependency array.  The bug involves an effect that triggers a state update without including that state in the dependency array, leading to continuous re-renders.

## Bug Description:
The `MyComponent` renders indefinitely due to a missing dependency in the `useEffect` hook's dependency array.  The effect runs after every render, triggering a state update and restarting the cycle. This occurs because the `count` variable is used within the `useEffect` but is not specified as a dependency. 

## Solution:
The solution involves adding `count` to the dependency array.  By doing this, the `useEffect` hook only runs when `count` changes.