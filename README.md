# Silent Failure of @apply with Undefined Classes in Tailwind CSS

This repository demonstrates a subtle but frustrating bug in Tailwind CSS involving the `@apply` directive. When `@apply` attempts to use a class that is not defined, it silently fails instead of throwing an error. This makes debugging significantly harder, as there's no obvious indication that the class application has failed.

## Problem
The primary problem lies in the lack of clear error reporting when an undefined class is used with `@apply`.  Existing Tailwind error handling doesn't catch these cases effectively.  This can lead to wasted time tracking down why styles aren't being applied as expected.

## Solution
Implementing robust checks within custom directives and plugins to ensure all classes used in `@apply` statements exist and are correctly defined.  Thorough testing is crucial to prevent this issue.

## Reproduction Steps
1.  Clone this repository.
2.  Run `npm install`.
3.  Observe that the styles in `bug.css` do not apply as expected due to the `@apply` directive's silent failure.  Note there is no error message indicating the class is missing.
4.  Compare to `solution.css` to see how to avoid this issue. 

## Recommendation
Always verify the existence of classes used with `@apply` to avoid unexpected styling errors. Consider creating a utility function to assist with this task.