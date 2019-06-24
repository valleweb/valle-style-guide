# HTML code style guide

> The [Valle](https://github.com/valleweb) HTML code style guide.

### Correct document type

*Always declare the document type as the first line in your document. Use lower case tags*

```html
<!-- Bad -->
<!DOCTYPE html>
```

```html
<!-- Good -->
<!doctype html>
```

### Always use UTF-8 for character encoding

```html
<head>
  <meta charset="UTF-8">
</head>
```

### Lower case element name

*Always declare elements with lower case*

```html
<!-- Bad -->
<SECTION>
  <p>This is a paragraph.</p>
</SECTION>
```

```html
<!-- Good -->
<section>
  <p>This is a paragraph.</p>
</section>
```

### Don't include a `/` in self-closing elements

*Except for the react elements*

```html
<!-- Bad -->
<img />
```

```html
<!-- Good -->
<img>
```

### Soft tabs with two spaces

*You can configure your editor for this*

```html
<!-- Bad -->
<section>
    <p>This is a paragraph.</p>
```

```html
<!-- Good -->
<section>
  <p>This is a paragraph.</p>
```

### Always use double quotes

```html
<!-- Bad -->
<div class='example'>
```

```html
<!-- Good -->
<div class="example">
```

### Separate block element by a blank line and agroup the inners block elements

```html
<!-- Bad -->
<div class="block-a">

  <ul>

    <li></li>

    <li></li>

  </ul>

</div>
<div class="block-b">

  <ul>
  
    <li></li>
    <li></li>

  </ul>
</div>
```

```html
<!-- Good -->
<div class="block-a">
  <ul>
    <li></li>
    <li></li>
  </ul>
</div>

<div class="block-b">
  <ul class="red">
    <li></li>
    <li></li>
  </ul>

  <ul class="blue">
    <li></li>
    <li></li>
  </ul>
</div>
```

### Always add the `alt` attribute to images

```html
<!-- Bad -->
<img src="exanple.png">
```

```html
<!-- Good -->
<img src="example.png" alt="Attribute alt example">
```

### Always add the `title` tag to svg

```html
<!-- Bad -->
<svg width="500" height="300" xmlns="http://www.w3.org/2000/svg">
  <g>
    <rect x="10" y="10" width="200" height="50"
    style="fill:wheat; stroke:blue; stroke-width:1px"/>
  </g>
</svg>
```

```html
<!-- Good -->
<svg width="500" height="300" xmlns="http://www.w3.org/2000/svg">
  <g>
    <title>SVG Title Demo example</title>
    <rect x="10" y="10" width="200" height="50"
    style="fill:wheat; stroke:blue; stroke-width:1px"/>
  </g>
</svg>
```

### No need to specify a type when including CSS and JavaScript files as `text/css` and `text/JavaScript`

```html
<!-- Bad -->
<link rel="stylesheet" href="style.css" type="text/css">
<script src="scripts.min.js" type="text/JavaScript"></script>
```

```html
<!-- Good -->
<link rel="stylesheet" href="style.css">
<script src="scripts.min.js"></script>
```

### All JavaScripts files must be at the end of the code, before closing the `<body>`

```html
<!-- Bad -->
<head>
  <script src="scripts.min.js"></script>
</head>
<body>
```

```html
<!-- Good -->
  <script src="scripts.min.js"></script>
</body>
```

### Break long lines

```html
<!-- Bad -->
<input id="input" class="input" type="text" placeholder="Input">
```

```html
<!-- Good -->
<input
  id="input"
  class="input"
  type="text"
  placeholder="Input"
>
```

### HTML Attribute Order

*HTML attributes should be in this order for facilitate the reading*

1. `id`
1. `class`, `name`
1. `data-*`
1. `src`, `for`, `type`, `href`, `placeholder`
1. `title`, `alt`
1. `aria-*`, `role`

```html
<a id="..." class="..." data-modal="#overlay" href="#">

<input class="form-control" type="text" placeholder="...">

<img class="img-rounded" src="..." alt="...">
```

## References

Project inspired by [LFeh coding style](https://github.com/LFeh/coding-style/blob/master/README.md#html) and [Google HTML style guide](https://google.github.io/styleguide/htmlcssguide.html).

### [<-- Back](https://github.com/valleweb/valle-style-guide)
