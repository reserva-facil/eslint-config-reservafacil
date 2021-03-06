This module allow you to check patterns on .js files using [ESLINT](https://eslint.org/)

## Install

```sh
npm i eslint-config-reservafacil eslint
```

## Usage

In root of your project, create a file `.eslintrc` and define:

```json
{
    "extends": "reservafacil"
}
```

## Pattern

We use actively es6 and es7, below you can find descriptions and examples about each rule we follow.

- [semi](#semi)
- [curly](#curly)
- [brace-style](#brace-style)
- [quotes](#quotes)
- [prefer-template](#prefer-template)
- [object-curly-spacing](#object-curly-spacing)
- [array-bracket-spacing](#array-bracket-spacing)
- [space-infix-ops](#space-infix-ops)
- [no-var](#no-var)
- [strict](#strict)
- [no-undef](#no-undef)
- [no-unused-vars](#no-unused-vars)
- [block-scoped-var](#block-scoped-var)
- [camelcase](#camelcase)
- [eol-last](#eol-last)
- [new-cap](#new-cap)
- [eqeqeq](#eqeqeq)

### semi

The actual minifiers can work totally without require to you write semicolons. So to help write a cleaner code, avoid use of semicolons.

```js
// right
console.log('lorem')
console.log('lorem 2')

// wrong
console.log('lorem');
console.log('lorem 2');

// wrong
console.log('lorem'); console.log('lorem 2');
```

### curly

Sometimes we forget, or dont know about scope of conditionals in javascript without curly. To avoid confusion, always write using curly.

```js
// right
if (condition) {
  console.log('lorem') // instruction1
  console.log('lorem') // instruction2
}

// wrong
if (condition)
  console.log('lorem') // instruction1 will be executed if condition is true
  console.log('lorem') // instruction2 always be executed, but looks like not
```

### brace-style

We use use the below format, for one reason, help fold and unfold scopes in code editors and IDE's.

```js
// right
if (condition) {

}

// wrong
if (condition)
{

}

// wrong
if (condition) {}
```

### quotes

Simple quotes is more clean and confortable to type in keyboard.

```js
// right
'lorem'

// wrong
"lorem"
```

### prefer-template

Interpolate instead concat strings, is more clean.

```js
// right
`Hello ${name}!`

// wrong
"Hello, " + name + "!"
```


### object-curly-spacing

Without space is more clean.

```js
// right
{name: 'lero'}
const {foo, bar} = object

// wrong
{ name: 'lero' }
const { foo, bar } = object
```

### array-bracket-spacing

Without space is more clean.

```js
// right
[name: 'lero']
const [foo, bar] = array

// wrong
[ name: 'lero' ]
const [ foo, bar ] = array
```

### space-infix-ops

In operations, is more clean use spaces between operators

```js
// right
10 + 10 * 3

// wrong
10+10*3
```

### no-var

In the future, `var` will be deprecated. In es6, we have `let` as substitute.
And variables can be changed on run time. So use `const` always that you can, to be more secure.

```js
// right
const name = 'lero'

// right
let name

if (condition) {
  name = 'lero'
}

// wrong
var name = 'lero'
```

### strict

Strict mode avoid some dangerous behaviors from javascript, like global variables when dont use `var`, but has many others, just to mention a example and not list all here.

```js
// right
'use strict'
const name = 'lero'

// wrong
name = 'lero'
```

### no-undef

Disallow use of undefined variables, helping you to declare how and from you're importing/using variables

```js
// right
require('angular')

angular.module('app')

// right
import angular from 'angular'

angular.module('app')

// wrong
angular.module('app')
```

```js
// right
const {HTMLElement} = window

class MyComponent extends HTMLElement {}

// wrong
class MyComponent extends HTMLElement {}
```

### no-unused-vars

Many times we create a variable, but never use it, serious, this happens all time.

```js
// right
function (a, b) {
  return a + b
}

// wrong
function (a, b, c) {
  return a + b
}
```

### block-scoped-var

Forces to use variable inside scope where you created. This avoid errors.

```js
// right
function test() {
  let name

  if (condition) {
    name = 'lero'
  }

  return name
}

// wrong
function test() {
  if (condition) {
    let name = 'lero'
  }

  return name
}
```

### camelcase

Completely followed by javascript community, compound names can be more legible using camel case.

```js
// right
let fullName

// wrong
let full_name
```

### eqeqeq

Using three equals, you can compare value and type, preventing a possible logical error.

```js
// right
10 === '10' // return false

// wrong
10 == '10' // return true
```

### new-cap

Better to read and identify that are constructor, e.g.

```js
// right
const user = new Person()

// wrong
const user = new person()


// right
class Person {}

// wrong
class person {}
```

<!-- ### max-depth

This is a warning, not required.
Multiples functions nested can be difficult to read. Limit recommended is 3 levels.

### max-len

This is a warning, not required.
Very long lines of code can be difficult to read. Limit lines of code to max 80 characters help to avoid that.

```js
// right, small and cleaver
function (argument1, argument2, argument4) {}

// right, but below is a example near to max allowed (80 characters)
function(argument1, argument2, argument3, argument4, argument5, argument6) {}

// wrong, because more than 80, is too long
function(argument1, argument2, argument3, argument4, argument5, argument6, argument7, argument8, argument9, argument10) {}
``` -->
