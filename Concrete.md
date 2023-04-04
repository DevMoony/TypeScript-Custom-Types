## This type is used to make all properties defined in `T` Concrete
### Example:
```ts
export type Concrete<T> = {
    [Property in KeyofType<T>]-?: T[Property];
};

interface I {
    a?: string;
    b?: number;
    c?: bigint;
}

const i: Concrete<I> = {};

i.a; // Concrete
i.b; // Concrete
i.c; // Concrete
```
