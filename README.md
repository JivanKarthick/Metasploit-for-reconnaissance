# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## PROGRAM:
Find out the ip address of the attackers system


## OUTPUT:

![image](https://github.com/JivanKarthick/Metasploit-for-reconnaissance/assets/121165867/83fdf10a-a58d-40eb-b0e9-0c58734c3b49)


## Invoke msfconsole:
## OUTPUT:
![image](https://github.com/JivanKarthick/Metasploit-for-reconnaissance/assets/121165867/8e34f226-af2f-40c4-bd4e-3ab5a81831e2)


Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## OUTPUT:
![image](https://github.com/JivanKarthick/Metasploit-for-reconnaissance/assets/121165867/6c29ec32-4902-4bd9-8111-b2d2bb8c3f30)


Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:

![image](https://github.com/JivanKarthick/Metasploit-for-reconnaissance/assets/121165867/79cb0e04-bfb6-4ca9-9c49-53042e88dd93)


 ## Step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:
![image](https://github.com/JivanKarthick/Metasploit-for-reconnaissance/assets/121165867/708d0cbe-e312-4c59-8142-ef6d63746c0d)


Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:

![image](https://github.com/JivanKarthick/Metasploit-for-reconnaissance/assets/121165867/4096badb-746b-4b41-9c59-9ad9bf679f3a)


![image](https://github.com/JivanKarthick/Metasploit-for-reconnaissance/assets/121165867/8aa8540b-4b8b-4b91-bdac-478b2b0c549b)


Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![image](https://github.com/JivanKarthick/Metasploit-for-reconnaissance/assets/121165867/5eb1c734-7aab-4b57-a624-ab749a4ee933)


The info command provides information regarding a module or platform
## OUTPUT:

![image](https://github.com/JivanKarthick/Metasploit-for-reconnaissance/assets/121165867/a691e9c7-cb59-4e09-b521-fe316acb295f)


Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![image](https://github.com/JivanKarthick/Metasploit-for-reconnaissance/assets/121165867/de7e755d-f609-414d-b627-2a3596d6efdf)


Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/JivanKarthick/Metasploit-for-reconnaissance/assets/121165867/6b6e95dc-ed87-478d-97a0-4146bf2b8bbc)


use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/JivanKarthick/Metasploit-for-reconnaissance/assets/121165867/cab1f4bb-1669-49b7-b38b-e6ce2ebbf04f)


Use the set rhosts command to set the parameter and run the module, as follows:

![image](https://github.com/JivanKarthick/Metasploit-for-reconnaissance/assets/121165867/ec67a381-80e5-4418-8ed0-36e1530ca941)


After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/JivanKarthick/Metasploit-for-reconnaissance/assets/121165867/dc87c0e9-0d2d-4578-8523-88359351a0ca)


set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/JivanKarthick/Metasploit-for-reconnaissance/assets/121165867/9e4cdffd-7fc8-4e71-a6df-fb213f4a700b)



## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
