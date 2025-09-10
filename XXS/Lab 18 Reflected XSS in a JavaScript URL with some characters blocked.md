This is the solution, and then I wrote down the explanation for this lab or something similar
![[Pasted image 20250827222203.png]]
```
https://YOUR-LAB-ID.web-security-academy.net/post?postId=5&%27},x=x=%3E{throw/**/onerror=alert,1337},toString=x,window%2b%27%27,{x:%27
```


The throw function respond the last item on the list, on this case 1338w
![[Pasted image 20250827220921.png]]
Here we get 1 (myVar) on the left  and on the rigth 1337
![[Pasted image 20250827221018.png]] ![[Pasted image 20250827221116.png]]

Here we have something really tricky, first he is define onerror as alert function, so when you get an error that will trigger the alert. 
And second is the 1337 (or whichever var that we pass).
![[Pasted image 20250827221527.png]]
![[Pasted image 20250827221724.png]]


Then we have a arrow function in java. But we can use parenthesis (), so we can manage that putting a variable. 
![[Pasted image 20250827221917.png]]![[Pasted image 20250827222029.png]]

Here toString a function in java, is being assigned to x. And then we can call toString, and this trigger the function x that is above.
![[Pasted image 20250827222341.png]]

Finally to end the payload we have a windows function and concatenating with a empty parameter. This will call the toString function, which is now redirect to the x function whit the payload.
![[Pasted image 20250827223037.png]]


Here is the vulnerability, where we can use the payload, the thing is insert the payload on the fetch function.
![[Pasted image 20250827223229.png]]
This is one example that what happen is we send extra variables to a function, and even we gonna receive myvar=10 on the final log. Because, for some reason even the function is only using the first two arguments, javascript is going to change the myVar's value. 
![[Pasted image 20250827224241.png]]

Ampersand here is saying the next key value  pair is part of the query string. The single quote closes the string, curly bracket closes the configuration of the javascript fecth function, then the coma indicate that we can start to add values to the function. 
The first argumente create a new function (x), we need use `/**/` to spoof the space. We use throw because is a statement, it does not return a value. The second comma to pass the second argument (toString...), another coma calling windows. And finally the las part {x:', which is use to end the attack
![[Pasted image 20250827224559.png]]

The attack is trigger when the user press "Back to Blog" link
![[Pasted image 20250827225734.png]]