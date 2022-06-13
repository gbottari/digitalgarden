---
{"dg-publish":true,"permalink":"/05-notes/javascript-modules/","dgHomeLink":true,"dgPassFrontmatter":false}
---


# Javascript Modules
Tags: #🌲evergreen 
Links: [[05 notes/Frontend Development|Frontend Development]] | [[Javascript|Javascript]]

---
Javascript has several ways to handle modules and not always intuitive.

## Exporting
Export default can only be used once per file:
```js
const onlyOne = 1;
export default { onlyOne }
```

You can have multiple exports.
```js
const one = 1
const two = 2

export { one }
export { two }
```

## Importing
Default lib is the first one, but the order of the remaining ones don't matter.
```js
import { defaultFirst, two, one } from './lib';
```

You can also use named imports (specifying a path to an object) so that you only import the slice you need from that module.

## CommonJS import and export
Since [[NodeJS|NodeJS]] uses CommonJS, the old way (before ES6) uses a different syntax and has different behavior [^2].

### Exporting
```node
function hello() {
	return 'hello';
}
function bye() {
	return 'bye';
}

module.exports = {hello, bye};
// or module.exports = hello;
```

### Importing
```node
const hello = require('./greetings');
greetings.hello();
greetings.bye();
```

One advantage when using require is that you can import a module anywhere and use a variable to compose the name. On the other hand, ES6 importing are always top-level and require fixed names.

[1]: [[30 literature/courses/📘 (MTL) Curso React Native|📘 (MTL) Curso React Native]]
[2]: [javascript - Using Node.js require vs. ES6 import/export - Stack Overflow](https://stackoverflow.com/a/60331886)