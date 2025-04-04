Examine this cookie in the Inspector panel and notice that it is Base64-encoded. Its decoded value is `wiener:51dc30ddc473d43a6011e9ebba6ca770`. Study the length and character set of this string and notice that it could be an MD5 hash![[Pasted image 20250312221702.png]]

So we need to hash the line that we will send, and it's MD5 the password  
1. `base64(username+':'+md5HashOfPassword)`
2. 
![[Pasted image 20250312231633.png]]
![[Pasted image 20250312231557.png]]

Finally we can grep looking for the "Update mail"
![[Pasted image 20250312222248.png]]
