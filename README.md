# Web Security
## Hackers 
Black hat - Hack for money cause the problem.
Gray hat - Hack for curiosity and then report to the compony.
White Hat - Appointed by compony to test their products. 

## Type of Attacks 
![](Screen%20Shot%202019-12-01%20at%206.45.35%20PM.png)

## XSS Defenses 
1. Sanitize user input data - Escape user data before putting in HTML
	1. Never trust user input data - Don’t use user input data directly at Dom node, attribute or tag name
	2. Treat user input data as value not as code.
	
2. Content Security policies
	1. Browser can’t tell the difference between script downloaded from your browser and other browser it’s all in same execution context.
	2. CSP allow modern browser to which source they should trust and with type of resources.
	3. This information comes via  HTTP response header or meta tag.
	Content-Security-Policy: ~script-src~ ‘self’ https://trustedSite/;
						     ~font-src~ https://fonts.googleapi.com
![](Screen%20Shot%202019-12-01%20at%207.58.09%20PM.png)

3. Malicious attachments.
	1. Use can add the html content to the .jpg image. Which can be render on screen.
	2. To avoid this do the image compression. They will drop the non visible data.

4. Cross Site Request Forgery (CSRF)
	1. Taking advantage of the fact that cookies (or basic authentication credentials ) are passed along with the request.
	2. If we make the get request with URL param to transfer money from one account to another with image tag. And p[ass this image to the user.
	Then the request for image url will be made and cookies will be passed along with the credentials. By the time request 		finished amount will be transfer to the different account.
	3. To avoid this we should not use the Get request to mutate data.
	4. But even hacker can make the post request happen with some submit of the hidden form on the screen.
	5. Use CSRF token can be use as two-factor authentication.
	6. Modern browser send the Origin header.
	7. CORS
		1. Make preflight request 
		2. Once this is authenticated main request will be maid
	
5. Clickjacking attacks 
	1. A “UI redress attacks”. User is thinking he is interacting with on site but he is actually on another site which domain looks like same. Some times hackers load the actual site in iframe on their fishy site so use will feel they are on correct site. 
	2. Here hacker attacking user not the system.
	3. Defenses:
		1. XTTP response header
		X-Frame-Options: DENY
		X-Frame-Options: SAMEORIGIN
		X-Frame-Options: ALLOW-FROM https://abc.com/ (Chrome/ Safari don’t respect ALLOW-FROM use ‘frame-				ancestors’ csp directive instead.)

6. Third party assets



