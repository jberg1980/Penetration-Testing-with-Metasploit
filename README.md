## Penetration-Testing-with-Metasploit 

### STEP 1: Installation 
1.1 Before installing Metasploit the anti-virus, firewall and intrusion detection/prevention systems settings must be turned off. I installed Metasploit on my Windows machine

### STEP 2: Setting Up Target Virtual Machines
2.1 To set up home lab I have downloaded these:

- VirtualBox 
-	Metasploitable 2
-	Windows 10
-	Kali Download 

### STEP 3: Run Basic Commands
3.1 Running Metasploit msfconsole on my Kali Linux VM.
3.2 Run the help command.
3.3 Run the search command. The search windows command will only display exploits which affect Windows. The search -h command list all other options.
3.4 Run the info command allows me to retrieve detailed information about a specific module. Here I ran the info 0 command to interact with a module by index

### STEP 4: Exploits and Payloads
4.1 Selecting and Using Exploits: How to search for and select specific exploits, such as the "doublepulsar" exploit for SMB vulnerabilities, using commands like use, check, run, and exploit.
4.2 Payloads: Once an exploit is selected, a payload is automatically attached. Payloads are specific commands executed after successfully exploiting a target. You can change the payload to suit your needs.
4.3 Configuration and Execution: Before launching an exploit, you need to configure various options, such as setting the target's IP address (RHOST) and your system's IP address (LHOST). The show options command helps you see these configurations.

### STEP 5: Metasploit Database Basics
5.1 Database Support: Metasploit supports the PostgreSQL database by default, which comes with a default configuration.
5.2 Service Status and Initialization: You can check the status of PostgreSQL and the Metasploit database (MSF DB) using commands like systemctl and msfdb status. If needed, you can reinitialize the database with msfdb reinit.
5.3 Database Commands: Here will cover essential commands such as db_status, db_connect, and db_disconnect to manage the database within the Metasploit framework.

### STEP 6: Information Gathering Using Metasploit
6.1 Passive Information Gathering: How to use Metasploit for passive information gathering, including commands like ping, traceroute, dig, and nslookup.
6.2 Using msfconsole: I can perform these information gathering activities directly from the Metasploit console (msfconsole), similar to how you would use a normal command prompt or terminal.
6.3 Importing Scans: I can import already run Nmap scans into Metasploit using the db_import command, which accepts input in XML format.
6.4 Direct Scanning: The db_nmap command allows me to run Nmap scans directly within Metasploit, automatically importing the results into the Metasploit database.
6.5 Verification: Use the hosts command to verify that the scan results have been successfully imported into the Metasploit database.
6.6Auxiliary Scanners: Metasploit provides specific auxiliary scanners for information gathering, which can be used in addition to Nmap.
6.7 Validation and Scenarios: These scanners are useful for validating results and in scenarios where Nmap cannot be used, such as during pivoting exploits.
6.8 Auxiliary Scanners: Metasploit includes auxiliary scanners for various protocols like TCP, UDP, and ARP. These scanners can be used to run specific scans against a target.
6.9 TCP Scans: How to run a TCP scan using the auxiliary scanner and compares the results with an Nmap scan, showing similar findings.

### STEP 7: Vulnerability Assessment using Metasploit 
7.1	WMAP Overview: WMAP is a vulnerability assessment tool built around sqlmap, primarily used for SQL injections.
7.2	Commands and Usage: Key commands load Wmap, Wmap sites -a, Wmap sites -l, Wmap targets -t, Wmap run -T, and Wmap run -E for executing scans.
7.3	Identifying Vulnerabilities: The video I will demonstrates how to use WMAP to identify various vulnerabilities in a target website, including SQL injection vulnerabilities and directory enumerations.
7.4 Integration with Nessus: Metasploit can import scan results from Nessus, a third-party vulnerability scanner, using the db_import command.
7.5 File Format: Nessus scan results should be exported in the Nessus file type (XML version 2 compliant) to be compatible with Metasploit.
7.6 Verification: After importing, use the hosts command to verify the import and list the vulnerabilities added to the Metasploit database.

### STEP 8: Target Exploitation Using Metasploit
8.1	Basic Commands: In this step I will cover the essential Metasploit commands like search, use, run, and info used for exploitation.
8.2	Nmap Scan: It demonstrates running a basic nmap scan against a target without additional flags or qualifiers.
8.3	FTP Brute Force Attack: The process involves searching for FTP modules, configuring parameters, and using word lists for usernames and passwords to find successful logins.
8.4	Identifying Exploit Modules: I will demonstrate how to identify and use an exploit module for vsftpd, which includes configuring necessary payloads.
8.5	Running the Exploit: Finally, I will run the exploit and confirms successful exploitation by opening a command shell session with the target machine.
8.6	Session Management: How to manage sessions, including backgrounding and listing active sessions.
8.7	Searching for Modules: It shows how to search for and select an appropriate SSH brute force module.
8.8	Configuring and Running the Exploit: The configuration of necessary options like R-host, port, username, and password, and demonstrates running the exploit to gain access to the target system.

### The correct sequence of commands:
|Run Scanners     |nmap  against a target without additional flags or qualifiers|
|Identify Exploit |search for specific open services by ports, use by selecting index number of the exploit|
|Select Payload   |show options to view configuration, set to configure options like R-host, port, username, and password|
|Run Exploit      |run / exploit to gain access to the target system|

