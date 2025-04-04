In this lab you can find a two of security issues 
First, you can realize that you can change the session cookie name, and nothing happen.
Second, you are able to make brute force to bypass the two factor security step. 
In the next screen shoot I changed the Cookie, to carlos. And use the post request, not the get one.  I used Caido proxy, so I had to create a list in order to not lose the first thousands number, cause caido doesn't have a way to brute force using 4 digits. If you put from 0 to 9999, it will skip 0001 or 0088, because it will count 1 by 1. (1,2,3...)

![[Pasted image 20250310212644.png]]

Finally, when we got the code, we need to copy the session cookie and put in the request.

![[Pasted image 20250310212956.png]]
