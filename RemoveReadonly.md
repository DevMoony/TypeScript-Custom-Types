## Removes the properties defined in `P` from `T` to be readonly, other properties will be ignored
### Example

```ts
export type ReduceReadonly<T, P extends KeyofType<T>> = {
    -readonly [Property in P]: T[Property];
} & { [Property in keyof T]: T[Property] };

// Creating a interface to test the type with
interface I {
    readonly a: string;
    readonly b: number;
    readonly c: bigint;
}

// Creating an example variable to test the assignment
let i: ReduceReadonly<I, "c">;

i.a = "Aw D:"; // Can't assign as it's Read-Only
i.b = 16; // Can't assign as it's Read-Only
i.c = BigInt(2382398); // Can assign as it's not Read-Only
```
