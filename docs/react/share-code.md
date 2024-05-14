# Share code

3 ways to share code in React:

Problem: Two components have different logic, but nearly identical JSX.
Solution: Create a reusable component that contains only the JSX.

Problem: Two components have the same logic, but different JSX.
Solution: Create a reusable hook that contains the shared logic. Call the hook in both components.

Problem: Two components have similar logic and JSX.
Solution: Unify the components. Add props to handle the differences.

Summary:
Repeated logic? Use a hook.
Repeated markup? Create JSX-only component.
Repeated logic and markup? Create a component.

[Source: Cory House](https://twitter.com/housecor/status/1745435403715223704)
