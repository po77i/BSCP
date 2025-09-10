First at all I will put only the payload to solve directly the lab, but then I will try to take note why this happens.

```
{{$on.constructor('alert(1)')()}}
```
![[Pasted image 20250820213318.png]]
The second () is to call the function that was created without calling it
![[Pasted image 20250820220858.png]]
![[Pasted image 20250820221217.png]]


On the next screenshot there is a basic web to understand how angularjs works. 
Here on the body there are a couple of {{}} with differents attributes, firstName is calling the value that was defined on the bottom. Then, 1+1 which is going to be shows on the web as 2, because is the JS is resolving the math. Finally, this lab solution. On the function there is a $, which the only porpoise is let it know us that the function is part of angular function and it was not written by a developer 
![[Pasted image 20250820213901.png]]

Creating a empty paragraph we are able to see the $scope, this is useful because we can se which function we are able to use and this is cause for the function heritage

![[Pasted image 20250820214839.png]]

![[Pasted image 20250820215634.png]]

Here in prototype there are the function and properties that the object has heritage 
![[Pasted image 20250820215655.png]]

But we need to focus on the parents attr, which contains function, on the solution they used the $on function, but we could have use any of these.
![[Pasted image 20250820220307.png]]

This function it is which had created the obj. But, behind the scene for example $on.constructor is calling this function. 
![[Pasted image 20250820220858.png]]
![[Pasted image 20250820221625.png]]
![[Pasted image 20250820221641.png]]

So, we can send an alert fuction, which is created by FUNCTION function, and we are calling with () . Because we are able to created fn without name or anonymous functions
![[Pasted image 20250820221911.png]]