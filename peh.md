**Information Gathering(Recon)**:  
active/passive, physical, social engineering  
Identify the target: hackerone/bugcrowd  
Discovering email addresses: phonebook.cz and others  
Gather breached creds - dehashed - paid  
Hunting Subdomains: sublist3r -d soda.com -t 100 -v , crt.h, owasp amass  
Identify website technologies: wappalyzer, builtwith, whatweb https://soda.com  
Google advanced search - site:soda.com -www filetype:pdf  //search except www.soda.com subdomain  
Social media: linkedin, twitter  

**Scanning and Enumeration**:  
netdiscover -r 10.1.1.1/24  -- host discovery - arp scan  
nmap -sS -p- -vv 10.1.1.1 -Pn     //-sU for udp  
Enumerating HTTP/s - nikto -H http://soda.com , gobuster dir -u https://soda.com -w /wordlist.txt -x php  
wordlist: /usr/share/wordlists/dirbuster/2.3smalllist  
SMB enum - enum4linux 10.1.1.1, smbclient -L \\10.1.1.1 , smbclient \10.1.1.1\test nmap smb scripts  
Reasearch potential exploits - modssl 2.8.4 bufferoverflow - use github  
Nessus - run nessus all ports  

**Exploitation Basics**:  
Reverse shell - victim-->attacker  
Bind shell -- attacker-->victim  
https://www.revshell.com  
Staged vs Non-staged: windows/meterpreter_reverse_tcp(non-staged), windows/meterpreter/reverse_tcp(staged), add_user(singles)  
searchsploit samba 2.2  //exploit using msf// try both staged and non-staged  
Manual exploitation  //github exploits  
Brute-force attacks: Hydra –l root –P /usr/share/wordlists/metasploit/unix_passwords.txt ssh://192.1.1.1:22 –t 4 –V  
Credential stuffing: any leaked creds, user:pass use hydra, or spray 1-2 pass on multi users with  

**Capstone machines**: blue, academy, Dev, butler, blackpearl  


