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
Arrays:
```ts
const programmingLanguages:string[] = ["Java", "C++", "Python"];
||
const programmingLanguages:Array<string> = ["Java", "C++", "Python"];
//These two syntaxes are interchangeable
/* Typescript can still infer that is an array of strings but it is best practice to still add it in case we forget to add a number to the array later on.
This way we get a compiler error if we do so */

```
Objects:
```ts
const developer: {firstName: string, isEmployed: boolean} = {
firstName = "Jessica",
isEmployed: true
//Using this syntax won't allow you to remove or add properties to the object. It will throw error

// Property 'isEmployed' is missing in type '{ firstName: string; }' but required in type '{ firstName: string; isEmployed: boolean; }'
const developer: { firstName: string, isEmployed: boolean } = {
  firstName: "Jessica",
}

//You can make certain properties optional with "?" after the property name
const developer: { firstName: string, isEmployed?: boolean } = {
  firstName: "Jessica",
}
```
If you don't know all the properties ahead of time, you can use this syntax:
```ts
//USE RECORD: built-in generic utility type in Typescript
Record<Keys, ValueType> //(types of keys and types of values)

const userRoles: Record<string, string> = {
admin: "full-access",
editor: "limited-access",
viewer: "read-only"
} /*all key name types are strings and their values are strings.
It allows to add or remove properties more freely */
```
OR use and index signature:
```ts
//const obj: {[key: string]: string} = {}

const settings: {[key: string]: string} = {
  theme: "dark",
  language: "en",
  layout: "grid"
}
```
