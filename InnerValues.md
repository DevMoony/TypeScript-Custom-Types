## This type extracts the values of a nested object type defined in `T` and returns them of the defined object.
### Example:
```ts
export type InnerValues<T extends any> = T extends Record<string, infer U> ? U : never;
```
