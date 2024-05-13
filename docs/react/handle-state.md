# Handle state in React

| Name                | When to use it                               |
| ------------------- | -------------------------------------------- |
| URL                 | Sharable app location                        |
| Web storage         | Persistent between sessions, one browser     |
| Local state         | Only one component needs the state           |
| Lifted state        | A few related components need the state      |
| Derived state       | State can be derived from existing state     |
| Refs                | DOM reference, state that isn't rendered     |
| Context             | Global or subtree state                      |
| Third party library | Global state, Remote sate (redux or zustand) |

## Derived state

Derived state is state that is derived from other state.
For example, if you have a `firstName` and a `lastName` state,
you can derive a `fullName` state from them.

❌ Avoid

```tsx
const [firstName, setFirstName] = useState('');
const [lastName, setLastName] = useState('');
const [fullName, setFullName] = useState('');
```

✅ Prefer

```tsx
const [firstName, setFirstName] = useState('');
const [lastName, setLastName] = useState('');
const fullName = `${firstName} ${lastName}`;
```
