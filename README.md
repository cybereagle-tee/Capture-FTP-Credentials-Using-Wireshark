Capture-FTP-Credentials-Using-Wireshark
--

**Project Overview:**  This lab demonstrates how insecure protocols like FTP expose sensitive credentials over the network. Using Wireshark, I captured and analyzed FTP traffic to extract login credentials in plaintext within a controlled virtual lab.

---

Objective
--
Capture FTP login credentials using Wireshark
Analyze network traffic to identify security weaknesses
Understand why FTP is considered insecure

---

Lab Environment
--
Component	Details
Attacker Machine	Kali Linux (VirtualBox)
Target Machine	Metasploitable 2
Network Type	Host-Only Adapter
Tools Used	Wireshark, Nmap, FTP

---

Lab Setup
--
1. Network Configuration
   
Both Kali Linux and Metasploitable 2 were configured with:

Adapter 1 set to Host-Only Adapter

This allows isolated communication between both machines.



2. Start Target Machine
   
Logged into Metasploitable 2 using default credentials
Identified the target IP address using system network configuration tools

Example IP:
192.168.56.101



3. Verify Connectivity
   
Confirmed communication between Kali Linux and the target machine using network testing
Successful response indicated both systems were connected properly

---

Step-by-Step Execution
--
Step 1: Scan for FTP Service

Performed a port scan on the target machine
Verified that FTP service (Port 21) was open and accessible



Step 2: Start Wireshark Capture

Launched Wireshark on Kali Linux
Selected the active network interface
Started packet capture



Step 3: Generate FTP Traffic

Initiated an FTP connection from Kali Linux to the target machine
Logged in using default credentials

This action generated network traffic for analysis



Step 4: Filter FTP Traffic

Applied a display filter in Wireshark to isolate FTP traffic



Step 5: Extract Credentials

Method 1: Packet Inspection
Selected FTP packets from the capture
Inspected the packet details under the File Transfer Protocol section
Observed username and password transmitted in clear text
Method 2: Follow TCP Stream (Recommended)
Followed the TCP stream of the FTP session
Clearly observed login credentials in plaintext



Results
--
Data Type	Value
Username	msfadmin
Password	msfadmin
Protocol	FTP

✅ Credentials were successfully captured in plaintext

---

Security Analysis
--
FTP does not encrypt transmitted data
Login credentials are exposed in plain text
Attackers can easily intercept sensitive information using packet sniffing tools

---

Key Takeaways
--
Insecure protocols pose significant security risks
Network traffic analysis is a critical cybersecurity skill
Even simple attacks can expose sensitive data if proper security measures are not in place

---

Recommendations
--
Replace FTP with secure alternatives like SFTP or FTPS
Ensure all authentication traffic is encrypted
Monitor network traffic for suspicious activity
Perform regular security assessments

---

Screenshots
--

Include screenshots such as:

Wireshark capture interface
FTP login attempt
TCP stream showing captured credentials

---

Project Value
--
This project demonstrates:

1. Practical use of Wireshark
2. Understanding of insecure network protocols
3. Hands-on penetration testing skills

   ---

   Author
   --
Treasure James
(The Cybereagle)

Understanding of insecure network protocols
Hands-on penetration testing skills
