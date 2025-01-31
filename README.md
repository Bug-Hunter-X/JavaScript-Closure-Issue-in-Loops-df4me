# JavaScript Closure Issue in Loops

This repository demonstrates a common error in JavaScript involving closures within loops.  The example shows how using `let` in the loop does not prevent the closure issue, leading to unexpected output. The solution demonstrates a simple fix using an immediately invoked function expression (IIFE) to capture the value of `i` in each iteration.

## Bug

The provided `bug.js` file contains a function that uses a `for` loop and `setTimeout`.  Due to the nature of closures in JavaScript, the `console.log(i)` statement inside `setTimeout` always accesses the final value of `i` after the loop has completed. This results in '10' being logged 10 times instead of 0 to 9.

## Solution

The `bugSolution.js` file provides a solution by using an IIFE to create a new scope for each iteration of the loop, thereby capturing the correct value of `i`. This correctly logs the values 0-9.