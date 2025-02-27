At first we will not find a graphql end point, so I tried the easiest one /api. 
![[Pasted image 20250208193620.png]]
Which is different to 
![[Pasted image 20250208193652.png]]

Then there was another problem, the introspectionQuery it is not allow. So, the trick is put a new line after the ``__schema``, before the curly bracket

![[Pasted image 20250208193036.png]]![[Pasted image 20250208193048.png]]

If we compare the url encoded, there is a %0a after schema
![[Pasted image 20250208193135.png]]

Now that we already have had the differents querys, there are two which catch our attention, DeleteOrganizationUser and getUser
![[Pasted image 20250208194253.png]]

If we send the query to the repeater and then to the decoder, we are able to see that we can get the users changing the id variable. 
![[Pasted image 20250208192327.png]]
First I tried with 1 and it gave me back the administrator user, finally the third ones is Carlos, we got the id that we will need in order to send the other query which we had discovered
![[Pasted image 20250208192311.png]]

Same process, we send the query to repeater -> decoder

![[Pasted image 20250208192426.png]]
![[Pasted image 20250208192414.png]]

Final step is send the delete query with the Carlos' id

![[Pasted image 20250208194912.png]]