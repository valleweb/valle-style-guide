# CSS code style guide

> The [Valle](https://github.com/valleweb) CSS code style guide.

### Use BEM
*[BEM](http://getbem.com/introduction/) - The Block, Element, Modifier methodology*

### Soft tabs with two spaces

*You can configure your editor for this*

```css
/* Bad */
.example {
    color: #ccc;
}
```

```css
/* Good */
.example {
  color: #ccc;
}
```

### Always use double quotes

```css
/* Bad */
.example {
  content: 'example';
}
```

```css
/* Good */
.example {
  content: "example";
}
```

### Include a single space before the opening bracket of a ruleset

```css
 /* Bad */
.example{
  color: #ccc;
}
```

```css
/* Good */
.example {
  color: #ccc;
}
```

### Include a single space after the colon of a declaration

```css
 /* Bad */
.example {
  color:#ccc;
}
```

```css
/* Good */
.example {
  color: #ccc;
}
```

### Include a semi-colon at the end of the last declaration in a declaration block

```css
 /* Bad */
.example {
  color: #ccc
}
```

```css
/* Good */
.example {
  color: #ccc;
}
```

### Keep one declaration per line

```css
 /* Bad */
.example-1, .example-2, .example-3 {
  color: #ccc
}
```

```css
/* Good */
.example-1,
.example-2,
.example-3 {
  color: #ccc;
}
```

### Single declarations should remain in one line

```css
 /* Bad */
.example {
  color: #ccc
}
```

```css
/* Good */
.example { color: #ccc; }
```

### Separate each ruleset by a blank line

```css
 /* Bad */
.example-1 {
  color: #ccc
}
.example-2 {
  color: #fff
}
```

```css
/* Good */
.example-1 {
  color: #ccc;
}

.example-2 {
  color: #fff;
}
```

### Use lowercase

```css
 /* Bad */
.example {
  color: #CCC;
}
```

```css
/* Good */
.example {
  color: #ccc;
}
```

### Use shorthand hex values

```css
 /* Bad */
.example {
  color: #cccccc;
}
```

```css
/* Good */
.example {
  color: #ccc;
}
```

### Avoid specifying units is zero-values

```css
 /* Bad */
.example {
  margin: 0px;
}
```

```css
/* Good */
.example {
  margin: 0;
}
```

### Omit leading `0` in values

*Do not put `0` in front of values or lengths between -1 and 1*

```css
 /* Bad */
.example {
  font-size: 0.5em;
}
```

```css
/* Good */
.example {
  font-size: .5em;
}
```

### Declaration Order

*The declarations should be added in alphabetical order*

```css
 /* Bad */
.example {
  font-size: 5em;
  color: #ccc;
  width: 500px;
  background-color: #fff;
  height: 500px;
  display: inline-block;
  padding: 3px;
  margin: 5px;
}
```

```css
/* Good */
.example {
  background-color: #fff;
  color: #ccc;
  display: inline-block;
  font-size: 5em;
  height: 500px;
  margin: 5px;
  padding: 3px;
  width: 500px;
}
```

## References

Project inspired by [LFeh coding style](https://github.com/LFeh/coding-style/blob/master/README.md#css) and [Google CSS style guide](https://google.github.io/styleguide/htmlcssguide.html#CSS).

### [<-- Back](https://github.com/valleweb/valle-style-guide)
