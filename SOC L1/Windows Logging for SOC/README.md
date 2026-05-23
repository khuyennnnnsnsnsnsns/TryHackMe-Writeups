# Windows Logging for SOC

## What is logged 

1 Looking at the last screenshot, which event ID describes a successful login? (Answer format: LogSource / ID, e.g. Application / 8194) 

→ Correct answer: Security / 4624

<img width="1597" height="497" alt="1" src="https://github.com/user-attachments/assets/418ec03a-74f3-4dc7-abe3-d0ef79abccfe" />

## Security log: Authentication

1 Open the "Practice-Security.evtx" file on the VM's Desktop. Which IP performed a brute force of the THM-PC?

→ Correct answer: 10.10.53.248

<img width="1692" height="780" alt="2" src="https://github.com/user-attachments/assets/24bbdf18-1144-4b39-9efc-eaf4dfb95eac" />

2 Which user has been breached as a result of the attack?

→ Correct answer: Administrator

<img width="705" height="532" alt="3" src="https://github.com/user-attachments/assets/1b410193-7b3d-4a81-8553-7f483b435d43" />

3 What was the Logon ID of the malicious RDP login?

Note: The login you are looking for has a Logon Type 10.

→ Correct answer: 0x183C36D

<img width="1301" height="775" alt="4" src="https://github.com/user-attachments/assets/7e639031-0274-44b1-aa07-8bd02a820648" />

## Security log: user management

1 Continue with the "Practice-Security.evtx" file on the VM's Desktop.

Which user was created by the attacker soon after the RDP login?

→ Correct answer: svc_sysrestore

<img width="1326" height="562" alt="5" src="https://github.com/user-attachments/assets/8b7ddae1-86b9-4ffe-9ae6-ae220d60b34d" />

Picture: filter event ID 4720 find  user was created by the attacker soon after the RDP login

2 Which two privileged groups was the backdoor user added to?

(Answer in alphabetical order, e.g. "Administrators, Power Users")

→ Correct answer: Backup Operators, Remote Desktop Users

<img width="1590" height="901" alt="6 1" src="https://github.com/user-attachments/assets/bc7b1398-61c7-4a0f-81d4-399593482527" />

<img width="1129" height="613" alt="6" src="https://github.com/user-attachments/assets/f44c86bc-4639-4c61-817b-6359c83642f2" />

3 Does the Logon ID field match what you saw in the previous task (Yea/Nay)?

→ Correct answer: ye

## Sysmon process monitoring 

1 Open the "Practice-Sysmon.evtx" file on the VM's Desktop.

Which web browser does Sarah use to browse the web?

→ Correct answer: Google Chrome

2 Which file did Sarah download from the browser?

→ Correct answer: C:\Users\sarah.miller\Downloads\ckjg.exe

<img width="1388" height="762" alt="7" src="https://github.com/user-attachments/assets/ac220520-2ea6-4b6b-9fb2-d98d6f185aaf" />

3 Which URL was the file downloaded from?

Note: Use other Sysmon events to find out!

→ Correct answer: http://gettsveriff.com/bgj3/ckjg.exe

<img width="1408" height="743" alt="8" src="https://github.com/user-attachments/assets/8cd42555-5902-4e25-be03-2255e7fa3eea" />

<img width="1918" height="1107" alt="9" src="https://github.com/user-attachments/assets/ab3d8c7b-a973-4051-97a8-09f000e63a7f" />

## Sysmon files and network 
1 Continue with the "Practice-Sysmon.evtx" file on the VM's Desktop.

Which file was created by the downloaded malware to persist on the host?

→ Correct answer: C:\Users\sarah.miller\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup\DeleteApp.url 

<img width="1587" height="891" alt="10" src="https://github.com/user-attachments/assets/c9b4f4db-c776-4ab8-84f1-f144be26ceeb" />

2 What is the Command & Control server malware connected to?

(Answer in format IP:Port, e.g. 1.1.1.1:80)

→ Correct answer: 193.46.217.4:7777

<img width="1346" height="791" alt="11" src="https://github.com/user-attachments/assets/2e3aedd4-4071-45fe-bb3b-787fd0f082bf" />

3 Finally, which domain does the malicious IP correspond to?

→ Correct answer: hkfasfsafg.click

<img width="1181" height="972" alt="12" src="https://github.com/user-attachments/assets/0d79dcce-1e93-4300-9348-32da3c450e94" />


## powershell logging commands 

1 Review the Administrator's PS history on the attached VM.

Which PowerShell command was executed first?

→ Correct answer:  Get-ComputerInfo

<img width="1510" height="530" alt="13" src="https://github.com/user-attachments/assets/275d05a2-0ee8-4962-b302-39f466339588" />

2 When did the Administrator run the first PS command? (Format: April 18, 2025)

Note: You might need to right-click the history file and open "Properties" to get the answer!

→ Correct answer: May 18, 2025

<img width="462" height="547" alt="14" src="https://github.com/user-attachments/assets/204ad9b7-bf95-4162-8479-34fb9f7d0ea2" />

3 Can you find the flag stored in the PowerShell history? (Format: THM{...})

Note: You might want to check the PS history of other local users!

→ Correct answer: THM{it_was_me!}

<img width="1557" height="647" alt="15" src="https://github.com/user-attachments/assets/f56f131a-0cc7-46d0-af8b-97993f2e6a26" />



