On this case, the first step was tried to upload a php file, which it is not allowed.  However, how we can see the server is a Apache.

![[Pasted image 20250704203043.png]]

Looking on the Apache documentation we can find this archive which allow to modify configurations on a per-directory basis.
![[Pasted image 20250704203224.png]]

In consequences, we are able to change how the files' extensions will be executed. 
On the next screenshot we are uploading one configuration archive (.htaccess), text/plain as content type and finally and the most important, we will add that the shell extensions are going to be executed as php. It will be allowed us to upload an shell archive, but it will be managed as a php. 

![[Pasted image 20250704203458.png]]

![[Pasted image 20250704202918.png]]

Finally we upload a .shell and should works
![[Pasted image 20250704204139.png]]


On the labs' solution that was given us, they used .l33t extension in order to solve the lab.
![[Pasted image 20250704205529.png]]