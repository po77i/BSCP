In this lab, when you post smth. You get a redirect web, if you check the html, we can find a Js.
![[Pasted image 20250203224713.png]]

In the script you can observe how it generate the link, it is use for redirect later.
There is a parameter call postId, which we are able to control. And then before of this parameter they add a blogPath.
![[Pasted image 20250203225031.png]]

If we use the Payload 2, we will not find nothing, because the path will be /post/my-account. In order to sort this out, we use /../ (path transversal) to back in, and then /my-account/
![[Pasted image 20250203225529.png]]

Finally we add the specific path that we need in this lab
![[Pasted image 20250203230014.png]]