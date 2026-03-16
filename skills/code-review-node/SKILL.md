---
name: code-review-node
description: Performs a full code review of Node.js code covering correctness, security, and maintainability. Invoke with /code-review-node.
---

Review the current git diff (`git diff`) or, if there are no unstaged changes, the last commit (`git show HEAD`). Work through all three areas below and write up your findings as a checklist. 
Group issues by area, lead with the most important problems, and be direct about what needs fixing and why.

If there are no issues in an area, say so briefly and move on.

**Correctness & Logic**

Does the code actually do what it's supposed to do?
- Does the implementation match the intent — no missing branches, no unhandled promise rejections, no silent failures?
- Are nulls, undefined values, empty arrays, and boundary values handled?
- Is async/await used correctly — no floating promises, no missing awaits?
- Are return types and error states consistent throughout?
- Are integration points (external API calls, events, queues, DB) handled defensively?

**Security & Error Handling**

Could this code be exploited or leak data?
- Is all input validated at system boundaries — nothing trusted that comes from outside?
- Are queries parameterized — no string interpolation into SQL or NoSQL queries?
- Is output escaped appropriately to prevent XSS or injection?
- Are authentication and authorization enforced at every relevant route or entry point?
- Are secrets sourced from environment variables — never hardcoded or committed?
- Are errors caught and handled without leaking stack traces or sensitive data to the caller?
- Do any new `npm` dependencies have known CVEs worth flagging, or are they pulling in an unreasonable dependency tree?

**Maintainability & Performance**

Will the next developer (or you in six months) be able to understand and change this?
- Are names meaningful — modules, functions, and variables should say what they are and do?
- Does each module and function have a single, clear responsibility?
- Is JSDoc present and thorough on all exported functions and modules? Verbose documentation is expected — brief or missing docs are a problem.
- Are magic numbers and strings extracted to named constants?
- Does the code follow the same patterns and conventions already established in the codebase — formatting, structure, naming style? Inconsistencies should be called out.
- Is there unnecessary duplication that should be extracted?
- Are there any obvious performance concerns — N+1 queries, unbounded loops, synchronous operations blocking the event loop?
- Is the code testable? Are there any untested paths that should have coverage?
- Are there orphaned TODOs or commented-out code that shouldn't be there?
