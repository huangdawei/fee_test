# HTML & CSS Style Guide

## General

Settings in this section could be done by configurating your text editor.

### Indention,

Use **4 spaces** for indention, do not use tab. Please config your editor tranlate tabs to spaces.

```html
<ul>
    <li>Kant</li>
    <li>Sartre</li>
</ul>
```
```css
.class {
    color: green;
}
```

### Trailing Whitespace

Remove trailing spaces when saving the file.

### New line At End Of Files

Ensure there is be a new line at the end of the file when saving.

- Vim: enabled by default
- Sublime Text 2/3: set `ensure_newline_at_eof_on_save` to true

## HTML

### Document Type
Use the HTML5 doctype

```html
<!DOCTYPE html>
<html lang="en">
    ...
</html>
```

### Encoding

Use UTF-8 (no BOM). Specify the encoding in HTML templates and documents via `<meta charset="utf-8">`

### Comments

Use syntax of the template language instead of tag comments, only if it should be a DOM node in the document.

```html
{# comment here #}
<section class="hero">
    <img src="" alt="">
</section>
```

### HTML Elements

- All code should be lowercase:  HTML element names, attributes & attribute values.
- No trailing slashes in self-closing elements, for example: `<br>`, `<img>` & `<input>`.

### Optional Tags

Do not omit [optional tags](http://www.whatwg.org/specs/web-apps/current-work/multipage/syntax.html#syntax-tag-omission), make your code easy to read.

### Quotation Marks

Use double ("") rather than single quotation marks ('') around attribute values.

```html
<!-- Recommended -->
<a class="maia-button maia-button-secondary">Sign in</a>
```

### Indent for blocks and inline

- Put every block (div, p, ul, li, table, & etc) to a dependent line
- Don't break a inline element

## CSS

### Formatting

- Put spaces after `:` in property declarations.
- Put spaces before `{` in rule declarations.
- Put line breaks between rulesets.
- When grouping selectors, keep individual selectors to a single line.
- Place closing braces of declaration blocks on a new line.
- Put `;` after every declaration.

```css
.demo {
    background: transparent;
    height: 50px;
}

.header,
.footer {
    height: 100px;
    box-shadow: none;
}
```

### Comments

- Use block comments for explainations on the top of files blocks
- Use `//` to to comment a lines in LESS/Sass/Stylus files
- Use `//` for explainations of lines

```css
/**
 * Style for Domain.com
 * Author: Your Name
 */

.demo {
    height: 100px;
    // width: 100%;
    font-family: monospace; // for code
}
```

### Class And ID

- Use meaningful words as the the class and id name
- Keep the name as short as possiable
- Use hyphen `-` to connect words in the name, don't use `_` and camel cases.

```css
.widget {}
#nav { }
.search-wrapper {}
```

### Selector

- Avoid using element names in conjunction with IDs or classes for the [preformce reason](http://www.stevesouders.com/blog/2009/06/18/simplifying-css-selectors/).
- Don't nest more than three levels (seclector with four levels at most), It happens quite a lot when using LESS/Sass/Stylus, organize your code carefully.

```css
.header {
    background: white;

    .logo {
        display: inline-block;
    }

    #nav {
        display: block;
    }
}
```

### Properties

- Don't separate shorthand properties into multi entities

```css
body {
    font: 16px/1.5 Helvetica, Arial, sans-serif;
}
```

### Color

Use color and its transformations setted in the global color palette. Don't use new color like `#000`, `red` and `rgba(0, 0, 0, 0)`.

```css
.btn {
    background: @color-blue;

    &:hover {
        background: darken(@color-blue, 5%);
    }
}
```

### Prefix Venders

You don't have to add prefix for different browsers, leave this work to CSS preprocessor tools.

### Units

- Omit leading “0”s in values:

```css
.test {
    font-size: .8em;
}
```

- Omit unit when the value is `0`:

```css
.test {
    font-size: 0;
}
```

### Quatation Marks

- Use double quotation marks for attribute selectors and property values
- Do not use quotation marks in URI values `url()'

```css
@import url(typography.scss);
.demo:after {
    content: "";
}
```

### CSS Modoules

There's no namespace in CSS language for modoulization, So with the growth of web modules, we wrap LESS/Sass/Stylus codes with classes in a module:

```css
.component-footer {
    height: 100px;

    .nav {}

    .social {}

    .copyright {}
}
```
