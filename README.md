# React Native AsyncStorage: Inconsistent Data Retrieval

This repository demonstrates a common bug in React Native applications using AsyncStorage. The issue stems from attempting to read data from AsyncStorage before the write operation is fully completed. This asynchronous behavior can lead to inconsistent data retrieval and debugging challenges.

## Problem
The `bug.js` file showcases the problem.  The component attempts to store data in AsyncStorage and immediately retrieves it. Due to the asynchronous nature of AsyncStorage, the read operation might complete before the write, resulting in null or unexpected values. This inconsistency can be hard to detect and reproduce reliably.

## Solution
The `bugSolution.js` file provides a solution using Promises and `then()` to ensure the write operation completes before the read begins. This guarantees consistent data retrieval.  This approach makes the data flow more predictable and avoids the race condition that causes the bug.

## How to reproduce
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run the app (instructions may vary depending on your React Native setup).
4. Observe the inconsistent behavior in `bug.js`.
5. Compare with the consistent results of `bugSolution.js`.