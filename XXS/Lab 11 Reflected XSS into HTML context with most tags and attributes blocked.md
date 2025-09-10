Here if we tried a usual payload, the firewall blocks us
![[Pasted image 20250825204436.png]]
![[Pasted image 20250825204413.png]]

But if we only try with this, the app works. So, the way to resolve this is using the repeater Burp's function, in order to reveal if some payload could work.
![[Pasted image 20250825204541.png]]

On the repeater we use first a payload to find which tags are available. The are 2 tags, one of them is `<body>`
![[Pasted image 20250825210322.png]]
But if we try to introduce one onload inside of `body` , it does not work.

![[Pasted image 20250825210648.png]]

So, again we need to try with body and some payload. 

![[Pasted image 20250825210800.png]]

In the next screenshot we can see that we can chose tags (for the first attack) and events (2 attack)
![[Pasted image 20250825210409.png]]

Now finally we find 3 or 4 events. But in order to solve this lab we need to trigger the event without an user action. So, to go through that the guy used onresize (an available event) and onload, which is not allowed, but using it on the onresize, we are able to use. Basically when the web load it will be reseized triggering the print()


![[Pasted image 20250825211211.png]]

1. ```
```
<iframe src="https://YOUR-LAB-ID.web-security-academy.net/?search=%22%3E%3Cbody%20onresize=print()%3E" onload=this.style.width='100px'>
```
