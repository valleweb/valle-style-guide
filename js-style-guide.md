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
if (true) {
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
if (true) {
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
if (true) {
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
if (true) {
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

### When you must use function expressions (as when passing an anonymous function), use `arrow function` notation

```js
// Bad
[1, 2, 3].map(function (x) {
  const y = x + 1;
  return x * y;
});
```

```js
// Good
[1, 2, 3].map((x) => {
  const y = x + 1;
  return x * y;
});
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

### Use `const` for all of your references, avoid using `var`

```js
// Bad
var foo = 'bar';
```

```js
// Good
const foo = 'bar';
```

### If you must reassign references, use `let` instead of `var`

```js
// Bad
var count = 1;

if (condition) {
  count += 1;
};
```

```js
// Good
let count = 'bar';

if (condition) {
  count += 1;
};
```

### Declare one `const` or `let` per declaration statement

```js
// Bad
const foo = require('./bar');
      foo = require('./foo');
```

```js
// Good
const foo = require('./bar');
const foo = require('./foo');
```

### Use the literal syntax for `object` creation

```js
// Bad
const foo = new Object();
```

```js
// Good
const foo = {};
```

### Use the literal syntax for `array` creation

```js
// Bad
const foo = new Array();
```

```js
// Good
const foo = [];
```

### Declare the `array` itens inline

```js
// Bad
const foo = [
  'hello', 'world'
];
```

```js
// Good
const foo = ['hello', 'world'];
```

### Parentheses `()` and commas , are not followed by indented children on new lines

```js
// Bad
foo.bar(
  'string',
  () => {
    statements
  }
);
```

```js
// Good
foo.bar('string', () => {
  statements
});
```

### Method chaining

```js
// Bad
user
.findOne({ name: 'foo' })
.populate('bar')
.exec(function(err, user) {
  return true;
});

// Bad
user.findOne({ name: 'foo' })
  .populate('bar')
  .exec(function(err, user) {
    return true;
  });
```

```js
// Good
user
  .findOne({ name: 'foo' })
  .populate('bar')
  .exec(function(err, user) {
    return true;
  });
```

### Use braces with all blocks

```js
// Bad
if (condition) doSomething();

while (condition) iterating++;
```

```js
// Good
if (condition) {
  ...
}

while (condition) {
  ...
}
```

### Any non-trivial conditions should be assigned to a descriptively named variable or function

```js
// Bad
if (password.length >= 4 && /^(?=.*\d).{4,}$/.test(password)) {
  ...
}
```

```js
// Good
const isValidPassword = password.length >= 4 && /^(?=.*\d).{4,}$/.test(password);

if (isValidPassword) {
  ...
}
```

### Try to write comments that explain higher level mechanisms or clarify difficult segments of your code

```js
// Bad
const foo = "var(--bar)";

// Regexp
if (foo.replace(/var\(/, "").replace(/\)/, "") === "--bar") {
  ...
}
```

```js
// Good
let foo = 'var(--bar)';

let value = foo
            .replace(/var\(/, '') // Remove the 'var('
            .replace(/\)/, ''); // Remove the ')'

if (foo === '--bar') {
  ...
}
```

### Don't use comments to trivial things

```js
// Bad

// Create the AST
const ast = css.parse('.a{color:#000;}');
```

```js
// Good
const ast = css.parse('.a{color:#000;}');
```

## React

> Follow the [HTML Guide](https://github.com/valleweb/valle-style-guide/blob/master/html-style-guide.md) except for the rules bellow.

### Always use stateless components

```js
// Bad

class Component extends React.Component {
  render () {
    return <h1>.</h1>
  }
}
```

```js
// Good

const Component = () => {
  return <h1>.</h1>
}
```

### Mixins

*Don't use*

### Naming

*Always use PascalCase for React components*

```js
// Bad

import componentTest from './ComponentTest';
import componenttest from './ComponentTest';
```

```js
// Good

import ComponentTest from './ComponentTest';
```

### Export component

```js
// Bad

export default function Component() {
  return <h1>.</h1>
}
```

```js
// Good

const Component = () => {
  return <h1>.</h1>
}

export default Component;
```

### Props

*Always create props with different names than the DOM props*

```js
// Bad

<Component style="test" />
```

```js
// Good

<Component myProp="test" />
```

*Always use camelCase for prop names*

```js
// Bad

<Component my_prop="test" />
```

```js
// Good

<Component myProp="test" />
```

*Always omit the value of the prop when it is explicity `true`*

```js
// Bad

<Component myProp={ true } />
```

```js
// Good

<Component myProp />
```

### Spacing

*Always include a single space in your self-closing tag*

```js
// Bad

<Component/>
```

```js
// Good

<Component />
```

*Always pad JSX curly braces with spaces*

```js
// Bad

<Component myProp={name}/>
```

```js
// Good

<Component myProp={ name }/>
```

## References

Project inspired by [Banana CSS](https://github.com/bananacss/banana-style-guide) and [LFeh coding style](https://github.com/LFeh/coding-style#js).

### [<-- Back](https://github.com/valleweb/valle-style-guide)
