# networkwalks-B082-WEEK4-PENETRATION-TESTING-REPORT
penetration testing report under written permission from mediroza hospital through networkwalks




Penetration Testing Report

Mediroza General Hospital
Target: https://medirozahospital.com
Engagement Type: Black-box Penetration Test
Batch: B082 | Week 4
NAME	NICHOLAS KIPTOO	
WEEK TASK	4	
ORGANIZATION	NETWORKWALKS 	
CLASSIFICATION	CONFIDENTIAL	


Networkwalks internship for cybersecurity and ethical hacking




THIS REPORT CONTAIN CONFIDENTIAL INFORMATION FROM MEDIROZA HOSPITAL. CONDUCTED UNDER WRITTEN PERMISSION FROM MEDIROZA THROUGH NETWORKWALKS. DO NOT USE THE KNOWLEDGE TO GAIN UNATHORISED ACCESS TO OTHER SYSTEM WITHOUT WRITTEN PERMISSION .  Cybercrimes Act, 2018 (Cap. 79C). It was amended in 2025-(kenya)




1.Executive Summary
A penetration test was conducted to identify security weaknesses in a controlled computer environment. The assessment involved reconnaissance, network scanning, service enumeration, vulnerability identification, and controlled validation of selected findings. The objective was to determine whether an attacker could identify and exploit weaknesses and to provide recommendations for improving the security of the tested environment.
Overall Risk Rating: Medium


2. SCOPE OF THE ASSESSMENT
The following systems were included in the assessment:
Item	Details
Target	medirozahospital.com
Target IP	199.188.201.16
Testing environment	Authorized laboratory
Tester	nicholas kiptoo  C|EH
Date	6-9-2026
Tools	Nmap, WhatWeb, HYDRA, Burp Suite, Wireshark,xhydra
Methodology	Reconnaissance → Scanning → Enumeration → Vulnerability Assessment → Validation → Reporting


3.OBJECTIVES
The objectives were to:
-Identify active ports and exposed services.
-Determine open ports and running services.
-Identify potential vulnerabilities.
-Assess the security configuration of the target.
-Validate selected vulnérabilités safely.
-Recommend appropriate remediation measures.



4.SCOPE AND METHODOLOGY
 The first thing in penetration testing and ethical hacking is footprinting and reconnaissance. Several tools are used here to get more details that will help for next step. It so crucial that when one thing misses it will be difficult to succeed. i run whatweb in terminal to get ip address
After get ip address, run nmap to look for open ports and service it runs
Do brute force attack using hydra. Since some useful port like ftp is open. But will be limited if firewall is in placed
Use xhydra
Children  were disabled because it has firewall. We have to try another way to get in. The patient portal login at /patient/login.php was first tested for SQL injection on the username/password fields; this 
did not succeed. The login form was then tested using Burp Suite Intruder against the username admin, cycling through 
a common password wordlist

5.RISK RATINGS AND FINDINGS
(for mediroza and other website of the same)
1.Weak passwords and authentication – no MFA, predictable passwords, or poor login protections. 
2.SQL injection vulnerabilities – user input is inserted into database queries without proper parameterization. 
3.Cross-Site Scripting (XSS) – the site accepts and displays untrusted input without proper output encoding. 
4.Broken access control – users can access another user's information or functions they shouldn't have access to. 
5.Outdated software – old CMS, plugins, libraries, or server software with known vulnerabilities. 
6.Insecure file uploads – allowing dangerous or unexpected files to be uploaded without proper validation. 
7.Poor session management – insecure cookies, long-lived sessions, or failure to invalidate sessions after logout. 
8.Exposed sensitive information – passwords, API keys, database credentials, or configuration files accidentally accessible. 
9.Security misconfiguration – unnecessary services, default credentials, directory listing, verbose error messages, etc. 
10.Missing HTTPS or poor TLS configuration – allowing sensitive information to travel insecurely. 
11.Lack of rate limiting – login and other sensitive endpoints can be repeatedly attempted without adequate controls. 
12.Insecure APIs – APIs that don't properly authenticate requests or enforce authorization. 
13.Poor input validation – accepting unexpected or malicious input. 
14.No logging/monitoring – attacks can occur without being detected. 
For a penetration-testing report
 classify findings :
Weakness	Typical risk
SQL Injection	Critical/High
Broken Access Control	High
Weak Authentication	High
Unrestricted File Upload	High
Stored XSS	High
Outdated Components	Medium–High
Missing Security Headers	Low–Medium
Directory Listing	Low–Medium
Verbose Error Messages	Low


6.RECOMMENDATION  AND REMEDIATION:
No.	weakness Identified	Risk Level	Recommendation

1	Weak passwords	High	Enforce strong passwords and enable multi-factor authentication (MFA).

2	SQL Injection	Critical	Use parameterized queries/prepared statements and validate user input.

3	Cross-Site Scripting (XSS)	High	Validate input and properly encode output before displaying user-supplied data.

4	Broken access control	High	Implement server-side authorization checks for every protected resource.

5	Outdated software/components	High	Regularly update the operating system, web server, CMS, plugins, and libraries.

6	Unrestricted file uploads	High	Restrict file types, validate uploaded files, rename files, and store them safely.

7	Poor session management	High	Use secure cookies, session expiration, and invalidate sessions after logout.

8	Exposed sensitive information	High	Remove credentials, API keys, and sensitive configuration files from public access.

9	Security misconfiguration	Medium	Disable unnecessary services, remove default accounts, and apply secure configurations.

10	Missing HTTPS	High	Implement HTTPS using a valid TLS certificate and redirect HTTP traffic to HTTPS.


11	No rate limiting	Medium	Implement rate limits and account lockout/progressive delays for sensitive operations.

12	Insecure APIs	High	Require authentication and authorization and validate all API requests.

13	Poor input validation	Medium	Validate and sanitize input on the server side using allowlists where appropriate.

14	Verbose error messages	Low	Display generic errors to users while recording detailed errors securely in server logs.

15	Lack of monitoring	Medium	Implement logging, alerting, and regular security monitoring to detect suspicious activity.

16	Poor pdf password	low	Use more complex password


