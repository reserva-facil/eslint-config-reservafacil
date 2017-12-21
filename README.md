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
