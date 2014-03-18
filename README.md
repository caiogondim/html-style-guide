# HTML style guide

<img
    src="https://raw.github.com/caiogondim/html-style-guide/master/logo.png"
    alt="HTML style guide logo"
    align="right"
/>

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Tempore, temporibus,
odio, beatae quo atque consectetur unde nesciunt vero eos harum excepturi
perferendis similique voluptatum fugit facere voluptatibus suscipit enim ullam.

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
