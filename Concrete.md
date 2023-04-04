## This type is used to make all properties defined in `T` Concrete
### Example:
```ts
export type Concrete<T> = {
    [Property in keyof T]-?: T[Property];
};

interface I {
    a?: string;
    b?: number;
    c?: bigint;
}

let i: Concrete<I>;

i.a; // Concrete
i.b; // Concrete
i.c; // Concrete
```
