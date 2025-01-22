# Unnecessary Re-renders in React 19 useEffect Hook

This repository demonstrates a common issue in React 19 applications where the `useEffect` hook causes unnecessary re-renders. The example showcases how an effect with no dependencies re-renders after every render, leading to performance problems.

## Problem

In React 18 and earlier, placing an empty dependency array `[]` in `useEffect` meant the effect would only run once on mount.  However, in React 19, if you omit the dependency array, the effect will run on every render, which is inefficient and can cause performance degradation in complex components.  This is a change from the previous behavior, potentially leading to unexpected behavior in existing codebases. 

## Solution

To ensure the effect only runs when necessary, explicitly specify the dependencies within the dependency array.  If you want to run the effect only once on mount and unmount, use an empty array (`[]`). If you need to track changes to particular values, add those values as dependencies.
