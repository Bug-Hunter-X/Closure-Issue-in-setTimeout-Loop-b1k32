# Closure Issue in setTimeout Loop
This repository demonstrates a common JavaScript closure issue encountered when using `setTimeout` within a loop.  The problem arises because of how closures capture variables in JavaScript.

## Bug Description
The `myFunc` function intends to log the numbers 0 through 9 with a one-second delay between each log.  Due to the way closures work with `setTimeout`, however, the loop completes before any of the `setTimeout` callbacks execute.  As a result, by the time the callbacks finally execute, the loop has finished, and the value of `i` is its final value (10).  Therefore, the code incorrectly logs '10' ten times.

## Solution
The solution involves using an Immediately Invoked Function Expression (IIFE) to create a new scope for each iteration of the loop, effectively capturing the current value of `i` for each callback.