![[Pasted image 20250209195847.png]]![[Pasted image 20250208145118.png]]
![[Pasted image 20250208145210.png]]
![[Pasted image 20250208145346.png]]
![[Pasted image 20250208145432.png]]
![[Pasted image 20250208150123.png]]
![[Pasted image 20250208150154.png]]
![[Pasted image 20250208150352.png]]
![[Pasted image 20250208150429.png]]
![[Pasted image 20250208150441.png]]
![[Pasted image 20250208150507.png]]
![[Pasted image 20250208150531.png]]

![[Pasted image 20250208150839.png]]
![[Pasted image 20250208150923.png]]
![[Pasted image 20250208151012.png]]
![[Pasted image 20250208151628.png]]
```
#Full introspection query
	query IntrospectionQuery {
	 __schema {
		  queryType {
			   name 
		  } 
		  mutationType {
			   name
		  } subscriptionType {
			   name 
		  } types {
		   ...FullType
		  } directives {
		   name
		   description
		   args {
		    ...InputValue
		  }
		  onOperation #Often needs to be deleted to run query
		  onFragment #Often needs to be deleted to run query 
		  onField #Often needs to be deleted to run query
		}
	} 
} fragment FullType on __Type {
	kind
	name
	description
	fields(includeDeprecated: true) {
	 name
	 description
	 args {
		...InputValue
	 } type {
		...TypeRef
	 } isDeprecated
	   deprecationReason
} inputFields {
	...InputValue 
} interfaces {
	...TypeRef
} 
enumValues(includeDeprecated: true) {
	name
	description 
	isDeprecated 
	deprecationReason 
} 
possibleTypes {
	...TypeRef 
} 
} 
fragment InputValue on __InputValue {
	name 
	description 
	type { 
		...TypeRef
	} 
	defaultValue 
} 
fragment TypeRef on __Type {
	kind
	name
	ofType { 
		kind 
		name 
		ofType {
			 kind 
			 name 
			 ofType {
				  kind name 
			} 
		} 
	} 
}
```

After that we are able to copy the response in the next URL and receive a graph of how the web works
https://nathanrandal.com/graphql-visualizer/
![[Pasted image 20250209200452.png]]

![[Pasted image 20250208153052.png]]
![[Pasted image 20250208153203.png]]
![[Pasted image 20250208154812.png]]
![[Pasted image 20250208154848.png]]



![[Pasted image 20250208183609.png]]
![[Pasted image 20250208183619.png]]
{
	"query": "query{__schema
		{queryType{name}}}"
}
![[Pasted image 20250208183645.png]]


![[Pasted image 20250208202318.png]]
![[Pasted image 20250208202645.png]]
![[Pasted image 20250209195925.png]]



![[Pasted image 20250209220608.png]]
![[Pasted image 20250209220620.png]]
![[Pasted image 20250209220636.png]]
![[Pasted image 20250209220651.png]]
![[Pasted image 20250209220711.png]]
