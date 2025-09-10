This lab only accept these tags. 
The svg tag has inside animatetransform as attribute
![[Pasted image 20250826204248.png]]

Second, we have only one event listener, we discovered this with burp intruder. 
Onbegin is executed at the beginning, from there its name.
![[Pasted image 20250826204636.png]]

```
<svg><animatetransform onbegin='alert(1)'>
```
![[Pasted image 20250826205033.png]]