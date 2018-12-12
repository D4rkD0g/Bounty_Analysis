## 0x01 XSS

## 0x02 Analysis

`"><img src=x onerror=prompt(document.domain)>`

1. I watched around 30 XSS POC videos and some write-ups to understand where I can actually find those xss.  
2. I saw an button there “Ask Question”, i clicked on it.In the body field there were many options likes insert link,instert html,insert image so I put the payload in those fields and hoping that the xss will popup.  
3. Just in the first attempt in “insert link” I put my paload in the link, title,tooltip field   
