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
To determine the configured DNS server responsible for resolving domain names.

Finding:
The system was using a private IP address (192.x.x.x), indicating the router is acting as a DNS forwarder.



Step 2: Perform DNS Query

Command used:

nslookup google.com

Purpose:
To manually query the DNS server and observe name resolution behavior.

Observation:

	•	The DNS server responded with public IP addresses for google.com.
	•	Resolution occurred successfully with no timeout or failure.



Step 3: Analyze Local DNS Cache

Command used:

ipconfig /displaydns

Purpose:
To review locally cached DNS records stored on the machine.

Observation:

	•	Multiple A records and CNAME entries were cached.
	•	Time-To-Live (TTL) values were visible.
	•	Both positive and previously resolved entries remained stored temporarily.


Key Findings

	1.  The system relies on a local router as a DNS intermediary.
	2.	DNS queries are cached locally to improve performance.
	3.	Cached entries remain until TTL expires.
	4.	DNS resolution happens before HTTP traffic begins.
	5.	DNS entries can reveal browsing behavior patterns.

Security Insight

	•	DNS cache can be targeted in DNS spoofing attacks.
	•	Flushing DNS cache (ipconfig /flushdns) can remove potentially malicious entries.
	•	Monitoring DNS activity helps detect suspicious traffic.

Security Risks Identified

*     DNS Cache Poisoning: If an attacker manipulates cached entries, traffic could be redirected to malicious servers.
*     Rogue DNS Server Risk: If the router DNS is compromised, all connected devices may resolve malicious IPs.
*     Information Disclosure: Local DNS cache reveals browsing history patterns. 

Mitigation Strategies

	•	Use secure DNS providers (e.g., encrypted DNS)
	*   Flush DNS cache regularly:
	                                 ipconfig /flushdns
	*   Secure router administrative access
	•	Monitor DNS anomalies using traffic analysis tools
	•	Implement DNSSEC where applicable								 


What I Learned

	•	DNS resolution is the first step in web communication.
	•	Local DNS caching improves speed but introduces risk.
	•	TTL values determine how long entries remain cached.
	•	Monitoring DNS activity is critical in SOC operations.

Relevance to SOC Analyst Role

Understanding DNS behavior is essential for:

	•	Detecting command-and-control (C2) communication
	•	Identifying suspicious domains
	•	Investigating phishing incidents
	•	Monitoring abnormal traffic patterns	

	
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










