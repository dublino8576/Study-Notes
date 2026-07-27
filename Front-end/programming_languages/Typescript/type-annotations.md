# Type Annotation

## For Primitive Data Types
```ts
let firstName: string = "Angie" //accepts only strings
let age: number = 16 //accepts only numbers/floats but not bigint(large number syntax)
let isLoggedIn: boolean = true //accepts only boolean
let isAdmin: boolean = false
//they can be reassigned only to the same data type
```
If type annotation is simple, Typescript can infer it by seeing the syntax of the value stored so we just type
```ts
let firstName = "Angie"
```
Undefined and null are special cases explained with functions, further ahead.

## For Arrays and Objects
```ts
const programmingLanguages:string[] = ["Java", "C++", "Python"];
||
const programmingLanguages:Array<string> = ["Java", "C++", "Python"];
//These two syntaxes are interchangeable
*Typescript can still infer that is an array of strings but it is best practice to still add it in case we forget to add a number to the array later on.
This way we get a compiler error if we do so*

```

