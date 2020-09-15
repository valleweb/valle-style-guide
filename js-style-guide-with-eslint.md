# JavaScript code style guide for ESLint

> The [Valle](https://github.com/valleweb) JavaScript code style guide.

> The rules of ESLint are version 7.9.0

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
[space-in-parens](https://eslint.org/docs/rules/space-in-parens)

```js
  "space-in-parens": [
    "error",
    "never"
  ]
```

### Always use semicolons

#### Use this rule in frontend

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
[semi](https://eslint.org/docs/rules/semi)

```js
"semi": [ 
  "error", 
  "always"
],
```
### Never use semicolons

#### Use this rule in backend
```js
// Bad
if (true) {
  console.log('True');
}
```

```js
// Good
if ( true ) {
  console.log('True')
}
```
[semi](https://eslint.org/docs/rules/semi)

```js
"semi": [ 
  "error", 
  "never"
],
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
[quotes](https://eslint.org/docs/rules/quotes)

```js
 "quotes": [
    "error",
    "single"
  ],
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
[brace-style](https://eslint.org/docs/2.0.0/rules/brace-style)

```js
brace-style": [
  2,
  "1tbs", 
  { 
    "allowSingleLine": true 
  } 
]
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
[space-infix-ops](https://eslint.org/docs/rules/space-infix-ops)

```js
 "space-infix-ops": [
    "error",
    {
      "int32Hint": false
    }
  ]
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
[id-lenght](https://eslint.org/docs/rules/id-length)

```js
"id-length": [ 
  "error", 
  {
    "min": 2
  }
]
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
[calmecase](https://eslint.org/docs/rules/camelcase)

```js
"camelcase": [
  "error", 
  {
    "properties": "always"
  }
]
```

* Because of the legacy system ids it is not possible to put this rule on ESLint. But by default it uses camelcase when possible.

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
[eqeqeq](https://eslint.org/docs/rules/eqeqeq)

```js
"eqeqeq": [
  "error",
  "always"
],
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
[keyword-spacing](https://eslint.org/docs/rules/keyword-spacing)

```js
keyword-spacing: [
  "error",
    {
      "before": true,
      "after": true
    }
  ]
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
[func-style](https://eslint.org/docs/rules/func-style)

```js
"func-style": [
  "error",
  "declaration", 
  { 
    "allowArrowFunctions": true // valid for below rule
  }
]
```

### When you must use function expressions (as when passing an anonymous function), use `arrow function` notation

* The rule func-style is used for arrow functions too.

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
[func-style](https://eslint.org/docs/rules/func-style)

```js
"func-style": [
  "error",
  "declaration", 
  { 
    "allowArrowFunctions": true
  }
]
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

[no-nested-ternay](https://eslint.org/docs/rules/no-nested-ternary)

```js
"no-nested-ternary": "error"
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

[no-var](https://eslint.org/docs/rules/no-var)

```js
"no-var": "error" 
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

[no-var](https://eslint.org/docs/rules/no-var)

```js
"no-var": "error"
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

[one-var](https://eslint.org/docs/rules/one-var)

```js
"one-var": [
  "error",
  {
    "initialized": "never"
  }
]
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

[no-new-object](https://eslint.org/docs/rules/no-new-object)

```js
"no-new-object": "error",
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
[no-array-constructuor](https://eslint.org/docs/rules/no-array-constructor)

```js
"no-array-constructor": "error",
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
[array-element-newline](https://eslint.org/docs/rules/array-element-newline)

```js
"array-element-newline": [
  "error", 
  { 
    "multiline": true, 
    "minItems": 3 
  }
]
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
[function-paren-newline](https://eslint.org/docs/rules/function-paren-newline)

```js
"function-paren-newline": [
  "error", 
  "multiline"
]
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

[newline-per-chianed-call](https://eslint.org/docs/rules/newline-per-chained-call)

```js
"newline-per-chained-call": [
  "error", 
  { 
    "ignoreChainWithDepth": 2 
  }
]
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

[curly](https://eslint.org/docs/rules/curly)

```js
"curly": "error"
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

Project inspired by [Banana CSS](https://github.com/bananacss/banana-style-guide), [LFeh coding style](https://github.com/LFeh/coding-style#js) and [Airbnb React Style Guide](https://github.com/airbnb/javascript/tree/master/react).

### [<-- Back](https://github.com/valleweb/valle-style-guide)
