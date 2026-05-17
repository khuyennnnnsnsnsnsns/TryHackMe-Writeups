# Detecting Web Shells
## 1.Webshells overview
webshell là một chương trình độc hại được thực hiện trên máy chủ web mục tiêu ( nó cho phép thực thi lệnh từ xa) 

1.Which MITRE ATT&CK Persistence sub-technique are web shells associated with?

→ Correct answer: T1505.003

2.What file extension is commonly used for web shells targeting Microsoft Exchange?

→Correct answer: .aspx
## 2.Anatomy of a Web Shell
1.Access the shell and determine which account you have access to by running the whoami 

→Correct answer: www-data 
<img width="1291" height="425" alt="1" src="https://github.com/user-attachments/assets/9ad4bc98-8ab2-4ac4-8ec1-6bbed20718d8" />
Hình 1: Sử dụng command : whoami

2.List the directory contents and find the flag using the ls and cat commands.

→Correct answer:THM{W3b_Sh3ll_Usag3}
<img width="1133" height="343" alt="2" src="https://github.com/user-attachments/assets/e50ca4db-fb5f-4268-80e9-6f59b80c4ab5" />
Hình 2 : Sử dụng command : ls + cat flag.txt
## 3.LOG-BASED DETECTION
1.What is the part of the URL that associates values to parameters and can be a valuable indicator of web shell activity?

→Correct answer: query strings

2.What auditd syscall would confirm that a file was written to disk following a suspicious POST request to /upload.php?

→Correct answer:  creat
## 4. BEYOND LOGS
1.What command would you use to locate .php files in the /var/www/ directory?

→Correct answer: ‘’’ find /var/www/ -type f -name "*.php" ’’’
<img width="921" height="840" alt="3" src="https://github.com/user-attachments/assets/23732e3b-1e1f-4100-bb57-97ddffbb2968" />
Hình 3 : sử dụng cmd 

2.Which Wireshark filter would you use to search specifically for PUT requests?

→Correct answer: ‘’’ http.request.method == "PUT" ‘’’
## 5. Investigation
1.Which IP address likely belongs to the attacker?

→Correct answer: 203.0.113.66
<img width="1422" height="882" alt="4" src="https://github.com/user-attachments/assets/3a8cc09f-bbcd-4da9-a586-3b91619c9f40" />
Hình 4 : Dùng ‘’’ cat /var/log/apache2/access.log | grep "404" ‘’’ để tìm ip giống kẻ tấn công 

2.What is the first directory that the attacker successfully identifies?

→Correct answer: /wordpress 
<img width="1283" height="152" alt="5" src="https://github.com/user-attachments/assets/96cfa4c4-d156-43e3-be89-c9b7480233f4" />
Hình 5 : Dùng ‘’’  cat /var/log/apache2/access.log | grep "203.0.113.66" ‘’’ tìm first directory

3.What is the name of the .php file the attacker uses to upload the web shell?

→Correct answer: upload_form.php
<img width="1912" height="92" alt="6" src="https://github.com/user-attachments/assets/71bbebde-f59d-46e1-a3b6-87e8e97278a1" />
Hình 6: Dùng ‘’’ cat /var/log/apache2/access.log | grep "203.0.113.66" | grep "POST" ‘’’

4.What is the first command run by the attacker using the newly uploaded web shell?

→Correct answer: whoami
<img width="1918" height="737" alt="7" src="https://github.com/user-attachments/assets/6debfdd2-67fd-4565-9e59-7f069f4b4720" />
Hình 7: Dùng ‘’’ cat /var/log/apache2/access.log | grep "203.0.113.66" | grep ".php" ‘’’ 

5.After gaining access via the web shell, the attacker uses a command to download a second file onto the server. What is the name of this file?

→Correct answer:linpeas.sh 
<img width="1930" height="753" alt="8" src="https://github.com/user-attachments/assets/8218c44a-b2c9-4f9e-b1cc-9fe3790b7a8b" />

Hình 8: Dùng ‘’’ cat /var/log/apache2/access.log | grep "203.0.113.66" | grep ".php" ‘’’ 

6.The attacker has hidden a secret within the web shell. Use cat to investigate the web shell code and find the flag.

→Correct answer: THM{W3b_Sh3ll_Int3rnals}
<img width="1035" height="232" alt="9" src="https://github.com/user-attachments/assets/57ac2b9c-6641-48d4-ba7c-26eeb780aaf5" />

Hình 9: Dùng ‘’’ cat /var/www/html/wordpress/wp-content/uploads/shadyshell.php ‘’’



