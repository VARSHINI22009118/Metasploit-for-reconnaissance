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


## OUTPUT:
![image](https://github.com/1808charitha/Metasploit-for-reconnaissance/assets/132996838/584a6e38-f7f5-48d1-a794-e46919e7f8d8)

Invoke msfconsole:
![image](https://github.com/1808charitha/Metasploit-for-reconnaissance/assets/132996838/8ece81bd-8d91-498d-91cc-18096809bf40)
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![image](https://github.com/1808charitha/Metasploit-for-reconnaissance/assets/132996838/6d8173b7-464c-4be9-9c3c-075633e02d2b)
Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
OUTPUT:
![image](https://github.com/1808charitha/Metasploit-for-reconnaissance/assets/132996838/ff252e3e-fe1e-4a93-b754-5d4ced4f68b7)
step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
OUTPUT:
![image](https://github.com/1808charitha/Metasploit-for-reconnaissance/assets/132996838/3ee66371-ccc9-4245-b5ff-5356809e362c)
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

OUTPUT:
![image](https://github.com/1808charitha/Metasploit-for-reconnaissance/assets/132996838/fbb24c97-3807-46e7-b06b-c3b625967215)
Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform,

OUTPUT
![image](https://github.com/1808charitha/Metasploit-for-reconnaissance/assets/132996838/97a56fd6-c08c-43d3-8816-6a1fcef38c56)
Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![image](https://github.com/1808charitha/Metasploit-for-reconnaissance/assets/132996838/93452bc1-249d-4a05-bda6-140c2db75eea)
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![image](https://github.com/1808charitha/Metasploit-for-reconnaissance/assets/132996838/fde3f8b6-db49-4248-8f77-39d61ea12557)
use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![image](https://github.com/1808charitha/Metasploit-for-reconnaissance/assets/132996838/93d8988f-b7a0-46c2-b816-262083158bf4)
Use the set rhosts command to set the parameter and run the module, as follows:
![image](https://github.com/1808charitha/Metasploit-for-reconnaissance/assets/132996838/41895fb8-8adf-4e5d-a486-0bb7cfda2f8c)
After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![image](https://github.com/1808charitha/Metasploit-for-reconnaissance/assets/132996838/e3a3574e-8c7e-4148-9cf5-5064b270f690)
set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
![image](https://github.com/1808charitha/Metasploit-for-reconnaissance/assets/132996838/671d8b95-a4c4-4be3-a006-52c6dccf5803)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
