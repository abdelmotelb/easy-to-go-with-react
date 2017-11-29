# React Tutorial
This is a Simple React Tutorial for all who to build web apps using React


## Table of Contents

  - [Prerequisites](#prerequisites)
  - [Setup](#setup)
  - [Tutorial Map](#tutorial-map)
  - [Quick Look at ES6](#quick-look-at-es6)
    - [let](#let)
    - [const](#const)
    - [Arrow Functions](#arrow-functions)
    - [Default Parameters](#default-parameters)
    - [String Interpolation](#string-interpolation)
    - [Modules](#modules)
  - [Why React](#why-react)
  - [Big Picture](#big-picture)
  - [Virtual DOM](#virtual-dom)
  
  
## Prerequisites
In order to go ahead with this tutorial, You should have good knowledge about the following

- [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)


## Setup

We will use in this tutorial the simple and easy method to create react app called `create-react-app` package
1. Install `create-react-app` NPM package globally
```
 npm i -g create-react-app
```   
2. Create your app
```
 create-react-app your-project-name
 
 cd your-project-name
 
 yarn install
```
3. Start your app
```
 yarn start
```

You can visit [Create React App](https://github.com/facebookincubator/create-react-app) for more info.

## Tutorial Map
![Tutorial Map](https://user-images.githubusercontent.com/11356226/33302591-e89a294a-d405-11e7-9485-cbffc33b79a5.png)

## Quick Look at ES6
We will take here a quick on the new features on EchmaScript 6.

### let
We all know that declaring variable with `var` makes theis variable available only on the function scope that it has been declared in. But with `let` every `{ }` consider a scope so any variable that declared with `let` will available only on this curly braces scope.

> Example using `var`:
```javascript
if (true) {
   var x = 5
}
console.log("using var: ", x)
```
it will result: ` using var: 5 `

> Example using `let`:
```javascript
if (true) {
   let x = 5
}
console.log("using let: ", x)
```
it will result:  `ReferenceError: x is not defined`

So `let` make a scope within `if` statement curly braces and `var` don't.

### const
`const` almost used to daclare any variables that will not changed or in accurate say you will not assign it a new value using `=` because when you declare a composite typed variable like objects or arrays you can add or remove elements to or from it normally but you can't asign to the variable another value.

```javascript
const x = [1, 2, 3]
x.push(4)       // x will now be [1, 2, 3, 4]
                // but
x = [1, 4, 6]   // It will raise TypeError: Assignment to constant variable
```

### Arrow Functions
Arrow Functions is a special type of functions that solve the problem of `this` keyword strange behavior when calling function from a context other than its own one ( it's not strange if you know how it works :smile: ) and convert it to Lexical `this` so that it maintains that the context that call it will be the reference `this`.

Examples on How to write it:
```javascript 
// Shorthand arrow functions with returned expression
const expressionFn = (x, y) => x + y;

// Statement Arrow Functions
const statementFn = (x, y) => {
  if (x && y) {
    return x + y
  }
  return false
}
```

### Default Parameters
EcmaScript6 added the ability to add default values to the given parameters if it's not be provided to the function. And that's for sure make the code more readable and organizable.

Here is an example 
```javascript 
function doSum (x, y = 7, z = 12) {
 return x + y + z;
}

doSum(2)         // output: 21
doSum(2,4)       // output: 18
doSum(2,4,10)    // output: 16
```
> Note: You must make function default parameters the last parameters of it in arrangement or assign its value to `undefined` when calling the function but that will be little confusing
```javascript
function doSum (x, y = 7, z) {
 return x + y + z;
}

doSum(2,undefined,6)       // output will be 2 + 7 + 6 = 15 
```

### String Interpolation
String Interpolation give the ability to write more readable and organized strings without need to use `+` operator to concatenate the string typed variables with each other.

Here is an example for that

```javascript
const firstName = 'Ahmed'

const lastName = 'Moawad'

let fullName = 'Full Name is ' + firstName + ' ' + lastName        // The old way

fullName = `Full Name is ${firstName} ${lastName}`                 // New String Interpolation

// Result for both: Full Name is Ahmed Moawad
```

### Modules
This is a big new feature and all JavaScript was waiting for releasing it to make your code more modular and organized. There is three points that we will talk about for this feature:

#### 1. Exporting
> In order to make class, function or any variable inside a file (module) available in other files (modules) we use module exporting, and here are some examples for how to do that:

```javascript
/**
* @file index.js 
*/

// Exporting Function
export function getFullName(firstName, lastName) { 
   return `${firstName} ${lastName}` 
}

// Exporting variable
export const title = "Frontend Engineer"

```

#### 2. Importing
> In order to import class, function or any type of variable inside a file (module) to be able to use it in this file we use module importing, and here are some examples for how to do that:

```javascript
/**
* @file about.js 
*/

// Import getFullName function and title variable from index module
import { getFullName, title } from 'index'

// Use them
const fullName = getFullName('Ahmed', 'Moawad')

console.log(`My Name is ${fullName} and I'm ${title}`)

// Result: My Name is Ahmed Moawad and I'm Frontend Engineer

```

#### 3. Default Exporting
> This is an awesome feature in order to make any kind of variables the default one when exporting to other modules. Here is an example that will explain it's functionality in more details:

```javascript
/**
* @file index.js 
*/

/*
* .... brevious code
*/

// Export the following Object as the default export for index module
export default {
 firstName: 'Ahmed',
 lastName: 'Moawad',
 title: 'Frontend Engineer'
}


/**
* @file about.js 
*/

// Import Default without the curly braces and with any name you choose for it
import myData, { getFullName } from index

const fullName = getFullName(myData.firstName, myData.lastName)

console.log(`My Name is ${fullName} and I'm ${myData.title}`)

// Result: My Name is Ahmed Moawad and I'm Frontend Engineer

```

### Why React

### Big Picture

### Virtual DOM
