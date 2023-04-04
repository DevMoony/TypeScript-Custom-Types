## This type is used to find `P` in `T` and return it as a type
### Example:

```ts
export type FindProperty<
    T,
    P extends KeyofType<T>
> = T[P] extends undefined ? unknown : T[P];

interface I {
    a: string;
    b: number;
    c: bigint;
}

let i: FindProperty<I, "c">;

i; // Returns as a bigint type, like defined in c
```
