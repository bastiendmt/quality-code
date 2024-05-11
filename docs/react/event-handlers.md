# Event Handlers

React tip: Avoid extracting event handlers to separate functions if they're only called once.

Benefits of declaring inline:
✅ Less code
✅ Automatic TypeScript types
✅ The reader doesn't have to jump around
✅ Clarifies to the reader that it's not reusable logic

```tsx
// Avoid
const handleClick = () => {
  // Do something
}

<button onClick={handleClick}>Click me</button>

// Prefer
<button onClick={() => {
  // Do something
}}>Click me</button>
```

This avoid creating a layer of abstraction that is not needed.

## When to use

- When the event handler is only called once
- When the event handler provides no additional value. Like `handleClick` is not descriptive.

## When not to use

- When the event handler is called multiple times
- When the event handler contains multiple lines of code

[Source: Cory House](https://twitter.com/housecor/status/1649876292618055681)
