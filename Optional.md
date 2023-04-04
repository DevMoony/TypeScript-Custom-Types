## This type is used to make all properties defined in `T` optional, except those defined in `P`
### Example:
```ts
export type Optional<T, P extends KeyofType<T>> = {
    [Property in KeyofType<T>]?: T[Property];
} & { [Property in P]-?: T[P]; };

interface I {
    a: string;
    b: number;
    c: bigint;
}

const i: Optional<I, "c"> = {};

i.a; // Optional
i.b; // Optional
i.c; // Concrete
```
#### P.S.: Properties defined in `P` also work if the properties in `T` are already Concrete
