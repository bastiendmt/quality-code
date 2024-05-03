# Duplication

Problem: “Duplication is often better than the wrong abstraction”.

Solution: I typically abstract via small, focused, pure functions.

A pure function is simple:

- ✅ Doesn’t mutate args.
- ✅ Doesn’t rely on outside state.
- ✅ No side-effects. Always returns the same output for a given input.
- ✅ Easy to test.

So, a pure function is easy to tweak later if my abstraction isn’t quite right.

[Source : Cory House](https://twitter.com/housecor/status/1785305853567947165)
