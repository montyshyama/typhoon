# Step-by-step walk-through of Typhoon 1.02: A Vulnhub VM

# Reconnaissance
1. Running initial nmap scan to discover open ports
2. Running targeted nmap scan for all open ports and with defaults scripts
3. Discovering that anonymous FTP login is enabled
4. A web server is also running on port 80
# Active Enumeration
5. Running nikto to discover hidden directories
6. Interesting findings include one disallowed entry in robots.txt (/mongoadmin), and some directories like /cms, /phpmyadmin
7. The link http://192.168.43.30/cms is running LotusCMS
8. Finding public exploits for LotusCMS with searchsploit
9. A metasploit module is also available
# Exploitation
10. Configuring the exploit (set rhost to 192.168.43.30 & uri to /cms/)
11. Gaining initial shell on the system
# Privilege Escalation
12. Transferring  Local Linux Enumeration & Privilege Escalation Checks script via Python server
13. Discovering that Linux kernel version is a bit old, driving an inclination to look for kernel exploits
14. All cronjobs looks normal
15. Finding kernel exploit for that specific kernel version using searchsploit
16. Transferring the priv-esc exploit to the target system via Python server
17. Compiling and running the exploit, & root shell is gained
