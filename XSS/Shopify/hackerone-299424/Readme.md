## 0x01 Cross-site Scripting (XSS) - Stored

Bounty	$3,000  
Severity	High (8.1)  

## 0x02 Analysis

可上传SVG，当SVG有XML entity时可以绕过白名单to include malicious attributes such as onload

1. create a new application within the Partners dashboard 
2. "Extensions" -> "Sales channel" to convert the application. 
3. a new field within the "App info" section titled "Navigation icon". Upload the following SVG:

`<svg><!--?php "--><script>confirm(20)</script>?&gt;</svg>`
