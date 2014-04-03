# HTML style guide

<img
    src="https://raw.github.com/caiogondim/html-style-guide/master/logo.png"
    alt="HTML style guide logo"
    align="right"
/>

My personal way of writing HTML, based in my own experience and others style
guides.


## Protocol

Ommit the protocol (http:, https:) from URLs pointing to images, style sheets,
scripts, unless they are not available in both protocols. That way, mixed
content issues is prevented, because the URL is now relative.

```html
<!-- Good -->
<script src="//ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js"></script>

<!-- Bad -->
<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js"></script>

```
```css
/* Good */
.example {
   background: url(//caiogondim.com/img/logo.png);
}

/* Bad */
.example {
   background: url(http://caiogondim.com/img/logo.png);
}
```

## Indentation

Always use 2 spaces for indentation.

```html
<html>
  <head></head>
  <body>
    <section></section>
  </body>
</html>
```


## Capitalization

Use only lowercase.

```html
<!-- Bad -->
<A HREF="/">Home</A>

<!-- Good -->
<a href="/">Home</a>
```


## Document type

Use HTML5. And use HTML syntax, not XHTML. Hixie
[wrote some about it](http://hixie.ch/advocacy/xhtml).

```html
<!--- Bad -->
<br />

<!-- Good -->
<br>

<!-- Good -->
<!doctype html>

<!-- Bad -->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
```


## Separation of Concerns

In your templates and documents, use only (or strive for it) HTML. Put
everything presentational into style sheets. And all the behavior in scripts
files.

Keep the contact area as small as possible by linking only the needed style
sheets and scripts for the current document.


```html
<!-- Bad -->
<!doctype html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Example</title>
</head>
  <body>
    <h1 style="font-size: 20px;">Lorem Ipsum</h1>
  </body>
  <script>
    document.querySelector("h1").style.color = "red";
  </script>
</html>

<!-- Good -->
<!doctype html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Example</title>
  <link rel="stylesheet" href="main.css" />
</head>
  <body>
    <h1>Lorem Ipsum</h1>
  </body>
  <script src="app.js"></script>
</html>
```


## Entity references

There is no need to use entity references like `&rdquo;` or `&mdash;` if you're
using UTF-8 encoding. The only exceptions are to characters with special meaning
to HTML, as `<`, `>` and `&`, or “invisible” characters, as no-break spaces.

```html
<!-- Bad -->
The currency symbol for the Euro is &ldquo;&eur;&rdquo;.

<!-- Good -->
The currency symbol for the Euro is “€”.

<!-- Ok, since we always want to “Mr.” and “Someone” to be together, and never in separate lines -->
Mr.&nbsp;Someone
```


## Self-closing tags

Use the HTML5 way, not XHTML.

```html
<!-- Bad -->
<br />
<hr />

<!-- Good -->
<br>
<hr>
```


## Attributes

Again, prefer the HTML5 way, not XHTML.

```html
<!-- Bad -->
<input type="checkbox" checked="checked">

<!-- Good -->
<input type="checkbox" checked>
```


## Quotes

Always use double quotes.

```html
<!-- Bad -->
<input type=checkbox>
<input type='checkbox'>

<!-- Good -->
<input type="checkbox">
```


## Maximum line length

Try as hard as you can to keep line lenght slower than 80 columns. It improves
readability and makes possible to use a 2 columns split view in your editor
(your editor supports it, right?) without horizontal scroll.

```html
<!-- Bad -->
<img class="block__element" id="unicorn" src="http://cl.ly/image/1a1U013E002Z" alt="Unicorn, rainbows, poop and stuff" width="500">

<!-- Good -->
<img
  class="block__element"
  id="unicorn"
  src="http://cl.ly/image/1a1U013E002Z"
  alt="Unicorn, rainbows, poop and stuff"
  width="500"
>
```

Also, it's a good pratice to put every attribute in it's line, since Git doesn't
show in a diff **what** in a line was modified, only that it's was modified.


## Reference

This documented is highly inspired in these others style guides:
- [Google HTML/CSS Guide](https://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml)
