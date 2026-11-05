# Experiment 7: OSINT Reconnaissance Using Google Dorking and Shodan

## 1. Objective

To perform **Open-Source Intelligence (OSINT) reconnaissance** using Google advanced search operators and **Shodan** to discover publicly available information, identify exposed services, and understand the information that can be gathered about internet-connected systems.

## 2. Procedure

### Step 1: Perform Domain-Based Reconnaissance Using Google

Open Google and use the search operator `site:gov.in` to restrict search results to websites under the `.gov.in` domain. Examine the results to understand how domain-based filtering helps identify publicly accessible information associated with a particular domain.

![Step 1 Screenshot](images/ss1.png)

### Step 2: Search for Potentially Exposed Directories

Enter the query `intitle:"index of"` into Google. Review the results to understand how search operators can identify pages that may display directory listings and reveal publicly accessible files or directories.

![Step 2 Screenshot](images/ss2.png)

### Step 3: Find Cybersecurity-Related PDF Documents

Use the Google search query `inurl: cybersecurity filetype:pdf` to locate PDF documents associated with cybersecurity-related URLs. Examine the results to understand how multiple search operators can be combined to narrow down publicly available information.

![Step 3 Screenshot](images/ss3.png)

### Step 4: Search for Login-Related Pages

Enter the query `inurl: login` in Google. Examine the results to identify web pages whose URLs contain the word `login`. This demonstrates how search operators can help discover login-related pages during reconnaissance.

![Step 4 Screenshot](images/ss4.png)

### Step 5: Examine Google's Cache Search Operator

Enter the query `cache:google.com` into Google and observe the information returned. The search result indicates that Google's public Cache feature has been discontinued. This step demonstrates the importance of understanding the availability and limitations of search operators used during reconnaissance.

![Step 5 Screenshot](images/ss5.png)

### Step 6: Identify Internet-Facing Services Using Shodan

Open Shodan and search for `apache`. Examine the results to identify internet-connected hosts reporting Apache web-server services. Observe displayed information such as IP addresses, server banners, HTTP response details, and service information.

![Step 6 Screenshot](images/ss6.png)

### Step 7: Search for Services on a Specific Port in India

In Shodan, enter the query `port:23 country:"IN"` to filter results for hosts in India associated with port 23, commonly used by Telnet. Review the results to understand how Shodan filters internet-connected systems by port and country.

![Step 7 Screenshot](images/ss7.png)

### Step 8: Perform Hostname-Based Reconnaissance

Enter the query `hostname:gov.in` in Shodan to search for hosts whose hostname matches the specified government-domain filter. Examine the results and observe available information about matching hosts, including detected services and network details.

![Step 8 Screenshot](images/ss8.png)

## 3. Result

The experiment demonstrated **OSINT reconnaissance using Google advanced search operators and Shodan**. Google Dorking was used to filter publicly indexed information, including government-domain pages, directory listings, PDF documents, and login-related pages. Shodan was used to examine internet-facing services and filter hosts by service port, country, and hostname. The experiment highlighted how publicly available information can support security reconnaissance and why exposed services and directory listings should be reviewed and secured appropriately.
