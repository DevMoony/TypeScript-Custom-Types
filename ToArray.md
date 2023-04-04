## This type is used to return `T` as an array 
### Example:

```ts
export type ToArray<T> = T extends any ? T[] : never;

interface I {
    a: string;
    b: number;
    c: bigint;
}

let i: ToArray<I>;

i[0].a; // First item of array
i[0].b; // Second item of array
i[0].c; // Third item of array
```
