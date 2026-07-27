# Differences with JavaScript

Typescript differs from JavaScript primarily because it is not a *dynamic* programming language, it does not allow to receive any data at compile time. 

It is a *static* programming language, which needs and accepts only a particular type of data otherwise it won't run.

Typescript introduces *compiler errors* for when a different data type is passed on a variable at run time.

Javascript: 
```
const getRandomValue = (array) => {
  return array[Math.floor(Math.random() * array.length)];
} //results undefined if a number is passed in the function instead of an array but it runs
```

Typescript:
```
const getRandomValue = (array: string[]) => {
  return array[Math.floor(Math.random() * array.length)];
} //returns compiler error if passing in the function something else than an array of strings
```

Typescript comes with a built-in compiler that translates it to Javascript in order to run on browsers or Node.js
