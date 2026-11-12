# Week2-Cybersecurity-and-ethical-hacking
This week focused on how attackers think before they attack: reconnaissance.

Objectives
•	Footprint the networkwalks.com domain using Kali Linux tools
•	Identify web technologies, DNS records, and firewall protection
•	Scan my local network with Zenmap to find live hosts, IPs, and MAC addresses
•	Generate a network topology
Tools & Environment
•	Kali Linux (virtual machine): WHOIS, WhatWeb, Nslookup, Curl, WAFW00f, DNSRecon
•	Windows PC: Command Prompt (ipconfig) and Zenmap (Nmap GUI)
Setup Steps
1. WHOIS: Domain Registration Details
•	Ran whois networkwalks.com
•	Domain registered with GoDaddy (created 6 Nov 2019, expires 6 Nov 2027)
•	Name servers are HostGator (NS6135/NS6136); DNSSEC is unsigned
•	Owner details are hidden behind a privacy service
[Screenshot: WHOIS]
2. WhatWeb: Web Technologies
•	Ran whatweb networkwalks.com
•	Found Apache, WordPress 7.1.4, WordPress Download Manager 3.3.76, jQuery 3.7.1 and Google Tag Manager
•	Also exposed the server IP 192.232.216.135 and a public email address
[Screenshot: WhatWeb]
3. Nslookup: DNS Resolution
•	Ran nslookup networkwalks.com
•	The domain resolved to Overview
This document covers Week 2 of my cybersecurity and hacking internship, where I practiced reconnaissance: gathering public information about a domain and discovering live hosts on a local network.
Objectives
•	Footprint the networkwalks.com domain using Kali Linux tools
•	Identify web technologies, DNS records, and firewall protection
•	Scan my local network with Zenmap to find live hosts, IPs, and MAC addresses
•	Generate a network topology
Tools & Environment
•	Kali Linux (virtual machine): WHOIS, WhatWeb, Nslookup, Curl, WAFW00f, DNSRecon
•	Windows PC: Command Prompt (ipconfig) and Zenmap (Nmap GUI)
Setup Steps
1. WHOIS: Domain Registration Details
•	Ran whois networkwalks.com
•	Domain registered with GoDaddy (created 6 Nov 2019, expires 6 Nov 2027)
•	Name servers are HostGator (NS6135/NS6136); DNSSEC is unsigned
•	Owner details are hidden behind a privacy service
[Screenshot: WHOIS]
2. WhatWeb: Web Technologies
•	Ran whatweb networkwalks.com
•	Found Apache, WordPress 7.1.4, WordPress Download Manager 3.3.76, jQuery 3.7.1 and Google Tag Manager
•	Also exposed the server IP xxx.xxx.xxx.xx and a public email address
[Screenshot: WhatWeb]
3. Nslookup: DNS Resolution
•	Ran nslookup networkwalks.com
•	The domain resolved to xxx.xxx.xxx.xx
[Screenshot: Nslookup]
4. Curl: HTTP Headers
•	Ran curl -I https://networkwalks.com
•	Response was HTTP/2 200 with WordPress caching headers
•	The REST API endpoint /wp-json/ was exposed in the headers
[Screenshot: Curl]
5. Wafw00f: Firewall Detection
•	Ran wafw00f networkwalks.com
•	The site is protected by a ModSecurity (SpiderLabs) Web Application Firewall
[Screenshot: Wafw00f]
6. DNSRecon: DNS Enumeration
•	Ran dnsrecon -d networkwalks.com
•	Found HostGator name servers running BIND 9.16.23-RH
•	Found the mail server mail.networkwalks.com, SPF and Google verification TXT records, and 8 cPanel autodiscover SRV records
[Screenshot: DNSRecon]
7. Zenmap: Local Network Scan
•	Ran ipconfig in Windows Command Prompt to find the local IP and subnet
•	Ethernet adapter IPv4 is xxx.xxx.xx.x with mask xxx.xxx.xxx.x, so the subnet is xxx.xxx.xx.x/xx
•	Ran a Ping Scan in Zenmap: nmap -sn xxx.xxx.xx.x/xx
•	Found 1 live host: xxx.xxx.xxx.xx
•	Opened the Topology tab, enabled the legend, and saved the topology as a PDF
[Screenshot: Zenmap scan]
[Screenshot: Zenmap topology]
Key Learnings
•	Public information alone (hosting provider, software versions, mail server, firewall) reveals a lot about a target before any attack
•	Seeing a software version or DNS record is not the same as finding a vulnerability
•	A ping scan shows which hosts are alive on a subnet, along with their IP and MAC addresses
•	Findings should be documented clearly, and reconnaissance must stay within an authorized scope
Next Steps
•	Run port and service scans with Nmap
•	Practice vulnerability scanning on a deliberately vulnerable target in the lab
Disclaimer
All activities were performed as part of an assigned educational lab, within an authorized scope. The findings are observations, not confirmed vulnerabilities.
Author
Tapiwanashe Ripondo

