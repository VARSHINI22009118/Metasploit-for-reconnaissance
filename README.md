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

![Screenshot 2024-04-29 131433](https://github.com/VARSHINI22009118/Metasploit-for-reconnaissance/assets/119401150/1b349fe1-e13a-4747-8e88-ec4c2e8737e7)


Invoke msfconsole:
![Screenshot 2024-04-29 203027](https://github.com/VARSHINI22009118/Metasploit-for-reconnaissance/assets/119401150/e9b02966-ae14-4627-b34a-16c860525c57)


Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![Screenshot 2024-04-29 203116](https://github.com/VARSHINI22009118/Metasploit-for-reconnaissance/assets/119401150/31c45e29-d12b-4456-be2b-e08f48902181)


Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
OUTPUT:

![Screenshot 2024-04-29 203306](https://github.com/VARSHINI22009118/Metasploit-for-reconnaissance/assets/119401150/6b690a88-0b7e-4877-a71c-76880596c60c)

step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
OUTPUT:
![image](https://github.com/VARSHINI22009118/Metasploit-for-reconnaissance/assets/119401150/545d851d-21c0-48ec-b338-cb4b7860ce8f)


Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

OUTPUT:

![Screenshot 2024-04-29 203419](https://github.com/VARSHINI22009118/Metasploit-for-reconnaissance/assets/119401150/1b40499a-2dc9-45d5-9d59-6a056d159ab2)


Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform,

OUTPUT
![Screenshot 2024-04-29 203514](https://github.com/VARSHINI22009118/Metasploit-for-reconnaissance/assets/119401150/21dc46ee-dad7-40be-9c2d-c6aaf31aea28)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![image](https://github.com/VARSHINI22009118/Metasploit-for-reconnaissance/assets/119401150/ad1f90d9-7714-4308-a83e-6f3afb2f67f8)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![Screenshot 2024-04-29 203728](https://github.com/VARSHINI22009118/Metasploit-for-reconnaissance/assets/119401150/060d163a-f25c-4c5f-8be6-38c995827a3d)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![image](https://github.com/VARSHINI22009118/Metasploit-for-reconnaissance/assets/119401150/cc5033cd-d632-4a55-840c-03a6dcca960d)

Use the set rhosts command to set the parameter and run the module, as follows:
![Screenshot 2024-04-29 203904](https://github.com/VARSHINI22009118/Metasploit-for-reconnaissance/assets/119401150/6736dac8-6c02-4938-bd73-184a719073e7)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![Screenshot 2024-04-29 203935](https://github.com/VARSHINI22009118/Metasploit-for-reconnaissance/assets/119401150/1e9c2f51-df9a-46a5-8a21-f03c5e3fd0d8)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
![image](https://github.com/VARSHINI22009118/Metasploit-for-reconnaissance/assets/119401150/24714efb-cd0b-407a-8f54-ce50cfcbe127)



## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
