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
- [eqeqeq](#eqeqeq)
- [max-depth](#max-depth)
- [max-len](#max-len)
- [max-statements](#max-statements)
- [new-cap](#new-cap)
- [no-extend-native](#no-extend-native)
- [no-mixed-spaces-and-tabs](#no-mixed-spaces-and-tabs)
- [no-trailing-spaces](#no-trailing-spaces)
- [no-multiple-empty-lines](#no-multiple-empty-lines)
- [block-spacing](#block-spacing)
- [newline-per-chained-call](#newline-per-chained-call)
- [keyword-spacing](#keyword-spacing)
- [space-unary-ops](#space-unary-ops)

#### semi

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

#### curly

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

#### brace-style

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
