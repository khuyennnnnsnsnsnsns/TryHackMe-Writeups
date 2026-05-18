# Detecting Web DDoS

## Dos and DDos attacks 
Về mục đích thì chúng nhằm làm quá tải để người dùng không thể sử dụng được 

1 What class of attack relies on disrupting the availability of a web service?

→ Correct answer: Denial-of-Service

2 What do we call the network of compromised machines that attackers use to launch DDoS attacks?

→ Correct answer: Botnet

## Attacks motives
1 Which attacker motive aims to make customers lose confidence in a company?

→ Correct answer: Reputational Damage

2. Which motive most likely drove the 2023 DDoS attack against Microsoft?

→ Correct answer: Hacktivism

## Log analysis
Dos/DDos thường tấn công vào việc gửi hàng loạt http truy vấn để làm nghẽn.

1 What is the attacker’s IP address?

→ Correct answer: 203.12.23.195
<img width="1727" height="771" alt="1" src="https://github.com/user-attachments/assets/1b806af0-6b00-4f06-b505-32c064905be8" />

Hình 1: The attacker ip address

2 Which page is repeatedly targeted by the attacker’s requests?

→ Correct answer: /login

<img width="1727" height="771" alt="2" src="https://github.com/user-attachments/assets/5440271a-a7ef-4153-aa2d-3013cf36b5c4" />

Hình 2:  Page is repeatedly targeted by the attacker’s requests

3 After the attack, what error code do legitimate users receive?

→ Correct answer: 503 

<img width="1741" height="768" alt="3" src="https://github.com/user-attachments/assets/bd57c07d-5ed4-4cf7-a482-248ecd4af1c1" />


Hình 3 :  error code do legitimate users receive

## Leveraging SIEMS
1 What was the most frequently requested uri?

→ Correct answer: /search 

<img width="1135" height="723" alt="4" src="https://github.com/user-attachments/assets/b73b75f8-446a-452f-bed7-c407033d80c5" />

2 Which clientip made the most requests to the target uri?

→ Correct answer: 203.0.113.7

<img width="1087" height="496" alt="5" src="https://github.com/user-attachments/assets/9875fcb1-83c7-440b-9787-ee9fed3bc21f" />

3 How many IP addresses were part of the botnet that attacked your website?

→ Correct answer: 60

4 Which useragent was most commonly used by the attacking traffic?

→ Correct answer: Java/1.8.0_181

<img width="1095" height="696" alt="6" src="https://github.com/user-attachments/assets/ecb68690-3f06-470d-a8dc-79bfc0cb4feb" />

5 Use the timechart command to visualize the requests.What is the peak number of requests made per second during the attack?

→ Correct answer: 207

<img width="1343" height="571" alt="7" src="https://github.com/user-attachments/assets/7e271a0a-19ac-4420-9a65-eaeefe81e245" />

6 Which legitimate (non-attacking) clientip received the first 503 response status post-attack?

→ Correct answer: 10.10.0.27

<img width="1376" height="808" alt="8" src="https://github.com/user-attachments/assets/49d66b97-2316-492d-951b-80142afa6d75" />

Hình: using filter ‘’’ index="main" status="503" 
|  table _time clientip uri
‘’’

## Defense 
1  What type of security challenge blocks bots by asking users to solve a simple puzzle?

→ Correct answer: CAPTCHA

2  Which CDN feature spreads traffic across multiple servers to prevent overload?

→ Correct answer: Load-balancing

