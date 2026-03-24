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

