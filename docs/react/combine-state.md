# Combine state

## Merge useState

Having multiple state can cause issues with incompatible state.

For example we could have an `status` and a `errorMessage` state.

[Source: You don't need useState in React](https://www.nico.fyi/blog/you-dont-need-usestate-in-react)

❌ Avoid

```tsx
const [loading, setLoading] = useState(false);
const [error, setError] = useState(false);
const [success, setSuccess] = useState(false);
```

These states are distinct from each other. When `loading` is true, the `error` and `success` states should be false. Using multiple `useState` hooks can cause unexpected behaviors, like accidentally setting two states to `true` simultaneously.

✅ Prefer

```tsx
type State = 'loading' | 'error' | 'success';

const [state, setState] = useState<State>('loading');
```

Instead, consider using the "finite state machine" (FSM) pattern. A FSM allows only a finite number of states. In the UI example above, a single `useState` can manage the current state more robustly and with less risk of error, as shown here:

## useReducer

[Source: Cory House](https://twitter.com/housecor/status/1645055575909072896)
