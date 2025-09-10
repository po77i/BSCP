This should be the normal vector attack, however it is block by the firewall. Cause its blocking the javascript on href

![[Pasted image 20250825222527.png]]

Using the repeater he found that "a" and "animate" tag is available to use. And animate is actually a SVG element. Then he tested if svg works, and actually is allowed. 
![[Pasted image 20250825224350.png]]

So, inside of the svg we can use different elements. In order to print text inside of svg, we need to use "a" tag and inside text tag with parameters 
![[Pasted image 20250825224759.png]]

But it is not allowed to introduce a href, so we need the animate element, which provides animation to svg. Furthermore, this allow to have control of certain attributes. The below screenshot show us that the element rect has attributes, these attributes are inside of animate tag.
![[Pasted image 20250825225030.png]]

Then, we are able to ensemble the payload, we have "animate", we called attributeName href (the attribute that we need), and finally the values, which is the javascript that we need. 

```
<svg><a><animate attributeName=href values=javascript:alert(1) <text x=20 y=20>Click Me</text></a>
```
![[Pasted image 20250825224201.png]]
![[Pasted image 20250825224220.png]]
```
https://YOUR-LAB-ID.web-security-academy.net/?search=%3Csvg%3E%3Ca%3E%3Canimate+attributeName%3Dhref+values%3Djavascript%3Aalert(1)+%2F%3E%3Ctext+x%3D20+y%3D20%3EClick%20me%3C%2Ftext%3E%3C%2Fa%3E
```