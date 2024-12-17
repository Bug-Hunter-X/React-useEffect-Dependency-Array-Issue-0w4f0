# React useEffect Dependency Array Issue

This repository demonstrates a common error in React's `useEffect` hook: forgetting to include state variables in the dependency array.  This can lead to unexpected behavior and performance issues.

The `bug.js` file contains the faulty code. The `bugSolution.js` file provides the corrected version.

## Problem

The `useEffect` hook in `bug.js` is intended to log the current count to the console. However, because `count` is not listed in the dependency array, the effect runs after every render, regardless of whether the `count` value has changed.  This creates unnecessary console logs and could cause other side effects if the effect was performing more complex tasks.

## Solution

`bugSolution.js` corrects this by adding `count` to the dependency array. Now the effect will only run when the value of `count` changes.