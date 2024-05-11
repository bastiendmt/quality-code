# Review

Code review ensure quality while getting the team familiar with code coming from other people.

## Automated what can be automated

- **Linting**: Checking for common errors and style issues
- **Formatting**: Enable formatting on save
- **Sorting**: Sorting imports

## What to look for in a code review

1. **Robustness**: Is the code secure, accessible, type-safe, and efficient?
2. **Edge cases**: Are error handling, validation, loading states, cancellation, and notifications implemented?
3. **Naming**: Are functions, files, and variables named clearly?
4. **Comments**: Are comments clear and used appropriately?
5. **Reuse**: Are we using existing packages and libraries when possible instead of creating our own? Are we extracting components and functions to eliminate repeated markup and logic? Is existing code being needlessly copy/pasted?
6. **Colocation**: Are related files and functions stored together?
7. **Decomposition**: Are we decomposing big problems into small, clear pieces?
8. **Consistency**: Does the code feel familiar? Does it follow our established standards, patterns, and practices?
9. **Tests**: Are the tests clear, atomic, fast, reliable, and comprehensive?

[Source: Cory House](https://twitter.com/housecor/status/1771885517082140939)

## Approach when wanting to review a code

- "Merge it quickly. We can improve it later."
- "Review it carefully. The code may have bugs. Once it's merged we may not improve it. It's harder to understand later. The patterns in this code may be copied."

Sure, I merge quickly if it's simple and easily reversible.

But generally, I've found developers who favor merge quickly rarely review or improve code after merge.

So "review quickly" often becomes "ship whatever".

[Source: Cory House](https://twitter.com/housecor/status/1788274292926398686)
