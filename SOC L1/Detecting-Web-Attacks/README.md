
# DECTECTING WEB ATTACKS 

Mục tiêu : Cách nhận diện các mối đe dọa tấn công mạng bằng các phương pháp phát sv hiện thực tế, và các công cụ trong ngành.
## 1.CLIENT_SIDE ATTACKS
XSS : tấn công chèn mã độc hại

CSRF :  tấn công thay mặt người dùng để đánh lừa trình duyệt

ClickJacking : tấn công chèn các yếu tố vô hình làm cho người dùng ngỡ mình đang dùng mọi thứ an toàn 

ANSWER THE QUESTIONS

What class of attacks relies on exploiting the user's behavior or device?

→ Correct answer : Client-side

What is the most common client-side attack?

→ Correct answer : XSS

## 2.SERVER-SIDE ATTACKS
BRUTE-FORCE ATTACK: kẻ tấn công sử dụng tài khoản và mật khẩu để truy cập trái phép vào tài khoản .

SQLi : tấn công vào cơ sở dữ liệu để truy xuất dữ liệu nội bộ.

Command-Injection: khi web nhận dữ liệu người dùng mà không kiểm tra khi chuyển tiếp tới hệ thống, kẻ tấn công sẽ chèn các đoạn lệnh khiến máy chủ thực thi.

ANSWER THE QUESTIONS

What class of attacks relies on exploiting vulnerabilities within web servers?

→ Correct answer : Server-side

Which server-side attack lets attackers abuse forms to dump database contents?

→ Correct answer : SQLi
## 3. LOG-BASED DETECTION
Lưu ý : GET là khi truy cập vào các trang để máy chủ trả về còn POST là các thông tin như là password or account để đăng nhập 

ANSWER THE QUESTIONS USING ACCESS.LOG 

What is the attacker's User-Agent while performing the directory fuzz?

→ Correct answer : FFUF v2.1.0
<img width="1913" height="487" alt="1" src="https://github.com/user-attachments/assets/4c1e6544-980d-43be-9017-666e949b2f9e" />

Ảnh 1: the attacker's User-Agent

What is the name of the page on which the attacker performs a brute-force attack?

→ Correct answer :/login.php
<img width="1328" height="345" alt="2" src="https://github.com/user-attachments/assets/9c8e21d4-45ea-4c18-abeb-f9fac59b04b1" />

Ảnh 2:  the name of the page on which the attacker performs a brute-force attack

What is the complete, decoded (opens in new tab) SQLi payload the attacker uses on the /changeusername.php form?

→ Correct answer :%' OR '1'='1
<img width="1878" height="943" alt="3" src="https://github.com/user-attachments/assets/19adb3ab-b573-46a5-bcd2-1c1b6bd2b320" />

Ảnh 3: SQLi payload decoded 
## 4. NETWORK-BASED DETECTION
ANSWER THE QUESTIONS USING TRAFFIC.PCAP

What password does the attacker successfully identify in the brute-force attack?

→ Correct answer : astrongpassword123
<img width="1932" height="822" alt="4" src="https://github.com/user-attachments/assets/a86f80ca-c282-4e47-b612-fa4d0bed5a2e" />

Ảnh 4: password does the attacker successfully identify in the brute-force attack

What is the flag the attacker found in the database using SQLi?

→ Correct answer :THM{dumped_the_db}
<img width="1918" height="802" alt="5" src="https://github.com/user-attachments/assets/cdf08640-ddeb-4833-a44e-c47c9d343a0e" />

Ảnh 5:  using follow http to find flag 

## 5. WEB APPLICATION FIREWALL
ANSWER THE QUESTIONS

What do WAFs inspect and filter?

→ Correct answer : Web Requests

Create a custom firewall rule to block any User-Agent that matches "BotTHM".

→ Correct answer : IF User-Agent CONTAINS "BotTHM" THEN block

