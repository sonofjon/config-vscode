---
applyTo: "**"
description: "General programming guidelines for code quality and consistency"
---

# General

1. Only apply the specific changes I explicitly request. In other words: Do
   not introduce any new functionality or stylistic updates beyond my
   instructions.

2. Do not refactor, rename variables, reorder code, delete comments, shorten
   or remove docstrings, or improve formatting, unless I explicitly ask for it.

3. Unless I explicitly tell you that I want you to produce code, you initial
   response should be a discussion of possible solutions to the problem at
   hand.

# Chat

1. When I ask a question about code, you MUST not edit the code; please just
   answer the question.

2. When providing several options for me to choose from please list them
   using unique numbered bullets so that I can refer to them easily.

# Format

1. Use only ASCII punctuation characters. Avoid Unicode punctuation such as
   curly quotes (“ ”), en dashes (–), em dashes (—), ellipses (…), arrows
   (→), bullet points (•), and other non-ASCII symbols. Instead, use
   straight quotes ("), hyphens (-), three periods (...), arrows as '->',
   bullet points as '-', and other standard ASCII punctuation.

2. Do not use emoji characters under any circumstances.

# Programming

## General

1. Ensure lines do not exceed 79 characters.

2. Don't include the data type in variable names, for example a string
   variable containing an address should be named 'address', not
   'addess_str'; a class containing animal types should be named 'Animals',
   not 'AnimalsClass'.

3. Code Consistency: Maintain strict consistency with existing code patterns
   by: (a) using search tools to find similar functions before
   implementation, (b) analyzing their naming conventions, documentation
   style, error handling, and formatting patterns, and (c) verifying that
   new code adhere to the same rules.

## Comments

1. Single sentence comments should not end with a period.

2. When you rewrite or move code, never remove code comments that were
   present in the original code.

## Documentation

1. Always add docstrings when new functions, classes and modules (and other
   constructs) are introduced.

2. The first line of a docstring (the summary line) should
   be a single sentence less than 80 characters long, using imperative mood
   (e.g., 'Return the user's full name.'). Following sentences should use
   third-person present (indicative) (e.g., 'Returns the user's full
   name.').

3. The same rules apply to Git commits.

4. If a README.md or other documentation file exists for the current
   project, always keep it up-to-date with any code changes applied.

## Tests

1. If a test suite exist for the current code project, always keep it
   up-to-date with any code changes applied.

## AI

1. If an instructions, context or memory file (e.g. AGENTS.md, CLAUDE.md,
   GEMINI.md, copilot-instructions.md or similar) exists for the current
   project, always keep it up-to-date with any code changes applied.
