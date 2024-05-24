# Types

## Strict types ensures quality

**I’m strict about types because:**

- ✅ Types help us code faster.
- ✅ Types help us read faster.
- ✅ Types help us catch mistakes earlier.
- ✅ Types help us assure the app works.

[Source : Cory House](https://twitter.com/housecor/status/1751605094309642753)

## Types saves times

In TypeScript, declaring types saves me more time than it costs me:

- ✅ Speeds up my reading.
- ✅ Catches my errors earlier.
- ✅ Clarifies my mental model.
- ✅ Gives me robust, reliable autocomplete.
- ✅ Avoids me spending time checking docs.
- ✅ Helps me understand my own code later.
- ✅ Reduces the number of tests I need to write.
- ✅ Helps my editor reliably auto-import so I don't have to write imports myself.
- ✅ Gives me the confidence and safety to be able to make large-scale, type-safe refactors.
- ✅ Helps other people understand my code, which speeds up code reviews, reduces the risk of bugs, and accelerates future code changes.

So types don’t just help ensure quality. They save me time

## Repeated prefixes

Group the related fields under an object.

```ts
type Driver = {
  id: string;
  // ❗This infers any combination of these 3 fields is valid.
  // ❗The property name are repetitive.
  // ❗The related fields aren't clearly grouped.
  diversLicenseNumber?: string;
  driversLicenseState?: string;
  driversLicenseExpiration?: date;
};

type Driver = {
  id: string;
  // ✅ Now driver's license is still optional, but all fields are required if it exists.
  // ✅ The property name aren't repetitive.
  // ✅ The related fields are clearly grouped under a well-named object.
  diversLicense?: {
    number: string;
    state: string;
    expiration: date;
  };
};
```

[Source: Cory House](https://twitter.com/housecor/status/1787637488485380347/photo/1)

## Deterministic types

Avoid

```ts
type Response = {
  status: 'success' | 'error';
  data?: string;
  error?: string;
};

// ❌ This type should not be allowed.
const invalidResponse: Response = {
  status: 'success',
  error: 'Something went wrong',
};
```

✅ Prefer

```ts
type Response =
  | { status: 'success'; data: string }
  | { status: 'error'; error: string };

// 💡 is not assignable to type Response
const invalidResponse: Response = {
  status: 'success',
  error: 'Something went wrong',
};
```

This is because the type system can infer the type of the `data` and `error` fields from the value of `status`.

_Also known as discriminated unions._

[Source: Avindra Fernando](https://x.com/avindrafernando/status/1774805301134295106)
