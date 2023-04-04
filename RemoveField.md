## This type is used to remove the field specified in `P` from `T`
### Example:

```ts
export type RemoveField<T, K extends KeyofType<T>> = {
    [Property in KeyofType<T> as Exclude<Property, K>]: T[Property];
};

interface I {
    a: string;
    b: number;
    c: bigint;
}

let i: RemoveField<I, "c">;

i.a; // Property exists
i.b; // Property exists
i.c; // Property removed by type
```
