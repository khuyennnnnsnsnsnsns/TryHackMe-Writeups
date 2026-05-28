# Windows Threat Detection 3

# Command and Control

1 Which suspicious archive did the user download?

→ Correct answer: URGENT!.zip

chúng ta cùng kiểm tra thấy rằng user đã mở  google và dowload file có tên URGENT!.zip

2 Where did the attackers hide the C2 malware file?

→ Correct answer:  C:\Users\Administrator\AppData\Roaming\update.exe

3 What is the domain of the Command and Control server?

→ Correct answer:  route.m365officesync.workers.dev


# Persistence overview

1 How many times did the threat actor fail to log in to the Administrator?

→ Correct answer: 6

Để kiểm tra xem log fail thì chúng ta filter 2625 để kiểm tra và đếm xem có bao nhiều request tới admin 

2 After the successful login, which backdoor user did the attacker create?

→ Correct answer: support

Fillter theo event id 4720 để coi người dùng nào vừa được tạo 

3 Which privileged group was the backdoor user added to?

→ Correct answer: Administrators

Kiểm tra id có số 4732 để coi có user nào được ad vào nhóm có quyền và kiểm tra user support vừa tạo ra được thêm vào quyền nào ở đây chúng ta thấy được thêm vào quyền administrator. 

# Persistence : Tasks and Services 

1 Which Windows service was created to persist the Nessie malware?

→ Correct answer:  Data Protection Service 

Fillter theo id 4697 là fillter dịch vụ được tạo ( không phải theo lịch trình ) chúng ta  cùng check sẽ thấy service name của nessie malware

2 Which scheduled task was created to persist the Troy malware?

→ Correct answer: AmazonSync

Fillter này lọc theo lịch trình id 2698 kiểm tra từng id chúng ta sẽ thu được task 

3 What flag do you get after finding and running the Troy malware?

→ Correct answer:  THM{c2_is_on_schedule!}

# Persistence : run keys and startups

1 What is the parent process image of the "Odin" malware?

→ Correct answer:C:\Windows\explorer.exe

Tìm nơi tiến trình odin đầu tiên kiếm image  parent chúng ta sẽ tìm ra 

2 What is the last line that the "Odin" malware outputs?

→ Correct answer:Done doing bad stuff! 

mở đường dẫn của odin.cmd chạy nó sẽ hiện  ra  được dòng chữ cuối cùng chúng ta cần tìm.

3 What flag do you get after finding and running the "Kitten" malware?

→ Correct answer: THM{persisting_in_basket!} 

command basket 


# impact and threat detection recap 

1 What is the biggest threat to most corporate Windows networks?

→ Correct answer: Ransomware

2 At which stage is it best to detect and stop the attack (e.g. Exfiltration)?

→ Correct answer: Initial Access
