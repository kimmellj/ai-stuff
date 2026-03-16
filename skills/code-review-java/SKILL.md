---
name: code-review-java
description: Performs a full code review of Java code covering correctness, security, and maintainability. Invoke with /code-review-java.
---

Review the current git diff (`git diff`) or, if there are no unstaged changes, the last commit (`git show HEAD`). Work through all three areas below and write up your findings as a checklist. 
Group issues by area, lead with the most important problems, and be direct about what needs fixing and why.

If there are no issues in an area, say so briefly and move on.

**Correctness & Logic**

Does the code actually do what it's supposed to do?
- Does the implementation match the intent — no missing branches, no off-by-one errors, no silent failures?
- Are nulls, empty collections, and boundary values handled?
- Are return types and error states consistent throughout?
- Do database operations handle transactions and rollbacks correctly?
- Are integration points (external calls, events, queues) handled defensively?

**Security & Error Handling**

Could this code be exploited or leak data?
- Is all input validated at system boundaries — nothing trusted that comes from outside?
- Are queries parameterized — no string concatenation into SQL or similar?
- Is output escaped appropriately to prevent injection?
- Are authentication and authorization enforced at every relevant entry point?
- Are secrets sourced from environment/config — never hardcoded?
- Are errors caught and handled without leaking stack traces or sensitive data to the caller?
- Do any new dependencies have known CVEs worth flagging?

**Maintainability & Performance**

Will the next developer (or you in six months) be able to understand and change this?
- Are names meaningful — classes, methods, and variables should say what they are and do?
- Does each class and method have a single, clear responsibility?
- Is Javadoc present and thorough on all public classes and methods? Verbose documentation is expected — brief or missing docs are a problem.
- Are magic numbers and strings extracted to named constants?
- Does the code follow the same patterns and conventions already established in the codebase — formatting, structure, naming style? Inconsistencies should be called out.
- Is there unnecessary duplication that should be extracted?
- Are there any obvious performance concerns — N+1 queries, unbounded loops, missing indexes implied by the logic?
- Is the code testable? Are there any untested paths that should have coverage?
- Are there orphaned TODOs or commented-out code that shouldn't be there?
