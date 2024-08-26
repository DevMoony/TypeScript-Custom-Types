## This type extracts the keys of a nested object type defined in `T` and returns the keys of the defined object.
### Example:
```ts
export type InnerKeys<T extends any> = T extends Record<string, infer U> ? keyof U : never;
```
