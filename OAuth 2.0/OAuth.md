![[Pasted image 20250704221613.png]]
![[Pasted image 20250704221747.png]]
![[Pasted image 20250704222119.png]]
![[Pasted image 20250704222335.png]]
![[Pasted image 20250704222413.png]]
GET /authorization?client_id=12345&redirect_uri=https://client-app.com/callback&response_type=code&scope=openid%20profile&state=ae13d489bd00e3c24 HTTP/1.1 Host: oauth-authorization-server.com

![[Pasted image 20250704222529.png]]
![[Pasted image 20250704222911.png]]
![[Pasted image 20250704222955.png]]
![[Pasted image 20250704223405.png]]
POST /token HTTP/1.1
Host: oauth-authorization-server.com
… 
client_id=12345&client_secret=SECRET&redirect_uri=https://client-app.com/callback&grant_type=authorization_code&code=a1b2c3d4e5f6g7h8

![[Pasted image 20250704223617.png]]
![[Pasted image 20250704223712.png]]


![[Pasted image 20250704223823.png]]
![[Pasted image 20250704223832.png]]

![[Pasted image 20250704223855.png]]
GET /authorization?client_id=12345&redirect_uri=https://client-app.com/callback&response_type=token&scope=openid%20profile&state=ae13d489bd00e3c24 HTTP/1.1 

Host: oauth-authorization-server.com

![[Pasted image 20250704224018.png]]
GET /callback#access_token=z0y9x8w7v6u5&token_type=Bearer&expires_in=5000&scope=openid%20profile&state=ae13d489bd00e3c24 HTTP/1.1 
Host: client-app.com

![[Pasted image 20250704224153.png]]