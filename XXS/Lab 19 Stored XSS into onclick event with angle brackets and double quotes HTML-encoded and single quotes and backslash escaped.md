Here we are able to see that the system is scaping to the single quotes on the link that he passed.
![[Pasted image 20250827231148.png]]

The server is sanitizing quotes, backslash, etc. But, if we encode the parameters these will be accepted. In this case the `apos;` is the html-encoded simple quote, how you can see on the next screenshot. The & designated the html encoding. (-) to concatenate. And the las single quote to close the trailing quote
```
http://foo?&apos;-alert(1)-&apos;
```
![[Pasted image 20250827231447.png]]
![[Pasted image 20250827231433.png]]
The raw html code that we receive from the server is this, but the browser interprets the code and then its where the vulnerabilities pop up.
![[Pasted image 20250827231652.png]]