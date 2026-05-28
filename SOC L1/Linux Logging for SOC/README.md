# Linux Logging for SOC

# Working with text log 

1 Use the /var/log/syslog file on the VM to answer the questions.

Which time server domain did the VM contact to sync its time?

--> Correct Answer: ntp.ubuntu.com
<img width="1918" height="973" alt="image2" src="https://github.com/user-attachments/assets/c0ac9776-0acb-47ee-a746-728aa37f17d7" />

2 What is the kernel message from Yama in /var/log/syslog?

--> Correct Answer: Becoming mindful.

<img width="946" height="222" alt="image6" src="https://github.com/user-attachments/assets/566e0f1f-5474-4c68-99b4-27c587cd5e5c" />

# Authentication logs

1 Continue with the VM and use the /var/log/auth.log file.

Which IP address failed to log in on multiple users via SSH?

--> Correct Answer: 10.14.94.82
<img width="1918" height="832" alt="image8" src="https://github.com/user-attachments/assets/a0d05d74-8273-451b-8655-2fe017289538" />

2 Which user was created and added to the "sudo" group?

--> Correct Answer: xerxes

<img width="1918" height="577" alt="image3" src="https://github.com/user-attachments/assets/e0c66ed7-5319-4c1d-b4c8-8af29e11ee02" />

# Common linux logs 

1 According to the VM's package manager logs,

which version of unzip was installed on the system?

--> Correct Answer: 6.0-28ubuntu4.1

<img width="933" height="212" alt="image1" src="https://github.com/user-attachments/assets/2c6b7c49-cb0e-416c-8ad6-58d927463acb" />

What is the flag you see in one of the users' bash history?

--> Correct Answer: THM{note_to_remember}

<img width="824" height="787" alt="image5" src="https://github.com/user-attachments/assets/d2bee5b4-3875-454b-b99e-0e3e490a14d3" />

# Runtime monitoring 

1 Which Linux system call is commonly used to execute a program?

--> Correct Answer: execve

2 Can a typical program open a file or create a process bypassing system calls? (Yea/Nay)

--> Correct Answer: Nay

# Using auditd

1 When was the secret.thm file opened for the first time? (MM/DD/YY HH:MM:SS)

Note: Access to this file is logged with the "file_thmsecret" key.

--> Correct Answer: 08/13/25 18:36:54

<img width="1918" height="265" alt="image4" src="https://github.com/user-attachments/assets/0d3763b6-8da3-4fa3-a3f5-44f8338f846e" />


2 What is the original file name downloaded from GitHub via wget?

Note: Wget process creation is logged with the "proc_wget" key.

--> Correct Answer: naabu_2.3.5_linux_amd64.zip

<img width="1923" height="656" alt="image7" src="https://github.com/user-attachments/assets/41545901-81a2-4730-b253-112e065071f8" />


3 Which network range was scanned using the downloaded tool?

Note: There is no dedicated key for this event, but it's still in auditd logs.

--> Correct Answer: 192.168.50.0/24

<img width="1918" height="862" alt="image9" src="https://github.com/user-attachments/assets/c75c0096-64a2-4291-817f-44b361445e1c" />
