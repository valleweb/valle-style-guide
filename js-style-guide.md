# JavaScript code style guide

> The [Valle](https://github.com/valleweb) JavaScript code style guide.

### Soft tabs with two spaces

*You can configure your editor for this*

```js
// Bad
if ( true ) {
    console.log('True');
}
```

```js
// Good
if ( true ) {
  console.log('True');
}
```

### Always use semicolons

```js
// Bad
if ( true ) {
    console.log('True')
}
```

```js
// Good
if ( true ) {
  console.log('True');
}
```

### Always use single quotes

```js
// Bad
if ( true ) {
  console.log("True");
}
```

```js
// Good
if ( true ) {
  console.log('True');
}
```

### Keep else in the same line of closure of the `if`

```js
// Bad
if ( true ) {
  console.log('True');
}
else {
  console.log('False');
}
```

```js
// Good
if ( true ) {
  console.log('True');
} else {
  console.log('False');
}
```

### Add spaces between operators

```js
// Bad
for (i=0;i<10;i++) {
  ...
}
```

```js
// Good
for (i = 0; i < 10; i++) {
  ...
}
```

### Avoid single letter names

*Be descriptive with your naming*

```js
// Bad
function q() {
  ...
}
```

```js
// Good
function query() {
  ...
}
```

### Use lowerCamelCase

```js
// Bad
let is_error;
```

```js
// Good
let isError;
```

### Use the === operator

```js
// Bad
const example = 'Is a example';

if (example == 15) {
  ...
}
```

```js
// Good
const example = 'Is a example';

if (example === 15) {
  ...
}
```

### Add spaces outside parentheses `()` but avoid it inside

```js
// Bad
if(condition){
  ...
}
```

```js
// Good
if (condition) {
  ...
}
```

### Use function declarations instead of function expressions

```js
// Bad
const foo = function () {
};
```

```js
// Good
function foo() {
}
```

### Ternary operator

*The ternary operator should not be used on a single line. Split it up into multiple lines instead*

```js
// Bad
const foo = (condition) ? 1 : 2;
```

```js
// Good
const foo = (condition)
  ? 1
  : 2;
```

## References

Project inspired by [Banana CSS](https://github.com/bananacss/banana-style-guide) and [LFeh coding style](https://github.com/LFeh/coding-style#js).

### [<-- Back](https://github.com/valleweb/valle-style-guide)
