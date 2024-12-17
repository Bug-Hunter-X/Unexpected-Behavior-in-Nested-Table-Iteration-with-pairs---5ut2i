# Lua Nested Table Iteration Bug

This repository demonstrates a subtle bug related to the order of iteration in Lua's `pairs` function when dealing with nested tables.

The `bug.lua` file contains code that recursively processes a nested table.  Because `pairs` doesn't guarantee iteration order, the order of processing the nested tables might not be consistent across different Lua versions or implementations. This can lead to unexpected behavior if the code modifies the table during iteration. 

The `bugSolution.lua` file provides a solution demonstrating how to use a different method to ensure consistent iteration order, if that is required.  For many cases, simply ensuring operations within the loop don't modify the table is sufficient.

## How to Reproduce

1. Clone this repository.
2. Run `lua bug.lua`.
3. Observe the output.  Run it multiple times to see the potential variation in output.
4. Run `lua bugSolution.lua` to see the solution.