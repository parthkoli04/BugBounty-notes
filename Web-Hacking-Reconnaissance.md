# Manually Walking through the target
- Before starting any automated scanning or testing, it's important to manually explore the target application. This allows you to understand the application's functionality, identify potential attack surfaces, and gather information that can be useful for later stages of testing.
- Start by navigating through the application as a regular user would. Pay attention to the different pages, forms, and features available. Take note of any input fields, parameters, and functionalities that could potentially be exploited.
- Look for any hidden or less obvious features that may not be immediately visible. This could include admin panels, API endpoints, or other functionalities that may have weaker security controls.
- Take note of any error messages or unusual behavior that may indicate potential vulnerabilities.
- Document your findings and observations as you go through the application. This information can be valuable for later stages of testing and for writing your report.  

# Google Dorking
- Google Dorking, also known as Google Hacking, is a technique used to find sensitive information or vulnerabilities in a target application by using advanced search operators in Google. This can help you discover hidden pages, exposed files, or other information that may not be easily accessible through normal browsing.
- Some common Google Dorking operators include:
    - `site:` - Restricts search results to a specific domain or website. For example, `site:example.com` will return results only from the example.com domain.
    - `filetype:` - Searches for specific file types. For example, `filetype:pdf` will return PDF files.
    - `inurl:` - Searches for specific keywords in the URL. For example, `inurl:admin` will return URLs that contain the word "admin".
    - `intitle:` - Searches for specific keywords in the title of web pages. For example, `intitle:"index of"` will return pages with "index of" in the title, which may indicate directory listings.
    - `intext:` - Searches for specific keywords in the body of web pages. For example, `intext:"password"` will return pages that contain the word "password" in their content.
- By using these operators in combination, you can create powerful search queries to find specific information about the target application. For example, `site:example.com filetype:pdf` will return all PDF files from the example.com domain, which may include sensitive documents or reports.
- Google Dorking can be a valuable tool for reconnaissance and can help you identify potential vulnerabilities or sensitive information that may be exposed on the target application. However, it's important to use this technique responsibly and ethically, and to respect the privacy and security of the target application. Always ensure that you have permission to perform reconnaissance on the target application and that you are not violating any laws or regulations in the process.
- Wildcards can also be used in Google Dorking to broaden your search. For example, `site:example.com inurl:admin*` will return URLs that contain "admin" followed by any characters, which may help you find various admin-related pages or endpoints on the target application.
- Quotes can be used to search for exact phrases. For example, `intitle:"login page"` will return pages with the exact phrase "login page" in the title, which may help you find login pages on the target application.
- It's important to note that while Google Dorking can be a powerful tool for reconnaissance, it can also be used by attackers to find vulnerabilities or sensitive information. Therefore, it's crucial to regularly monitor your own applications for any exposed information and to implement proper security measures to protect against unauthorized access.
- OR (|) operator can be used to search for multiple keywords or phrases. For example, `site:example.com inurl:admin | inurl:dashboard` will return URLs that contain either "admin" or "dashboard", which may help you find various administrative pages on the target application.
- The minus (-) operator can be used to exclude certain keywords or phrases from your search results. For example, `site:example.com inurl:admin -inurl:login` will return URLs that contain "admin" but exclude those that contain "login", which may help you find admin pages that are not login pages.

- While searching look for sensitive information such as:
    - Exposed files (e.g., configuration files, backup files, log files)
    - Hidden pages or directories (e.g., admin panels, staging environments)
    - Vulnerable endpoints (e.g., outdated software versions, known vulnerabilities)
    - User credentials or sensitive data (e.g., usernames, passwords, API keys)
- Document any findings from your Google Dorking searches, including the search queries used and the results obtained. This information can be valuable for later stages of testing and for writing your report.

# Scope Discovery
- During your reconnaissance, it's important to identify the scope of your testing. This includes understanding which parts of the application are in scope for testing and which are out of scope. This can help you focus your efforts on the areas that are most relevant and avoid any potential legal or ethical issues.
- Review the scope provided by the bug bounty program and ensure that you understand which parts of the application are in scope for testing. This may include specific domains, subdomains, or endpoints that are allowed for testing.
- Identify any areas of the application that are out of scope for testing, such as third-party services, APIs, or other components that are not owned or controlled by the organization. Avoid testing these areas to prevent any potential legal or ethical issues.
- Document the scope of your testing and any areas that are out of scope. This information can be included in your report to provide clarity on the boundaries of your testing and to demonstrate that you have adhered to the rules of the bug bounty program.

# WHOIS and Reverse WHOIS Lookup
- WHOIS is a protocol used to query databases that store information about registered domain names. A WHOIS lookup can provide valuable information about the target domain, such as the registrant's name, contact information, registration date, and expiration date. This information can be useful for reconnaissance and can help you understand more about the target organization and its online presence.
- To perform a WHOIS lookup, you can use various online tools or command-line utilities. Some popular online WHOIS lookup tools include:
    - [Whois Lookup](https://whois.domaintools.com/)
    - [ICANN WHOIS](https://lookup.icann.org/)
    - [Whois.net](https://www.whois.net/)
- When performing a WHOIS lookup, pay attention to the following information:
    - Registrant Name: The name of the individual or organization that registered the domain.
    - Registrant Contact Information: This may include email addresses, phone numbers, and physical addresses associated with the registrant.
    - Registration Date: The date when the domain was registered.
    - Expiration Date: The date when the domain registration is set to expire.
    - Name Servers: The servers that are responsible for handling DNS queries for the domain.
- Reverse WHOIS lookup is a technique used to find all domains that are registered by the same registrant. This can be useful for identifying other domains that may be associated with the target organization, which can help you expand your reconnaissance and identify additional attack surfaces.
- To perform a reverse WHOIS lookup, you can use online tools such as:
    - [DomainTools Reverse WHOIS](https://reversewhois.domaintools.com/)
    - [WhoisXML Reverse WHOIS](https://reverse-whois.whoisxmlapi.com/)
- When performing a reverse WHOIS lookup, you can search for domains based on the registrant's name, email address, or other contact information. This can help you identify other domains that may be associated with the target organization, which can provide additional opportunities for reconnaissance and testing.
- Document any findings from your WHOIS and reverse WHOIS lookups, including the information obtained and any additional domains identified. This information can be valuable for later stages of testing and for writing your report.

IP Address:
- An IP address is a unique identifier assigned to each device connected to a network. In the context of web reconnaissance, identifying the IP address of the target application can provide valuable information about the hosting environment, potential vulnerabilities, and other attack surfaces.
- To find the IP address of a target domain, you can use various tools and techniques. One common method is to use the `nslookup` command in the terminal. For example, you can run `nslookup example.com` to retrieve the IP address associated with the domain.
- Another method is to use online tools such as:
    - [DNS Lookup](https://dnslookup.online/)
    - [MXToolbox](https://mxtoolbox.com/DNSLookup.aspx)
- When you perform an IP address lookup, you may find multiple IP addresses associated with the target domain, especially if the application is hosted on a content delivery network (CDN) or uses load balancing. In such cases, it's important to note all the IP addresses associated with the target domain, as they may all be relevant for reconnaissance and testing.
- Document the IP addresses associated with the target domain, as well as any additional information obtained from the lookup, such as the hosting provider or geographic location. This information can be valuable for later stages of testing and for writing your report.   

# Certificate Parsing
- SSL/TLS certificates are used to secure communication between a client and a server. When a website uses HTTPS, it presents an SSL/TLS certificate to the client to establish a secure connection.
- Certificate parsing involves analyzing the SSL/TLS certificate presented by the target application to extract valuable information that can be useful for reconnaissance and testing. This information may include the domain names covered by the certificate, the organization that issued the certificate, and the expiration date of the certificate.
- To parse an SSL/TLS certificate, you can use various tools and techniques. One common method is to use the `openssl` command in the terminal. For example, you can run `openssl s_client -connect example.com:443` to retrieve the certificate information for the target domain.
- Another method is to use online tools such as:
    - [SSL Labs](https://www.ssllabs.com/ssltest/)
    - [Certificate Decoder](https://www.sslshopper.com/certificate-decoder.html)
    - [crt.sh](https://crt.sh/)
    - [Censys](https://censys.io/)
    - [Certspotter](https://certspotter.com/)
- When parsing the certificate, pay attention to the following information:
    - Common Name (CN): The primary domain name covered by the certificate.
    - Subject Alternative Names (SANs): Additional domain names covered by the certificate.
    - Issuer: The organization that issued the certificate.
    - Expiration Date: The date when the certificate is set to expire.
- By analyzing the certificate information, you may be able to identify additional domains associated with the target application, which can provide additional opportunities for reconnaissance and testing. For example, if the certificate includes multiple SANs, you can investigate those additional domains to see if they are part of the target application and if they have any vulnerabilities or sensitive information exposed.
- Document any findings from your certificate parsing, including the information obtained and any additional domains identified. This information can be valuable for later stages of testing and for writing your report.

# Subdomain Enumeration
- Subdomain enumeration is the process of identifying subdomains associated with a target domain. Subdomains can provide additional attack surfaces and may have different security controls or vulnerabilities compared to the main domain. Therefore, identifying subdomains is an important part of reconnaissance and can help you discover additional vulnerabilities or sensitive information that may be exposed on the target application.
- There are various tools and techniques available for subdomain enumeration. Some popular tools include:
    - [Sublist3r](https://github.com/aboul3la/Sublist3r)
    - [Amass](https://github.com/OWASP/Amass)
    - [Gobuster](https://github.com/OJ/gobuster)

- When performing subdomain enumeration, you can use a combination of techniques, such as:
    - DNS brute forcing: This involves using a wordlist of common subdomain names and attempting to resolve them against the target domain to see if they exist.
    - Certificate transparency logs: By analyzing SSL/TLS certificates, you can identify additional subdomains that are covered by the certificate.
    - Search engine queries: Using search engines with specific queries can help you discover subdomains that may be indexed by search engines.
    - Passive reconnaissance: This involves using online services that collect and analyze DNS data to identify subdomains associated with the target domain.
- Document any subdomains identified during your enumeration, as well as any additional information obtained about those subdomains, such as their IP addresses, hosting providers, or any vulnerabilities or sensitive information exposed on those subdomains. This information can be valuable for later stages of testing and for writing your report. 

# Service Enumeration
- Service enumeration is the process of identifying the services and applications running on the target application. This can provide valuable information about the technologies used by the target application, potential vulnerabilities, and attack surfaces that can be exploited during testing.
- To perform service enumeration, you can use various tools and techniques. Some popular tools include:
    - [Nmap](https://nmap.org/)
    - [Masscan](https://github.com/robertdavidgraham/masscan)
    - [Nikto](https://github.com/sullo/nikto)
    - [WhatWeb](https://github.com/urbanadventurer/WhatWeb)
- When performing service enumeration, you can use a combination of techniques, such as:
    - Port scanning: This involves scanning the target application for open ports to identify which services are running on those ports.
    - Banner grabbing: This involves connecting to the open ports and retrieving information about the services running on those ports, such as the software name and version.
    - Web application fingerprinting: This involves analyzing the responses from the target application to identify the technologies and frameworks used by the application.
    - Vulnerability scanning: This involves using automated tools to scan the target application for known vulnerabilities associated with the identified services and technologies.
- Document any services and applications identified during your enumeration, as well as any additional information obtained about those services, such as their versions, configurations, or any vulnerabilities or sensitive information exposed by those services. This information can be valuable for later stages of testing and for writing your report.

# Directory Brute Forcing
- Directory brute forcing is a technique used to discover hidden directories and files on a web server. This can help you identify additional attack surfaces and potential vulnerabilities that may not be immediately visible through normal browsing.
- To perform directory brute forcing, you can use various tools and techniques. Some popular tools include:
    - [DirBuster](https://github.com/digination/dirbuster)
    - [Gobuster](https://github.com/OJ/gobuster)
    - [Dirsearch](https://github.com/maurosoria/dirsearch)
- When performing directory brute forcing, you can use a wordlist of common directory and file names to attempt to access those directories and files on the target application. The tool will send requests to the target application for each entry in the wordlist and analyze the responses to determine if the directory or file exists.
- Pay attention to the HTTP status codes returned by the target application during directory brute forcing. A status code of 200 may indicate that the directory or file exists, while a status code of 404 may indicate that it does not exist. However, be aware that some applications may return a status code of 200 for all requests, even if the directory or file does not exist, so it's important to analyze the responses carefully.
- Document any directories and files discovered during your brute forcing, as well as any additional information obtained about those directories and files, such as their contents, permissions, or any vulnerabilities or sensitive information exposed by those directories and files. This information can be valuable for later stages of testing and for writing your report.

# Third Party Hosting
- During your reconnaissance, you may come across third-party hosting services that are used by the target application. These services may include content delivery networks (CDNs), cloud hosting providers, or other third-party services that are used to host parts of the application or to provide additional functionality.
- It's important to identify any third-party hosting services used by the target application, as they may have different security controls and vulnerabilities compared to the main application. Additionally, these third-party services may have their own attack surfaces that can be exploited during testing.
- To identify third-party hosting services, you can analyze the HTTP headers returned by the target application. Look for headers such as "Server" or "X-Powered-By" that may indicate the hosting provider or the technologies used by the application. You can use tools such as `curl` or online services to analyze the HTTP headers. For example, you can run `curl -sI https://example.com | grep "Server\|X-Powered-By"` to retrieve the relevant headers.
- Document any third-party hosting services identified during your reconnaissance, as well as any additional information obtained about those services, such as their hosting providers, technologies used, or any vulnerabilities or sensitive information exposed by those services. This information can be valuable for later stages of testing and for writing your report.

# Github Recon
- GitHub is a popular platform for hosting code repositories, and it can be a valuable source of information during reconnaissance. Many organizations use GitHub to host their code, and sometimes sensitive information such as API keys, credentials, or configuration files may be accidentally exposed in public repositories.
- To perform GitHub reconnaissance, you can use the GitHub API or command-line tools to search for repositories associated with the target organization. For example, you can use the `gh` command-line tool to search for repositories owned by the target organization. You can run `gh repo list getyourguide --json name,description,createdAt` to retrieve a list of repositories owned by the "getyourguide" organization, along with their names, descriptions, and creation dates.
- When analyzing GitHub repositories, pay attention to the following information:
    - Repository names and descriptions: This can provide insights into the projects and technologies used by the target organization.
    - Commit history: This can reveal changes made to the codebase, which may include the addition of sensitive information or the introduction of vulnerabilities.
    - Issues and pull requests: This can provide insights into the development process and may reveal discussions about potential vulnerabilities or security issues.
    - Code contents: This can reveal sensitive information such as API keys, credentials, or configuration files that may have been accidentally exposed in the codebase.
- Document any findings from your GitHub reconnaissance, including the repositories identified, any sensitive information discovered, and any vulnerabilities or security issues revealed through the analysis of the repositories. This information can be valuable for later stages of testing and for writing your report. 


