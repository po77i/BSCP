# Cross-site scripting (XSS)

Cross-site scripting is a web security vulnerability that enables an attacker to manipulate a vulnerable web site so that it returns malicious JavaScript to users. Attackers can use malicious code to fully compromise a victim's interaction with the application.

There are 3 types:
- Reflected XXS, where the malicious script comes from the current HTTP request.
- Stored XSS, where the malicious script comes from the website's database.
- DOM-based XSS, where the vulnerability exists in client-side code rather than server-side code.

#### **Reflected XXS**

This is the first XXS lab in portswigger academy. In it we can observe a space where we are able to look for a blog.
![[Pasted image 20240909210711.png]]

If you insert something to look for, we can see how the request is send. And you can notice that the same thing that we searched is reflected to the page.

![[Pasted image 20240909212501.png]]

For this reason, the next step is try if they allowed to insert special characters, for example html tags.

![[Pasted image 20240909212954.png]]

When we are able to see that is possible inject html, I injected a script to resolve the lab.  

![[Pasted image 20240909213429.png]]

There are multiple ways to evade XXS filters and preventions. But the majority of XSS prevention must depend on the web application’s sanitization of untrusted user input.

#### **Stored XXS**

Stored Cross-site Scripting is the most dangerous type of Cross Site Scripting. Web applications that allow users to store data are potentially exposed to this type of attack.

In this lab, we are able to insert comments without sanitization.

![[Pasted image 20240909215435.png]]

Then, the blog shows the comment to everyone. And this is the main problem, the input that is stored is not filtered. Therefore, this vulnerability can be use to conduct browser-based attacks.

![[Pasted image 20240909215504.png]]

In order to resolve this lab, I injected an alert.

![[Pasted image 20240909215612.png]]

The blog stored my comment, and when I tried to come back to see my comment, the alert is display.
![[Pasted image 20240909215656.png]]

Additionally, If the web application allows file upload, it is important to check if it is possible to upload HTML content.


#### **DOM XXS**

This vulnerabilities appears when JavaScript (could be others, as JQuery) take data from an user input and passes it to a sink that supports code execution. The most common source for DOM XXS is the URL. An attacker can construct a link to send a victim to a vulnerable page.

In this lab, I used the inspector browser.

![[Pasted image 20240909230100.png]]

Here if we use the blog's search function, and we checked what you had looked before, you will able to see a script function. 
After read the function and analyze, I noticed that we can try to inject some code.

![[Pasted image 20240909230325.png]]

I tried with different input, and then I found a way to broke the syntaxis and inject code 

![[Pasted image 20240909230936.png]]

![[Pasted image 20240909230948.png]]





# XML external entity (XXE) injection

It is a web security vulnerability that allows an attacker to interfere with an application's processing of XML data.
There are various types of XXE attacks:

- Exploiting XXE to retrieve files, where an external entity is defined containing the contents of a file, and returned in the application's response.
- Exploiting XXE to perform SSRF attacks, where an external entity is defined based on a URL to a back-end system.
- Exploiting blind XXE exfiltrate data out-of-band, where sensitive data is transmitted from the application server to a system that the attacker controls.
- Exploiting blind XXE to retrieve data via error messages, where the attacker can trigger a parsing error message containing sensitive data.

I'm going to exemplify just one type of xxe, the most basic one. Since I don't want to go into too much detail

This lab in portswigger, where if you send a request we can recognize a xml format

![[Pasted image 20240910195322.png]]
![[Pasted image 20240910200858.png]]
In the next screenshot I injected code to retrieve sensitive information. 
![[Pasted image 20240910200044.png]]
![[Pasted image 20240910200058.png]]

XXE to perform SSRF attacks

![[Pasted image 20240910203906.png]]
![[Pasted image 20240910204143.png]]
![[Pasted image 20240910203951.png]]


# SSRF

Allows an attacker to cause the server-side application to make requests to an unintended location.
In a typical SSRF attack, the attacker might cause the server to make a connection to internal-only services within the organization's infrastructure

Below I will show how an SSRF can be run.
In this case when I checked the request, I could see that some data was sent, this data was URL encoded. 
![[Pasted image 20240910215754.png]]

I was looking for a SSRF so I tried to insert a request that client server should be able to make.

![[Pasted image 20240910220243.png]]

That request showed me this

![[Pasted image 20240910220356.png]]

To solve the lab I needed to delete the carlos user. When I tried directly, I did not work. Because the request it had sent from me.  

![[Pasted image 20240910220323.png]]

But I realized that I could see the destination of the request. 
![[Pasted image 20240910221505.png]]

Therefore, I made the next request and it solved the lab. 

![[Pasted image 20240910220522.png]]



# Cross-site request forgery CSRF

It allows an attacker to induce users to perform actions that they do not intend to perform.
For example, this might be to change the email address on their account, passwords, or to make a funds transfer.

For a CSRF attack to be possible, there must exist three conditions:

- A relevant action: This might be a privileged action or any action on user-specific data
- Cookie-based session handling:  Performing the action involves issuing one or more HTTP requests, and the application relies solely on session cookies to identify the user who has made the requests. And there is not SameSite cookies.
- No unpredictable request parameters: The requests that perform the action do not contain any parameters whose values the attacker cannot determine or guess. 

Portswigger give to us a lab to prove this.
When we login with a user that they gave to us. 

![[Pasted image 20240911220609.png]]

We are able to see that the request contain our cookie and data

![[Pasted image 20240911223636.png]]

In this case, the lab contain a way to set up a web server if we do not have Burp Professional.
Then, we can use a simple web imitating the original form, where the victim should use his email. Consequently, the victim unintentionally changes his email.

![[Pasted image 20240911222907.png]]

Again, this is a basic lab. There are different ways to perform this attack and there are other common defenses that we can try to bypass. For example, CSRF tokens, SameSite cookies, referer-based validation.



### Web Caching

Fundamentally, web cache poisoning involves two phases. 
First, the attacker must work out how to elicit a response from the back-end server that inadvertently contains some kind of dangerous payload. Once successful, they need to make sure that their response is cached and subsequently served to the intended victims.

I found this methodology with steps. I think it is very useful.

![[Pasted image 20240913181129.png]]

This lab is a little bit more complex to explain. I ask apologies in advance if something is not enough clear.

In this lab we can observe that it has a parameter where we are able to realize if the web is already in cache.
X-Cache is the parameter, in the first screenshot the parameter is miss, this communicate to us that did not hit the cache.
Additionally, we can see Cache-Control and Age, two important parameters.

![[Pasted image 20240913182540.png]]


Second step is send a request with a cache buster and verify that the cache buster is working.

![[Pasted image 20240913175559.png]]
![[Pasted image 20240913182821.png]]

When we send a request with a query string, the cache server interpret that is another request.

![[Pasted image 20240913181748.png]]

For this lab portswigger give to us a web server. And here we are able to insert what the labs required to us in order to solve. But, basically it represents a source where we could add our payloads or whatever we want.
![[Pasted image 20240913175655.png]]

In additions in order to solve this lab, we have already got the parameter that is vulnerable and we could use to exploit. But, we are able to look for this parameter with Burp.
The parameter here is X-Forwarded-Host and here we can inject the Burp's web server path (attacker server).

![[Pasted image 20240913184703.png]]

Once we have achieved to put our malicious web on the cache server, we only need to make a request as a normal victim without the cache buster. 


### AWS Policies and Permissions

A policy is an object in AWS that, when associated with an identity or resource, defines their permissions. These determine if a request is allowed or not. Most of them are allowed in JSON documents.
It support 6 types of policies:

- **Identity-based policies**: Attach managed and inline policies to IAM identities. Identity-based policies grant permissions to an identity

- **Resourced-based policies**: Attach inline policies to resources. Resource based policies grant permissions to the principal that is specified in the policy. Principals can be in the same account as the resource or in other accounts

- **Permissions boundaries:** Use a managed policy as the permissions boundary for an IAM entity (user or role). That policy defines the maximum permissions that the identity-based policies can grant to an entity, but does not grant permissions. Permissions boundaries do not define the maximum permissions that a resource-based policy can grant to an entity

- **Organization service control policies (SCPs)**: Use an AWS Organizations service control policy (SCP) to define the maximum permissions for account members of an organization or organizational unit (OU). SCPs limit permissions that identity-based policies or resource-based policies grant to entities (users or roles) within the account, but do not grant permissions.

- **Access control lists (ACLs)**: Use ACLs to control which principals in other accounts can access the resource to which the ACL is attached. ACLs are cross-account permissions policies that grant permissions to the specified principal. ACLs cannot grant permissions to entities within the same account.

- **Session Policies**: Pass advanced session policies when you use the AWS CLI or AWS API to assume a role or a federated user. Session policies limit the permissions that the role or user's identity-based policies grant to the session. Session policies limit permissions for a created session, but do not grant permissions



IAM provides controlling access, but it can be vulnerable to hacking if are not properly secured. I found a couple of thing to keep in mind.

1 - Weak or compromised Access Keys : 
-  Phishing and social engineering attacks.
-  Leaked access keys in public repositories, such as Github, is a common issue.
-  Store access keys in insecure locations, for example local files or environment variables.

2 - Inadequate IAM policies and permissions
- Overly permissive policies, if someone gain access to an account with excessive privileges can cause substantial damage, including data theft or infrastructure sabotage.
- Misconfigured resource-based policies

3 - Unmonitored or Unused IAM users and roles
- Unused IAM users and roles: Regularly reviewing and removing unused IAM entities can help to reduce the attack surface
- Lack of monitoring and auditing. Implementing proper monitoring and auditing processes, such as using AWS CloudTrail, can help quickly identify and remediate security incidents.

4 - Insufficient MFA Implementation
- Not enforcing MFA (multi factor authentication) for all users. 
- MFA Misconfiguration, such as not enabling it for the root user or not requiring it for specific high-privilege actions

5 - Strengthening IAM with AWS services
- AWS security token service (STS) : AWS STS enables the creation of temporary, limited-privilege credentials for IAM users or federated users, reducing the need for long-lived access keys and the risk associated with key compromise.
- Workload identity federation, this allows the delegation of access to AWS resources to trusted entities, minimizing the need to create and manage IAM users and access keys


And I read some types of attacks. But I did not know if I should include it so as not to extend the document any further. I will leave the link here.

https://cloud.hacktricks.xyz/pentesting-cloud/aws-security/aws-privilege-escalation/aws-iam-privesc