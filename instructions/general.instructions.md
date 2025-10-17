---
applyTo: "**"
description: "General programming guidelines for code quality and consistency"
---

# General Programming Guidelines

- Ensure lines do not exceed 79 characters.

- Don't include the data type in variable names, for example a string
  variable containing an address should be named 'address', not
  'addess_str'; a class containing animal types should be named 'Animals',
  not 'AnimalsClass'.

- Always add docstrings when new functions, classes and modules (and other
  constructs) are introduced.

- The first line of a docstring (the summary line) should be a single
  sentence less than 80 characters long, using imperative mood (e.g.,
  'Return the user's full name.'). Following sentences should use
  third-person present (indicative) (e.g., 'Returns the user's full name.').

- When you rewrite or move code, never remove code comments that were
  present in the original code.

- Code Consistency: Maintain strict consistency with existing code patterns
  by: (a) using search tools to find similar functions before
  implementation, (b) analyzing their naming conventions, documentation
  style, error handling, and formatting patterns, and (c) verifying that new
  code adhere to the same rules.

- If a test suite exist for the current code project, always keep it
  up-to-date with any code changes applied.
