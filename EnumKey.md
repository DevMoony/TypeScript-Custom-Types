## This type is used to fetch the keys from an enum defined in `T`.
### Example:

```ts
export type EnumKey<T> = keyof T;

enum Color {
  RED = "Red",
  GREEN = "Green",
  Blue = "Blue"
}

type StandardColors = EnumKey<Color>; // "RED" | "GREEN" | "BLUE"
```
