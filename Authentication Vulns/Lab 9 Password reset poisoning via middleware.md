In this lab you are able to use X-Forwarded-Host header, but I don't know how you can realize of this, or you need to try.
So, we are able to send the answer to us (the lab server) 
![[Pasted image 20250404212409.png]]
On the lab's server we can get the answer, where we can copy the token 
![[Pasted image 20250404212334.png]]
And using a copy of the request, we can change the token and in consequence the victim's password
![[Pasted image 20250404212315.png]]
https://portswigger.net/web-security/learning-paths/authentication-vulnerabilities/vulnerabilities-in-other-authentication-mechanisms/authentication/other-mechanisms/lab-password-reset-poisoning-via-middleware#