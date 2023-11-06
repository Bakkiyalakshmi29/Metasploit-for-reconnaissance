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

PROGRAM:

Find out the ip address of the attackers system.
OUTPUT:

Invoke msfconsole:

![273782143-fb9ee731-6a06-4db2-bf87-8739851ad4da](https://github.com/Bakkiyalakshmi29/Metasploit-for-reconnaissance/assets/119406233/75244f17-b95e-4a8e-a28e-39dd9a493a20)

OUTPUT:

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole: ![273782318-05321f33-8c8f-412c-b94f-c7301f6218de](https://github.com/Bakkiyalakshmi29/Metasploit-for-reconnaissance/assets/119406233/9dca98d5-2a62-44fe-9ec1-1b1bddcc4a7a)



Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
OUTPUT:

step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24 ![273782654-23181869-34cf-42b6-b1a1-76dcac6baf07](https://github.com/Bakkiyalakshmi29/Metasploit-for-reconnaissance/assets/119406233/62bdfa09-8b58-4bb1-bb57-37afa281fc06)

OUTPUT:

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l ![273782953-86701abe-eea5-4c19-a0b4-ff7df4ac9168](https://github.com/Bakkiyalakshmi29/Metasploit-for-reconnaissance/assets/119406233/e1b281f3-acc8-464c-8967-3a0ed2fceb40)

OUTPUT:

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit ![273783181-5a78cefa-970f-49dc-a6aa-4820ac8ed704](https://github.com/Bakkiyalakshmi29/Metasploit-for-reconnaissance/assets/119406233/96198803-e84c-4089-9929-865636e7beff)


The info command provides information regarding a module or platform. ![273783305-e8c28c49-2758-4a17-9954-d67eb34f4f0c](https://github.com/Bakkiyalakshmi29/Metasploit-for-reconnaissance/assets/119406233/cfa818fb-59cf-44a9-84b9-362f0e74f1fc)

OUTPUT:

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ![273783459-31502b5b-9ff5-420a-a336-5b359b99f5bd](https://github.com/Bakkiyalakshmi29/Metasploit-for-reconnaissance/assets/119406233/551f9aff-3ae9-4fae-aa6a-d18fd5b7c61b)

MYSQL ENUMERATION:

Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port.

db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
OUTPUT:
![273783857-39be6a58-391d-4ca1-a5fa-a5af0b29a953](https://github.com/Bakkiyalakshmi29/Metasploit-for-reconnaissance/assets/119406233/f7c153b5-24a4-4d27-bb3d-34ff04845d01)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql 

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version ![273783999-e3adae25-a5cb-4ee1-b44b-cd1320f37d5d](https://github.com/Bakkiyalakshmi29/Metasploit-for-reconnaissance/assets/119406233/5f083dec-2633-4bc6-bf0b-11348372468e)


Use the set rhosts command to set the parameter and run the module, as follows:  ![273784257-0d3354a4-6104-43a8-865a-b0fd519325dd](https://github.com/Bakkiyalakshmi29/Metasploit-for-reconnaissance/assets/119406233/7ee58f3a-8043-4bca-8703-dc2bc518b7d2)



After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module. ![273784475-ec2fd0ef-e4f3-45e3-a85f-677c436a9ce3](https://github.com/Bakkiyalakshmi29/Metasploit-for-reconnaissance/assets/119406233/fa9d3b6a-0d46-450d-9f5f-84d246a02734)


set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![273784660-00495dde-12aa-4df1-9a21-1dc5a6fcb270](https://github.com/Bakkiyalakshmi29/Metasploit-for-reconnaissance/assets/119406233/56520ca7-f657-4dac-9ce0-71fe541f765e)


![273784781-08d83442-e2cd-41a9-a03a-d1edb24b5553](https://github.com/Bakkiyalakshmi29/Metasploit-for-reconnaissance/assets/119406233/6cff6d28-cd14-4318-8103-8aabcd658103)

RESULT:
The Metasploit framework for reconnaissance is examined successfully





## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
