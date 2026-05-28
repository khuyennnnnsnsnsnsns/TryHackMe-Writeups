# Windows Threat Detection 3

# Command and Control

1 Which suspicious archive did the user download?

→ Correct answer: URGENT!.zip

<img width="1198" height="813" alt="image5" src="https://github.com/user-attachments/assets/6004c5fa-a993-445a-93b8-8ee2c8c58a84" />

chúng ta cùng kiểm tra thấy rằng user đã mở  google và dowload file có tên URGENT!.zip

2 Where did the attackers hide the C2 malware file?

→ Correct answer:  C:\Users\Administrator\AppData\Roaming\update.exe

<img width="1227" height="527" alt="image3" src="https://github.com/user-attachments/assets/bd5b53ed-56e0-487d-948d-6bbe201b20e7" />

3 What is the domain of the Command and Control server?

→ Correct answer:  route.m365officesync.workers.dev

<img width="1248" height="598" alt="image1" src="https://github.com/user-attachments/assets/e26515a8-bfad-4f4d-bbfe-43299032e2c9" />

# Persistence overview

1 How many times did the threat actor fail to log in to the Administrator?

→ Correct answer: 6

<img width="1397" height="1005" alt="image7" src="https://github.com/user-attachments/assets/b24985e4-5f99-4b50-aab7-730c22e011fd" />

Để kiểm tra xem log fail thì chúng ta filter 2625 để kiểm tra và đếm xem có bao nhiều request tới admin 

2 After the successful login, which backdoor user did the attacker create?

→ Correct answer: support

<img width="1193" height="850" alt="image12" src="https://github.com/user-attachments/assets/25972bda-edfc-4ddf-bb71-d62d42acf0f9" />

Fillter theo event id 4720 để coi người dùng nào vừa được tạo 

3 Which privileged group was the backdoor user added to?

→ Correct answer: Administrators

<img width="1218" height="808" alt="image2" src="https://github.com/user-attachments/assets/a4e7c8b3-bbc5-42bc-a92e-c4b038d7008e" />

Kiểm tra id có số 4732 để coi có user nào được ad vào nhóm có quyền và kiểm tra user support vừa tạo ra được thêm vào quyền nào ở đây chúng ta thấy được thêm vào quyền administrator. 

# Persistence : Tasks and Services 

1 Which Windows service was created to persist the Nessie malware?

→ Correct answer:  Data Protection Service 

<img width="1227" height="591" alt="image10" src="https://github.com/user-attachments/assets/ff8f2b01-4693-4d75-90f9-22d8def25613" />

Fillter theo id 4697 là fillter dịch vụ được tạo ( không phải theo lịch trình ) chúng ta  cùng check sẽ thấy service name của nessie malware

2 Which scheduled task was created to persist the Troy malware?

→ Correct answer: AmazonSync

Fillter này lọc theo lịch trình id 2698 kiểm tra từng id chúng ta sẽ thu được task 

<img width="1182" height="823" alt="image4" src="https://github.com/user-attachments/assets/5724c541-aeda-4d1a-b1a0-25192413cce7" />

3 What flag do you get after finding and running the Troy malware?

→ Correct answer:  THM{c2_is_on_schedule!}

<img width="1466" height="808" alt="image6" src="https://github.com/user-attachments/assets/0efc98f1-33e6-432d-bace-03cb2c1432e9" />

# Persistence : run keys and startups

1 What is the parent process image of the "Odin" malware?

→ Correct answer:C:\Windows\explorer.exe

Tìm nơi tiến trình odin đầu tiên kiếm image  parent chúng ta sẽ tìm ra 

<img width="1202" height="842" alt="image11" src="https://github.com/user-attachments/assets/5350d2ab-7bf4-4977-b99d-5666b15d4729" />

2 What is the last line that the "Odin" malware outputs?

→ Correct answer:Done doing bad stuff! 

mở đường dẫn của odin.cmd chạy nó sẽ hiện  ra  được dòng chữ cuối cùng chúng ta cần tìm.

<img width="1280" height="613" alt="image8" src="https://github.com/user-attachments/assets/924ca326-fee7-4944-9379-4067790fb064" />

3 What flag do you get after finding and running the "Kitten" malware?

→ Correct answer: THM{persisting_in_basket!} 

<img width="1475" height="896" alt="image9" src="https://github.com/user-attachments/assets/2daef313-7623-4367-8735-b5e0b649d9e4" />

command basket 


# impact and threat detection recap 

1 What is the biggest threat to most corporate Windows networks?

→ Correct answer: Ransomware

2 At which stage is it best to detect and stop the attack (e.g. Exfiltration)?

→ Correct answer: Initial Access
