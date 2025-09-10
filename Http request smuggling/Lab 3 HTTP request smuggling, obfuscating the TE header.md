On this lab we are forcing to obfuscate the TE in order to take advantage using the CL on the back.
1 - Trying to discover which method is using the server, front and back. If we send the next payload we can verify that the front is using chunked. We send a 3 for the first chunk and then an X, which is not permitted because is not a hexadecimal variable. 
![[Pasted image 20250905211118.png]]
2 - If we put 0, we are able to go through the frontend, the x is dropped, then we confirmed that on the back we have chunked.
![[Pasted image 20250905211200.png]]
3 - Different methods to obfuscate TE header
![[Pasted image 20250905211256.png]]

Obtaining a timeout give us this idea, we send two TE, on the frontend we are able to bypass it and on the back the servers reject those two headers and use the CL. So, the server stayed waiting because the CL=6 and we only send 5 characters.
![[Pasted image 20250905211439.png]]

If we send the next payload, we will get a G0Post. As on the past lab, we need to managed to bypass this and transform to a GPOST
![[Pasted image 20250905211524.png]]

This is the final payload idea. 

![[Pasted image 20250905212437.png]]

We need to send two request on one. The first will be chunked and one more to obfuscate. 
The minimun for the CL is 10 plus 1.  
![[Pasted image 20250905212659.png]]

And 5c (92) on the chunk size.
![[Pasted image 20250905212915.png]]

Final payload
![[Pasted image 20250905212955.png]]

```
POST / HTTP/1.1
Host: 0aa3005b04113a098035a43a00070004.web-security-academy.net
Content-Type: application/x-www-form-urlencoded
Content-length: 4
Transfer-Encoding: chunked
Transfer-encoding: cow

5c
GPOST / HTTP/1.1
Content-Type: application/x-www-form-urlencoded
Content-Length: 11

x=1
0


```

Normal request which trigger the solution
![[Pasted image 20250903220029.png]]