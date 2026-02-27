Project Title: DNS Resolution & Cache Analysis (Windows Lab)



Objective:  To understand how DNS resolution works on Windows systems and analyze how DNS records are stored locally in the DNS resolver cache.




Lab Environment



	•	Operating System: Windows 10 / Windows 11
	•	Tools Used:
	•	ipconfig /all
	•	nslookup
	•	ipconfig /displaydns
	•	Command Prompt (CMD)



Methodology (Step-by-Step Process)

Step 1: Identify DNS Server Configuration

Command used:

ipconfig /all

Purpose:
To identify the configured DNS server and network adapter details.

Observation:

	•	DNS Server IP: (Insert your DNS server IP here)
	•	Connection Type: (Wi-Fi / Ethernet)



Step 2: Perform DNS Query

Command used:

nslookup google.com

Purpose:
To query the DNS server and resolve the domain name into an IP address.

Observation:

	•	Resolved IP Address:
	•	DNS Server Used:



Step 3: Analyze Local DNS Cache

Command used:

ipconfig /displaydns

Purpose:
To view cached DNS records stored on the local machine.

Observation:

	•	Record Name
	•	Record Type (A, AAAA, CNAME)
	•	Time To Live (TTL)



Step 4: Findings

	•	The system queries the configured DNS server to resolve domain names.
	•	Successfully resolved google.com to its IP address.
	•	DNS responses were stored in the local cache.
	•	TTL determines how long records remain cached.
	•	Cached records reduce future DNS query time.



Setep 5: Security Insight

	•	DNS cache can be targeted in DNS spoofing attacks.
	•	Flushing DNS cache (ipconfig /flushdns) can remove potentially malicious entries.
	•	Monitoring DNS activity helps detect suspicious traffic.



Conclusion

This lab demonstrates the DNS resolution process on Windows systems and highlights the importance of DNS caching in performance and security.



Bonus: Clearing DNS Cache

Command:

ipconfig /flushdns

Purpose:
Clears local DNS cache to remove outdated or malicious records.





Author

Adetoye-Elemoro E.A.
Aspiring Network & Cybersecurity Professional
Nigeria










