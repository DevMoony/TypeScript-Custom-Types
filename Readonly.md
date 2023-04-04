**Set Readonly Properties Type**
This type is used to make all properties defined in `T` readonly, except those defined in `P`

```ts
export type ReadonlyProperties<T, P extends KeyofType<T>> = {
    readonly [Property in KeyofType<T>]: T[Property]
} & { -readonly [Prop in P]: T[P] };

// Creating a interface to test the type with
interface I {
    a: string;
    b: number;
    c: bigint;
}

// Creating an example variable to test the assignment
const i: ReadonlyProperties<I, "c"> = {};

i.a = "Aw D:"; // Can't assign as it's Read-Only
i.b = 16; // Can't assign as it's Read-Only
i.c = BigInt(2382398); // Can assign as it's not Read-Only
```
