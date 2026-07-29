# Type Annotation

Typescript has a type-system. When it sees a variable it reduces it as a type on top of all the features that normal JavaScript offers.

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
OR use an index signature:
```ts
//const obj: {[key: string]: string} = {}

const settings: {[key: string]: string} = {
  theme: "dark",
  language: "en",
  layout: "grid"
}
```

### Interface Declaration
Interface accepts all JavaScript primitive data-types plus: 
1. *any* >> allow anything
2. *unknown* >>  sibling to *any*, allows the definition of type to be specified by someone when using this data (eg. The user receiving JSON data needs to declare and decide the type when calling the API)
```ts
//Server side
const jsonParserUnknown = (jsonString: string): unknown => JSON.parse(jsonString);
const myOtherAccount = jsonParserUnknown(`{ "name": "Samuel" }`);
myOtherAccount.name;

//Client side
type User = { name: string };
const myUserAccount = jsonParserUnknown(`{ "name": "Samuel" }`) as User;
myUserAccount.name;
```
3. *never* >> this specific type cannot happen
4. *void* >> a function that returns *undefined* or has no return value
```ts
//Declare first interface and then type the object like in JavaScript
interface User {
  name: string;
  id:number;
}

const user: User = {
  name: "Hayes",
  id: 0,
};
//ERROR SHOWN when adding more properties >> Object literal may only specify known properties, and 'username' does not exist in type 'User'.
```
#### Classes
```ts
// You can use interface declaration with classes too since Typescripts supports OOP and classes like JavaScript
interface User {
  name: string;
  id: number;
}
 
class UserAccount {
  name: string; //declares class keys and their type
  id: number;
 
  constructor(name: string, id: number) {
    this.name = name;
    this.id = id;
  }
}
 
const user: User = new UserAccount("Murphy", 1); //each UserAccount instance that claims to be a User must follow the interface definition
```
