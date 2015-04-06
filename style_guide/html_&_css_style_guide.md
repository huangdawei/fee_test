# HTML & CSS Style Guide

## 1. General

This guide is a practice for writing HTML and CSS with uniform style, aims at improving collaboration in front-end engineering. It comes from [Google HTML/CSS Style Guide](https://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml#CSS_Style_Rules), [GitHub](http://primercss.io/guidelines/) and [idiomatic CSS](https://github.com/necolas/idiomatic-css).

When you are editing, look at the code around you and follow it's style at first, not kick off your own.

### Indention

Use **4 spaces** for indention, do not use tab. Set your editor to translate tabs to spaces.

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

- Vim: [How can you automatically remove trailing whitespace in Vim](http://stackoverflow.com/questions/356126/how-can-you-automatically-remove-trailing-whitespace-in-vim)
- Sublime Text: set `trim_trailing_white_space_on_save` to `true`

### New Line At The End Of Files

Ensure there is a new line at the end of the file when saving.

- Vim: enabled by default
- Sublime Text 2/3: set `ensure_newline_at_eof_on_save` to `true`

## 2. HTML

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

Use syntax of the template language instead of tag comments, only if it should be a DOM node.

```html
{# comment here #}
<section class="hero">
    <img src="" alt="">
</section>
```

### HTML Elements

- These code should be lowercase:  HTML element names, attributes & attribute values.
- No trailing slashes in self-closing elements, for example: `<br>`, `<img>` & `<input>`.

### Optional Tags

Do not omit [optional tags](http://www.whatwg.org/specs/web-apps/current-work/multipage/syntax.html#syntax-tag-omission), make your code easy to read.

### Quotation Marks

Use double `""` rather than single quotation marks `''` around attribute values.

```html
<a class="btn blue-btn" data-id="madness">Happy Me</a>
```

### Indent Of Blocks And Inline

- Put every block (div, p, ul, li, table & etc) to a dependent line
- Don't break a inline element

## 3. CSS

### Formatting

- Put spaces after `:` in property declarations
- Put spaces before `{` in rule declarations
- One line with one single deslaration
- When grouping selectors, one line each selector
- Put closing braces of declaration blocks on a new line
- Put `;` after every declaration

```scss
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

- Use block comments for explainations on the top of files and blocks, friendly for Doc generators
- Use `//` to to comment a lines of Less/Sass/Stylus
- Use `//` for explainations in lines of Less/Sass/Stylus

```scss
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
- Use `-` (hyphen) to connect words in the name, don't use `_` and camel cases

```scss
.widget {}
#nav { }
.search-wrapper {}
```

### Selector

- Avoid using element names in conjunction with IDs or classes for the [preformce reason](http://www.stevesouders.com/blog/2009/06/18/simplifying-css-selectors/)
- Don't nest more than three levels (seclector with four levels at most). It happens quite a lot in Less/Sass/Stylus, so organize your code carefully

```scss
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

- Don't separate shorthand properties into multiple entities

```scss
body {
    font: 16px/1.5 Helvetica, Arial, sans-serif;
}
```

### Color

Use colors and their transformations setted in the global color palette. Don't use `#000`, `red` and `rgba(0, 0, 0, 0)`.

```scss
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

```scss
.test {
    font-size: .8em;
}
```

- Omit unit when the value is `0`:

```scss
.test {
    font-size: 0;
}
```

### Quatation Marks

- Use double quotation marks for attribute selectors and property values
- Do not use quotation marks in URI values `url()`

```scss
@import url(typography.scss);
.demo:after {
    content: "";
}
```

### CSS Modoules

There's no namespace in CSS language for modoulization, So with the growth of web modules, we wrap Less/Sass/Stylus code with a class in a module:

```scss
.component-footer {
    height: 100px;

    .nav {}

    .social {}

    .copyright {}
}
```
