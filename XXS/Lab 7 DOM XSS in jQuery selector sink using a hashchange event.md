![[Pasted image 20250807174920.png]]

The vulnerability here is that the function is creating obj if it does not find what your had passed as value
![[Pasted image 20250807175332.png]]

Here he showed how you can check that the object was created and he is using appendChild to attach to the DOM

![[Pasted image 20250807175413.png]]

Then he created a img element, and as src attr, 0 was set it. 
![[Pasted image 20250807175657.png]]

This create a http request and with this we can force an error 
![[Pasted image 20250807175746.png]]

![[Pasted image 20250807174815.png]]