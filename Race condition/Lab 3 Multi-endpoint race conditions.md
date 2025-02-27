In this lab we are able to explode the multi-endpoint race condition vuln.
First we identify the two endpoint that allow to interact with the cart. POST /cart to add items and POST /cart/checkout to buy.
If we send the request in parallel we are able to buy the jacket. Only we need to send the request of checkout as if we are buying an item that we had enough money. And at the same time we send the post to add a jacket, modifying the id of the item. 
![[Pasted image 20250225201914.png]]
![[Pasted image 20250225201859.png]]
