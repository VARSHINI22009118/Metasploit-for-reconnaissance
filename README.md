# EX 05 Metasploit-for-reconnaissance
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
```
NAME : VARSHINI S A
REGISTER NUMBER : 212222100059
```

## EXECUTION STEPS AND ITS OUTPUT:
Find out the ip address of the attackers system
![170bedfd-5515-412a-8add-c8a1d97484ef](https://github.com/deepikasrinivasans/Metasploit-for-reconnaissance/assets/119393935/8af9633f-724f-40c4-b333-537f34243721)
Invoke msfconsole:
![bb8f89e6-7fba-4d39-83fc-52e1152c3bd8](https://github.com/deepikasrinivasans/Metasploit-for-reconnaissance/assets/119393935/0db16e5e-ff11-4d06-8f72-db7d80703fc7)
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![image](https://github.com/Naveenaa28/Metasploit-for-reconnaissance/assets/131433133/814f3e01-93e2-494a-9434-11f32e34b293)
Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
![image](https://github.com/Naveenaa28/Metasploit-for-reconnaissance/assets/131433133/782125d5-dfd5-4487-ac45-569e564b58e9)
use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later. scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
![image](https://github.com/Naveenaa28/Metasploit-for-reconnaissance/assets/131433133/1d55c8be-ae1f-408b-b777-2146a0b3c74a)
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l
![image](https://github.com/Naveenaa28/Metasploit-for-reconnaissance/assets/131433133/8d9bfd2b-6e0d-4c63-8b29-7a3264563f62)
Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit
![image](https://github.com/Naveenaa28/Metasploit-for-reconnaissance/assets/131433133/04c6792c-c539-4654-80a6-367108f24965)
The info command provides information regarding a module or platform
![image](https://github.com/Naveenaa28/Metasploit-for-reconnaissance/assets/131433133/d4977770-bac1-48fd-9238-f89dcaaa509c)
Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![image](https://github.com/Naveenaa28/Metasploit-for-reconnaissance/assets/131433133/e4156442-6cf5-45fa-83c6-10dfbb6c3d6c)
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![image](https://github.com/Naveenaa28/Metasploit-for-reconnaissance/assets/131433133/e9765b55-f7fd-46bb-a34c-617de8111df2)
use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![image](https://github.com/Naveenaa28/Metasploit-for-reconnaissance/assets/131433133/7d98154f-f495-4fe3-bb15-323654a6d169)
Use the set rhosts command to set the parameter and run the module, as follows:
![image](https://github.com/Naveenaa28/Metasploit-for-reconnaissance/assets/131433133/712d0971-a80e-461e-805c-3275fc1d71ee)
After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module. 
![image](https://github.com/Naveenaa28/Metasploit-for-reconnaissance/assets/131433133/7f653cef-96e3-4c1d-a5df-02f5d16febe7)
set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
![image](https://github.com/Naveenaa28/Metasploit-for-reconnaissance/assets/131433133/fdb5cabf-877c-4bb1-876d-6c6208d8d4be)
## RESULT:
The Metasploit framework for reconnaissance is  examined successfully

