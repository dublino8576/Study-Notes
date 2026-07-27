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
