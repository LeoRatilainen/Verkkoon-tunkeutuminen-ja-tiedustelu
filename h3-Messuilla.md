### En saanut lippua tapahtumaan niin teen vaihtoehtoisen tehtävän: laadi tiivistelmä täyspitkästä hakkeritapahtuman esityksestä verkosta löytämästäsi videosta.

# x)
## This is a talk given by Dr Nestori Syynimaa at the disobey event: Syynimaa, N. https://www.youtube.com/watch?v=b-9d5UXOcaA

The talk is segmented into 4 sections 

### Introduction
- Explanation of how HTTP authentication works
  
		1. The client uses a GET method to ask the server for something. 
		2. If not authenticated the server then asks the client to do so and tells you what schemes it supports.
		3. The client then gives the authentication.
		4. And if the server is happy responds with something.
		5. After this usually a session cookie is used so the user doesn't need to authenticate over and over.
- Key roles used in the talk are.
  
		1. User.
		2. Service provider (SP).
		3. Identity provider (IdP).

### Federated authentication methods
  - A few examples of these methods are given such as.
	- Kerberos authentication flow.
		1. This works with the user authenticating themselves. 
		2. They then recieve a Ticket Granting Ticket (TGT) that. 
		3. They can use this to tell the IdP that they want to use a service and will recieve a service ticket (ST).
		4. After this they can use the service with the ST.
	- SAML authentication flows.
		1. Attempt to use a service.
		2. Get redirected to IdP.
		3. Authenticate.
		4. Recieve a SAML user token that then can be used for the services.
	- Simplified OAuth authentication flow.
		1. User authenticates with the IdP.
		2. Recieves an access token and a refresh token.
		3. Then you can use the services.

### Token based authentication attacks
  - If any unintended party gains access to the bearer token it can be used to access the associated resources or services without providing a cryptographic key.
  - A few MITRE ATT&CK techniques given are.
	  - Unsecured Credentials: Private keys. MITRE ATT&Ck: https://attack.mitre.org/techniques/T1552/004/
	  - Forge Web Credentials. MITRE ATT&Ck: https://attack.mitre.org/techniques/T1606/
	  - Access Token Manipulation: Token Impersonation/Theft. MITRE ATT&Ck: https://attack.mitre.org/techniques/T1134/001/
  - The three roles in this case are.
	  - Tokens are stolen from the user.
	  - Secrets are stolen from IdP.
	  - And you use them with SP.
  - Adversary-in-the-middle attack.
	  - is this form of attack the user is sent a malicious link that looks like a site they know, but it goes through a
	   third uninvited party that is then able to get access to the user's tokens and credentials.
  - A few demos are then given in the talk to demostrate how these attacks might work.

### Detecting and preventing
  - Logs are very important to save at every step of the authentication process
  - There are 4 different scenarios given
      - On-prem identity
      - Hybrid identity
      - Cloud-only identity 1
      - Cloud-only identity 2
  - Best prevention pratices are
    - Harden your tier 0 meaning what ever IdP is used.
    - Zero trust for users.
    - Always verify if providing the services such as user logs.
# Sources

Karvinen 2025: https://terokarvinen.com/verkkoon-tunkeutuminen-ja-tiedustelu/

Syynimaa, N 11.03.2025 [D25] Exploiting Token Based Authentication - Dr Nestori Syynimaa. Disobey: https://www.youtube.com/watch?v=b-9d5UXOcaA

MITRE ATT&Ck: https://attack.mitre.org/
