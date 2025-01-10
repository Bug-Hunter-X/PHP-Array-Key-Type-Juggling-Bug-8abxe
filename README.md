# PHP Array Key Type Juggling Bug

This repository demonstrates a subtle bug in PHP related to how it handles array keys and type juggling.  The bug arises when an array key, which is not an integer but evaluates to zero (0) when cast to an integer, leads to unintended overwriting of array elements.

The `bug.php` file contains the buggy code. The `bugSolution.php` file shows a corrected version.

## How to Reproduce

1. Clone this repository.
2. Navigate to the repository's directory in your terminal.
3. Run `php bug.php`.
4. Observe the unexpected output.
5. Run `php bugSolution.php` and observe the expected output.

## Bug Explanation

The bug occurs because PHP performs type juggling when working with array keys.  If a key is not an integer, PHP attempts to convert it to an integer.  When the resulting integer value is 0, it causes the new value to overwrite an element that may already exist at the numeric index 0.

## Solution

The solution involves ensuring that the keys you use are explicitly strings if it is intended to create a string based key or use a different data structure for handling that specific scenario if appropriate.