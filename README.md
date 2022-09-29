# Float

This a template for html preprocessing and typescript

`build/stuff` -- this is for all non-code files 

`build/pages` -- this is for all `.ftml` files

`build/src` -- this is for all `.ts` files

`build/styles` -- this is for all `.css` files but anything will do

Build your site with `make` or `make [ts | pages | styles]`

Clean build with `make clean`

### FTML spec

Ftml is the same as html except you have an additional tag

`<#include src='partials/nav.ftml' button="Order" dest="order.ftml">`

If `partials/nav.ftml` looks like
```
<div class='nav'>
    <a href='about.ftml'>About</a>
    <a href='contact.ftml'>Contact</a>
    <a href='<#get dest>'><#get button></a>
</div>
```

Then the the `<#include>` tag will be replaced with
```
<div class='nav'>
    <a href='about.html'>About</a>
    <a href='contact.html'>Contact</a>
    <a href='order.html'>Order</a>
</div>
```

