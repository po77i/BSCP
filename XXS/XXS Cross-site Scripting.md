	
![[Pasted image 20250804190208.png]]
![[Pasted image 20250804190319.png]]
![[Pasted image 20250804190444.png]]
![[Pasted image 20250804190511.png]]
![[Pasted image 20250804190617.png]]
![[Pasted image 20250804191702.png]]

![[Pasted image 20250804191645.png]]
![[Pasted image 20250804191955.png]]


![[Pasted image 20250804192252.png]]
```
POST /post/comment 
HTTP/1.1 Host: vulnerable-website.com 
Content-Length: 100 

postId=3&comment=This+post+was+extremely+helpful.&name=Carlos+Montoya&email=carlos%40normal-user.net
```
![[Pasted image 20250804192526.png]]![[Pasted image 20250804194059.png]]
![[Pasted image 20250804194416.png]]
![[Pasted image 20250804194536.png]]
![[Pasted image 20250804200527.png]]



![[Pasted image 20250804201216.png]]

![[Pasted image 20250804201543.png]]
![[Pasted image 20250804201731.png]]
![[Pasted image 20250804202845.png]]
![[Pasted image 20250804203217.png]]
![[Pasted image 20250804203228.png]]
The following are some of the main sinks that can lead to DOM-XSS vulnerabilities:

```
document.write()
document.writeln()
document.domain
element.innerHTML
element.outerHTML
element.insertAdjacentHTML
element.onevent
```

The following jQuery functions are also sinks that can lead to DOM-XSS vulnerabilities:

```
add()
after()
append()
animate()
insertAfter()
insertBefore()
before()
html()
prepend()
replaceAll()
replaceWith()
wrap()
wrapInner()
wrapAll()
has()
constructor()
init()
index()
jQuery.parseHTML()
$.parseHTML()

```


![[Pasted image 20250807143343.png]]
![[Pasted image 20250807150032.png]]
![[Pasted image 20250807150041.png]]
![[Pasted image 20250807164023.png]]

![[Pasted image 20250807164122.png]]

```
$(function() { $('#backLink').attr("href",(new URLSearchParams(window.location.search)).get('returnUrl')); });
```

![[Pasted image 20250807172127.png]]
```
<iframe src="https://vulnerable-website.com#" onload="this.src+='<img src=1 onerror=alert(1)>'">
```
![[Pasted image 20250820212324.png]]


![[Pasted image 20250821134803.png]]
```
eval('var data = "reflected string"');
```


![[Pasted image 20250821152712.png]]


![[Pasted image 20250827194954.png]]
![[Pasted image 20250827195008.png]]
![[Pasted image 20250827194857.png]]
Lab15 for the above lab


![[Pasted image 20250827201639.png]]![[Pasted image 20250827213531.png]]

![[Pasted image 20250827213816.png]]![[Pasted image 20250827220136.png]]


![[Pasted image 20250827230518.png]]

![[Pasted image 20250827232826.png]]