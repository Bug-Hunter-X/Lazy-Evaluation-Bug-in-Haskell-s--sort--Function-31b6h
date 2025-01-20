# Lazy Evaluation Bug in Haskell's `sort` Function

This repository demonstrates a subtle bug related to lazy evaluation in Haskell's `sort` function. When sorting extremely large lists, the function might not fully evaluate before the result is printed, potentially leading to incorrect sorting.

The `bug.hs` file contains the buggy code, while `bugSolution.hs` provides a corrected version.

## Bug Description

The bug stems from Haskell's lazy evaluation mechanism.  The `sort` function only performs the necessary computations to produce the initial portion of the sorted list requested by the `print` function.  If the list is large, the complete sort might not be done before the output is generated.

## Solution

The solution involves forcing the complete evaluation of the sorted list before printing. This ensures the entire list is sorted before any output is produced.