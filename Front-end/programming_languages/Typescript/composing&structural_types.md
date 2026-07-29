## Composing Types
Creates *complex types* by combining simple ones.

### Unions
A type that could have a finite and defined number of options within that type:
```ts
type MyBool = true | false // this is a boolean that can be either true or false
type WindowStates = "open" | "closed" | "minimized"; //any of these strings
type LockStates = "locked" | "unlocked"; //any of these strings
type PositiveOddNumbersUnderTen = 1 | 3 | 5 | 7 | 9; //any of these numbers
```
They are a popular choice to define arguments types for functions:
```ts
function getLength(obj: string | string[]) {
  return obj.length
}
```
#### Typeof
You can make a function return different values depending on what type of data is passed in the function
```ts
function wrapInArray(obj: string | string[]) {
  if (typeof obj === "string") {
    return [obj]; //(parameter) obj: string
  }
  return obj;
}
```

### Generics
You can save your own specific types into variables with *generics*. Useful non-primitive data types
```ts
//everytime we use these variables, we intend their assigned type value
type StringArray = Array<string>; 
type NumberArray = Array<number>;
type ObjectWithNameArray = Array<{ name: string }>;
```

You can use generics with interface as follows
```ts
interface Backpack<Type> {
  add: (obj: Type) => void;
  get: () => Type;
}
 
// This line is a shortcut to tell TypeScript there is a
// constant called `backpack`, and to not worry about where it came from.
declare const backpack: Backpack<string>;
 
// object is a string, because we declared it above as the variable part of Backpack.
const object = backpack.get();
 
// Since the backpack variable is a string, you can't pass a number to the add function.
backpack.add(23);
/*!Argument of type 'number' is not assignable to parameter of type 'string'.!*/
```

## Structural Type System
Typescripts focuses here at the shape that the values have, so no need to be explicit when assigning a variable to that type:
```ts
interface Point {
  x: number;
  y: number;
}
 
function logPoint(p: Point) {
  console.log(`${p.x}, ${p.y}`);
}
 
// logs "12, 26"
const point = { x: 12, y: 26 };
logPoint(point);
```
The code above passes because the constant variable *point* has the same *shape* as the interface *Point*.
Typescripts infers this for us using this system of checking shape
