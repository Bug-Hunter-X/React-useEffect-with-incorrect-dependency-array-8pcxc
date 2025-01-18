# React useEffect Incorrect Dependency Array

This repository demonstrates a common error in React's `useEffect` hook: using an incorrect dependency array. This can lead to unexpected behavior and bugs.

## The Bug

The `MyComponent` component uses `useEffect` to update the document title with the current count. However, the dependency array only includes `count`. This means the effect only runs when `count` changes and is greater than 0. 

If `count` starts at 0, the title will not be updated even when the component renders and the count changes.  This is a subtle, easily missed issue and can lead to difficult to diagnose behavior.

## The Solution

The solution is to correctly specify the dependencies in the effect's array. In this case, the effect should run every time the `count` changes, regardless of its value. Thus, the dependency array should be `[count]`. Alternatively, removing the conditional check entirely would solve this as well if the goal is to always update the document title based on the count.

## How to Run

1. Clone this repository.
2. Navigate to the directory.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.