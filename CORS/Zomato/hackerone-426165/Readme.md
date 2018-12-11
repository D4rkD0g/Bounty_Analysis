## 0x01 CORS Misconfiguration, could lead to disclosure of sensitive information

Bounty	$550  
Severity	Medium (5.9)

## 0x02 Description:

An HTML5 cross-origin resource sharing (CORS) policy controls whether and how content running on other domains can perform two-way interaction with the domain that publishes the policy. The policy is fine-grained and can apply access controls per-request based on the URL and other features of the request.
Trusting arbitrary origins effectively disables the same-origin policy, allowing two-way interaction by third-party web sites. Unless the response consists only of unprotected public content, this policy is likely to present a security risk.  
If the site specifies the header Access-Control-Allow-Credentials: true, third-party sites may be able to carry out privileged actions and retrieve sensitive information. Even if it does not, attackers may be able to bypass any IP-based access controls by proxying through users' browsers.  
Platform(s) Affected: *.zomato.com  

Impact:  
Attacker would treat many victims to visit attacker's website, if victim is logged in, then his personal information is recorded in attacker's server.
If the site specifies the header Access-Control-Allow-Credentials: true, third-party sites may be able to carry out privileged actions and retrieve sensitive information. Even if it does not, attackers may be able to bypass any IP-based access controls by proxying through users' browsers.

How to fix:  
Rather than using a wildcard or programmatically verifying supplied origins, use a whitelist of trusted domains.

PoC:  
Open any browser and go to http://developersxzomato.com/ then inspect the page and go to console.
run the following code in console and you would find it pops up user information var req = new XMLHttpRequest(); req.onload = reqListener; req.open('get','https://www.zomato.com/abudhabi',true); req.withCredentials = true; req.send('{}'); function reqListener() { alert(this.responseText); };

from request I inject a header Origin: developersxzomato.com then from response it returns Access-Control-Allow-Origin: developersxzomato.com Which mean there is CORS misconfig here.