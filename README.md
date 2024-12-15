# Elixir Enum.each and Process.exit Bug

This repository demonstrates a subtle bug that can occur in Elixir when using `Enum.each` in conjunction with `Process.exit`.  The `Process.exit` call within the `Enum.each` function unexpectedly terminates the entire process, rather than just the current iteration.

## The Bug
The provided Elixir code uses `Enum.each` to iterate over a list. Inside the loop, an `if` statement checks for a specific value (3 in this case). If the value matches, `Process.exit` is called, causing the entire process to terminate prematurely. This behavior is counterintuitive and can be difficult to debug.

## Solution
The solution avoids using `Process.exit` directly within the enumeration.  Instead, it utilizes a more appropriate method for controlling process termination and handles the exit condition gracefully.