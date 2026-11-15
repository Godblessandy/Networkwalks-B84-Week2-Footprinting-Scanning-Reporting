Networkwalks-B84-Week2-Footprinting & Scanning
I have completed my penetration testing process focusing on two important area: footprinting and scanning
One module covers the footprinting phase and the other covers the scanning phase. Footprinting involves the process of gathering publicly available information about a target domain, networkwalks.com, using specialized tools within Kali Linux. This phase demonstrates how kali linux (attacker) begins by mapping the digital footprint of an organization before attempting deeper intrusion.
Using kali linux all commands were run (footprinting) and on a Windows PC Zenmap was installed for scanning.
These two steps highlight how an attacker can move from gathering information about a system to actively mapping devices on a network. All the steps below include the exact command used, the results, screenshots as evidence, and a short note on why the finding matters from an attacker’s point of view.
Tools Used
The table below lists each tool used in this report and its purpose:
Kali Linux & Windows	Operating systems used for reconnaissance activities
WHOIS	Find domain registration details (owner, dates, name servers). 
whatweb	Identifies technologies running on a web server, including CMS platforms, plugins, and IP details.
nslookup	Resolve the domain name to its IP address using DNS.
curl -I	Read HTTP response headers of the website. 
wafw00f	Detect whether a Web Application Firewall protects the site.
dnsrecon	Enumerate all DNS records (NS, MX, SPF, TXT, SRV).
Zenmap (Nmap GUI)	Scan the local subnet to find live hosts, IPs and MAC addresses.
Windows CMD	Used to check local IP and MAC address details on the host machine.
Footprinting & Reconnaissance:
I performed reconnaissance against the networkwalks.com domain using six Kali Linux tools: WHOIS, WhatWeb, Nslookup, Curl, Wafw00f, and DNSRecon. Each tool was applied to gather a specific type of information about the target.
I started by using WHOIS to obtain publicly available domain registration details, including ownership information and the domain’s name servers. The results provided insight into the registration and hosting infrastructure.
I then used WhatWeb to identify technologies running on the website. The scan revealed WordPress version 7.1.4 and WP Download Manager 3.3.76, along with other components exposed by the website.
Making use of Nslookup, domain name was resolved to its IP address. The result showed the IP address: 192.232.216.135.
I used Curl with the option -I to inspect the HTTP response headers. This provided additional details about the web application, including the exposed WordPress REST API endpoint /wp-json/.
Next, I used Wafw00f to determine whether a Web Application Firewall was protecting the website. The result identified ModSecurity (SpiderLabs).
Lastly, I used DNSRecon to enumerate DNS records. The results provided information relating to name servers, mail servers, SPF/TXT records, service records, and DNS software information.
Network Scanning with Zenmap:
For the second task, I used Zenmap to perform network discovery on my local network. The aim of the practice was to identify my local IP address and subnet, identify active or live hosts, identify their IP and MAC addresses, and generate basic network topology.
I began by running the ipconfig command in Windows to confirm my local IP address and the LAN. I then entered the subnet into Zenmap and selected the Ping Scan to identify the devices that were online.
The example results provided in the practical identified example results, showing six live hosts within the subnet.
The process revealed attackers moving from identifying a network range to mapping out which devices are live, creating the scenario for enumeration with corresponding MAC addresses revealed.
After completing the scan, I opened the Topology section of the Zenmap, enabled the legend and saved the topology in PNG format as required by the practical task. 
 These practical tasks involved information gathering and host discovery. No vulnerability validation or exploitation was performed as part of these two modules.
Therefore, the presence of information such as software version, Ip addresses or DNS record do not bt themselves mean that the system is vulnerable. So, to determine whether any actual vulnerabilities exist, further authorized security testing and validation would be recommended.
Recommendations:
1.	Review and Assess Publicly Exposed Technology Details: Regularly evaluate what information about web technologies, CMS platforms, and plugins is visible externally to reduce unnecessary exposure.
2.	Update Software: Ensure CMS platforms, plugins, and supporting technologies are regularly updated and checked against current security advisories.
3.	Review HTTP Response Headers: Review and adjust HTTP headers to minimize disclosure of technical details that could aid attackers in reconnaissance.
4.	Review DNS Records Regularly: Conduct routine checks of DNS records to confirm that only essential information and services are publicly accessible.
5.	Configure and Monitor WAF Optimisation: Keep the Web Application Firewall (ModSecurity) enabled, properly configured, and continuously monitored to strengthen protection against naive attacks.
6.	Conduct Internal Network Discovery: Perform periodic scheduled scans of internal networks to identify active devices and maintain visibility of the environment.
7.	Investigate Unrecognized Devices: Any unexpected or unauthorized device discovered during scanning should be promptly investigated and verified.
8.	Maintain Accurate Network Documentation: Ensure documentation of network topology diagrams and device inventories to support effective monitoring and incident response.
9.	Ensure to Perform Authorized Security Testing: Reconnaissance and scanning activities must only be performed on systems and networks where explicit authorization has been given.
10.	Lesson learned:
11.	During these exercises, I learned that information gathering is an important part of cybersecurity. Before an attempt is made to exploit a system, a security professional can learn a significant amount about an environment by carefully analysing publicly available information and network responses
12.	I also learned that technical findings should be documented clearly. A good cybersecurity report should explain what was performed, what was discovered, what the observation means, what risk it may pose, and what can be done to reduce that risk.
Finally, I learned that reconnaissance and scanning must always be performed within an authorised scope. These activities were completed as part of the assigned educational cybersecurity lab.

Liability Disclaimer
I have demonstrated a couple of security testing activities only on systems and devices that I personally own or for which I have obtained explicit, written authorization. All the performances, notes, and materials provided here are intended only for educational and research purposes.
Nothing in this project must not be used to engage in an unlawful activity. The authors, instructors, and NETWORKWALKS will not accept any responsibility for any misuse of this information. Every action you take is your own responsibility.
In most countries, like the UK, Unauthorized access is a crime and can result in prosecution, severe financial penalties, termination of employment, and a permanent record. By engaging with this material, you acknowledge these risks and agree to act responsibly, ethically, and within the confines of the law.
