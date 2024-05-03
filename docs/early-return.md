# Early return / guard clauses

Guard clauses are one of the most useful tools we have to fight complexity at a granular level and they’ve become my favorite technique to simplify an implementation.

Early return have multiple advantages :

- avoid nesting if statements
- reduce the number of lines of code.
- avoid long blocks of code to then find a else statement
- easier to maintain

## Example

### Don't ❌

```js title="welcomeUser.js"
if (!isLoading) {
  if (!error) {
    if (user) {
      return `Hello ${user.name} !`;
    }
  } else {
    return 'an error occurred';
  }
} else {
  return 'loading...';
}
```

### Do ✅

```js title="welcomeUser.js"
if (isLoading) {
  return 'loading...';
}
if (error) {
  return 'an error occurred';
}
if (user) {
  return `Hello ${user.name} !`;
}
```

The goal of our function is to greet the user. In the "Do" example, even though we first handle the edge cases, it results in a cleaner code.

We could even remove the brackets for shorter syntax :

```js title="welcomeUser.js"
if (isLoading) return 'loading...';
if (error) return 'an error occurred';
if (user) return `Hello ${user.name} !`;
```

<!-- Add long blocks of code to then find a else statement -->

### Example with React code

```tsx
export default function PromptContent({ prompt }) {
  return prompt.answered ? (
    <AnswersList answers={prompt.answers} />
  ) : (
    <AnswerForm />
  );
}
```

A ternary is essentially a shorthand `if-else` statement and one good design approach is to avoid writing `else` statements at all.

```tsx
export default function PromptContent({ prompt }) {
  if (!prompt.answered) {
    return <AnswerForm />;
  }
  return <AnswersList answers={prompt.answers} />;
}
```

By inverting the condition and pulling it up, we check the faulty state and keep the golden path on the base level of indentation. This conditional statement “guards” the rest of the logic from errors and is known as a “guard clause”.
