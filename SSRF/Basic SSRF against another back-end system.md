Using sniper repeater attack we discover a ip where we have access to Admin panel
![[Pasted image 20241029223900.png]]

Click on this request, send it to Burp Repeater, and change the path in the `stockApi` to: `/admin/delete?username=carlos`

![[Pasted image 20241029223918.png]]