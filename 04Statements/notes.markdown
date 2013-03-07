Notes for Chapter 4: Statements
===============================

- Lua allows multiple assignment, which assigns a list of values to a list of
  variables in one step, both lists have their elements seperated my commas
- Lua first evaluates all values and only then executes the assignments
  (allowing us to swap two variables with multiple assignment)
- When there are more variables than values, they are filled with `nil`s
- When there are more values than variables, they are silently discarded
- A frequent use of multiple assignment is to collect multiple returns from
  function calls
- Lua supports local variables with the keyword `local <variable name>`
- In interactive mode, local variables don't work as expected because every
  line is executed in it's own chunk
- To make local variables work in interactive mode, their use needs to be put
  into a do-end block
- Access to local variables is faster than to global ones
- A common idiom in Lua is `local foo = foo`, which creates a local variable
  `foo` assigns the global variable `foo` to it
- Lua supports if-then-[[elseif-then]-else]-end, while-do, repeat-until,
  numeric for and generic for control structures
- Numeric for starts at a given start value and ends at a given end value
  using the steps provided: `for <var> = <start>, <end>, [<step=1>] do...`
- The value of the control variable should never be changed (use `break` to
  prematurely exit the loop)
- The generic for traverses all values returned by an iterator function, like
  so: `for k, v in pairs(t) do...`
- There are several iterators: `pairs()` to traverse a table, `io.lines()` to
  iterate over the lines of a file, `ipairs()` to iterate over the entries of a
  sequence, `string.gmatch()` to iteratre over words in a string and so on
- A return statement can only appear as the last statement of a block
- Lua supports `goto` and labels, they are declared with `::labelname::` and can
  be jumped to with `goto labelname`
- You cannot jump into a block or out of a function and you cannot jump into
  the scope of a local variable
- The scope of a local variable ends on the last non-void statement of the
  block where the variable is defined, labels are considered void statements
- Gotos can be used to emulate functionality like `continue`