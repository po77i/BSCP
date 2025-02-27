
![[Pasted image 20250224201758.png]]
![[Pasted image 20250224202228.png]]
![[Pasted image 20250224202249.png]]
![[Pasted image 20250224202258.png]]
![[Pasted image 20250224202619.png]]
![[Pasted image 20250224202951.png]]
![[Pasted image 20250224203416.png]]

![[Pasted image 20250224214647.png]]
![[Pasted image 20250224215300.png]]
![[Pasted image 20250224215311.png]]
```PYTHON
def queueRequests(target, wordlists):
	engine = RequestEngine(endpoint=target.endpoint, concurrentConnections=1, engine=Engine.BURP2 )
# queue 20 requests in gate '1' 
for i in range(20):
	engine.queue(target.req, gate='1') 
# send all requests in gate '1' in parallel 
engine.openGate('1')
```


![[Pasted image 20250225191348.png]]
![[Pasted image 20250225191721.png]]

![[Pasted image 20250225192237.png]]
![[Pasted image 20250225192617.png]]
![[Pasted image 20250225193313.png]]
![[Pasted image 20250225193348.png]]
![[Pasted image 20250225193548.png]]
![[Pasted image 20250225193757.png]]
![[Pasted image 20250225194452.png]]
![[Pasted image 20250225215506.png]]
![[Pasted image 20250225215516.png]]
![[Pasted image 20250225220953.png]]
![[Pasted image 20250225221004.png]]
![[Pasted image 20250225221134.png]]

![[Pasted image 20250225224028.png]]
![[Pasted image 20250225224520.png]]
![[Pasted image 20250225224807.png]]
![[Pasted image 20250225224925.png]]
