# Windows Threat Detection 1

# Intro to initial access 

1 Which MITRE technique ID describes Initial Access via a vulnerable mail server?

→ Correct Answer : T1190

2 Which Initial Access method relies on a user opening a malicious email attachment?

→ Correct Answer : Phishing

# initial access via RDP 

1 Which user seems to be most actively brute-forced by botnets?

→ Correct Answer : Administrator

Để xem người dùng nào bị tấn công chúng ta lọc theo ID 4625 là lọc theo các lần đăng nhập không thành công, nó sẽ hiện ra một list kiểm tra thì chúng ta sẽ thấy user bị tấn công chính là Administrator 

<img width="1918" height="1112" alt="image5" src="https://github.com/user-attachments/assets/9c75e7e1-855a-4098-998d-6f539dfbdd43" />

2 Which IP managed to breach the host via RDP (Logon Type 10)?

→ Correct Answer :  203.205.34.107 

Ở đây khi đăng nhập được vào máy chủ thì chúng ta sẽ lọc id là 4624 để hiện ra bảng , sau đó kiểm tra detail xem user admin được đăng nhập ở đâu và login type sẽ là 10 vì đây là login type đăng nhập từ xa mà có thể đã bị tấn công để kiếm được địa chỉ ip. 

<img width="1287" height="508" alt="2" src="https://github.com/user-attachments/assets/01ac42ad-7f8e-48f3-a3e5-98a301e10d2c" />

3 Can you get the real Workstation Name (hostname) of the threat actor?

→ Correct Answer : DESKTOP-QNBC4UU

Chúng ta đã có được ip của kẻ tấn công thì sẽ follow theo ip của kẻ tấn công để tim real workstation name của kẻ tấn công, tìm nơi có login type là 3 vì đây sẽ là nơi xác định nguồn đăng nhập kết nối mạng. 

<img width="1306" height="828" alt="3" src="https://github.com/user-attachments/assets/00c2944d-fd2a-4e01-a13b-728448efc780" />

# Initial access via phishing 

1 Let's play the role of the untrained user and mindlessly open the COM file.

Run the www.skype.com file from the Phishing Case 1 folder, which flag do you get?

→ Correct Answer : THM{misleading_extension}

<img width="1221" height="267" alt="4" src="https://github.com/user-attachments/assets/df8f7f42-d49b-4d1e-8aa2-4c4d36db24cf" />

2 Continue with the second attachment from the Phishing Case 2 folder.

From which URL does the malicious LNK download the next stage malware?

→ Correct Answer : http://wp16.hqywlqpa.thm:8000/cgi-bin/f

<img width="1393" height="712" alt="5" src="https://github.com/user-attachments/assets/8159c451-16cb-42eb-a607-b11fcb367b78" />


3 Finally, move on to the Phishing Case 3 folder and review its content.

What is the name of the double-extension file you see there?

→ Correct Answer : best-cat.jpg.exe

<img width="1491" height="392" alt="6" src="https://github.com/user-attachments/assets/00f57a42-7e13-4044-8da2-10eed46256d9" />


# Continuing phishing topic

1 Which file did the user download via the web browser?

→ Correct Answer :C:\Users\Administrator\Downloads\top-cats.zip 

<img width="1317" height="787" alt="7" src="https://github.com/user-attachments/assets/5658d8a8-a217-45ee-af07-43a0645283f1" />

2 In which folder did the user unarchive the suspicious file?

→ Correct Answer :C:\Users\Administrator\Pictures

<img width="1318" height="755" alt="8" src="https://github.com/user-attachments/assets/ee6651a2-39bb-4594-be35-308e6d293a49" />

3 What is the process ID of the launched phishing malware?

→ Correct Answer : 5484 

<img width="1366" height="760" alt="9" src="https://github.com/user-attachments/assets/34b3cd1f-d968-4dc6-8b9a-d4e6750f8195" />

4 Finally, which malicious domain did the malware try to connect to?

→ Correct Answer : rjj.store

Ngay sau khi tìm được tiến trình của mã độc  ta xem xét ngay sau đó sẽ thấy tiến trình query dns và tên miền mà phần mềm mã độc muốn kết nối sẽ hiện ra. 

<img width="1322" height="741" alt="10" src="https://github.com/user-attachments/assets/34e2f807-9f6c-4a27-8d54-f2099b70410c" />

# Initial access via USB 

1 Which USB file was launched by the user?

→ Correct Answer :E:\Open Sandisk 4GB USB.exe

<img width="1325" height="632" alt="image11" src="https://github.com/user-attachments/assets/a9f44342-58fe-4fe6-a9b5-e1826e600437" />

2 Which suspicious file did the malware drop to the disk?

(Format: full path to the file, e.g. C:\file.txt)

→ Correct Answer :C:\Users\Public\Documents\winupdate.exe

<img width="1318" height="807" alt="image13" src="https://github.com/user-attachments/assets/cfe28379-0017-4f0c-8b27-2245d9e3c481" />

Ngay sau khi mở file usb thì chúng ta thấy nó đã copy 1 file .exe 

3 To which other USB did the malware propagate?

(Format: just the letter, e.g. X:)

→ Correct Answer :F:

Sau khi chạy file mã độc thì nó đã lan tới usb  của  ổ đỉa khác 

<img width="1348" height="877" alt="image9" src="https://github.com/user-attachments/assets/5e28c62e-f066-4e17-b1d9-7a3983832998" />


