# Name:gajalakshmi.V
# register no:212223040047
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

## EXECUTION STEPS AND ITS OUTPUT:


## OUTPUT:
![Screenshot 2024-04-24 081434](https://github.com/Gajalakshmivelmurugan/Metasploit-for-reconnaissance/assets/144871940/b10ccbe6-2266-4d38-a2ab-2d3f878986e5)

invoke msfconsole

## OUTPUT:

![Screenshot 2024-04-24 081446](https://github.com/Gajalakshmivelmurugan/Metasploit-for-reconnaissance/assets/144871940/3a0621d5-358b-4d20-ae18-28034b0e0e19)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT:

![Screenshot 2024-04-24 081459](https://github.com/Gajalakshmivelmurugan/Metasploit-for-reconnaissance/assets/144871940/3c2450b4-200a-4996-9b4d-afc2f90a8152)


Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:
![Screenshot 2024-04-24 081512](https://github.com/Gajalakshmivelmurugan/Metasploit-for-reconnaissance/assets/144871940/14dca9f5-4ad7-47e7-b7fa-1745b2bfaf9a)

use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
## OUTPUT:
![Screenshot 2024-04-24 081528](https://github.com/Gajalakshmivelmurugan/Metasploit-for-reconnaissance/assets/144871940/514184c7-fbe8-405b-b18b-e0095eb87146)
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l
## OUTPUT:
![Screenshot 2024-04-24 081541](https://github.com/Gajalakshmivelmurugan/Metasploit-for-reconnaissance/assets/144871940/f2f5861c-5435-4ca2-b1ec-467a02968817)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

## OUTPUT:
![Screenshot 2024-04-24 081854](https://github.com/Gajalakshmivelmurugan/Metasploit-for-reconnaissance/assets/144871940/7dc83a84-dd7f-4ec1-b52a-1c7c74596248)
The info command provides information regarding a module or platform.

## OUTPUT:
![Screenshot 2024-04-24 081910](https://github.com/Gajalakshmivelmurugan/Metasploit-for-reconnaissance/assets/144871940/0bfab289-77db-4887-82a7-747072581cd3)
Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

## OUTPUT:
![Screenshot 2024-04-24 081953](https://github.com/Gajalakshmivelmurugan/Metasploit-for-reconnaissance/assets/144871940/472bd026-7c49-4933-b291-b027f375eee3)
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

## OUTPUT:
![Screenshot 2024-04-24 082002](https://github.com/Gajalakshmivelmurugan/Metasploit-for-reconnaissance/assets/144871940/809b4e7f-3000-4997-bb6a-9ab53992563b)
use 11 Or: use auxiliary/scanner/mysql/mysql_version

## OUTPUT:
![Screenshot 2024-04-24 082012](https://github.com/Gajalakshmivelmurugan/Metasploit-for-reconnaissance/assets/144871940/b1717b88-192c-4f10-b60b-918e5821558f)
Use the set rhosts command to set the parameter and run the module, as follows:
## OUTPUT:
![Screenshot 2024-04-24 082026](https://github.com/Gajalakshmivelmurugan/Metasploit-for-reconnaissance/assets/144871940/71bcf2c8-ea62-4ab9-87c4-cc875f8d2dfc)


After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

## OUTPUT:

![Screenshot 2024-04-24 082037](https://github.com/Gajalakshmivelmurugan/Metasploit-for-reconnaissance/assets/144871940/1b14212c-bba4-44ca-97b3-cbf4c52fbaac)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

## OUTPUT:

![Screenshot 2024-04-24 082046](https://github.com/Gajalakshmivelmurugan/Metasploit-for-reconnaissance/assets/144871940/3e504f86-77c7-4453-b135-4cd649dde450)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully

