# Explore Google hacking and enumeration 

# AIM:

To use Google for gathering information and perform enumeration of targets

## STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various Google hacking keywords and enumeration tools as follows:


### Step 3:
Open terminal and try execute some kali linux commands

## Pen Test Tools Categories:  

| Operator    | Description                        | Example Usage           |
| ----------- | ---------------------------------- | ----------------------- |
| `site:`     | Search within a specific domain    | `site:example.com`      |
| `inurl:`    | Search in URL                      | `inurl:admin`           |
| `intitle:`  | Search in page title               | `intitle:"index of"`    |
| `filetype:` | Search by file type                | `filetype:pdf`          |
| `intext:`   | Search inside page text            | `intext:"confidential"` |
| `link:`     | Pages that link to a specific site | `link:example.com`      |
| `cache:`    | View cached version of a site      | `cache:example.com`     |
| `ext:`      | Same as filetype                   | `ext:xls`               |

 ## Architecture 
 ```
+----------------------+
|   Attacker / Hacker  |
|   (Browser & Google) |
+----------+-----------+
           |
           | Google Dork Queries
           v
+---------------------------+
|       Google Search       |
+---------------------------+
           |
           | Indexed Public Content
           v
+---------------------------+
|   Target Websites / Data  |
| - Leaked files            |
| - Open directories        |
| - Sensitive info          |
+---------------------------+

```

# Output:
# SITE:
<img width="1887" height="984" alt="Screenshot 2025-09-19 132918" src="https://github.com/user-attachments/assets/55c37d74-d3e6-4a4f-acf3-c99cf5a2bc7d" />

# INURL:
<img width="1802" height="879" alt="Screenshot 2025-09-19 133930" src="https://github.com/user-attachments/assets/a5f6e730-712e-4589-bb95-2386c981a140" />

# INTITLE:
<img width="1903" height="1018" alt="Screenshot 2025-09-19 133958" src="https://github.com/user-attachments/assets/c33a8f9a-29c5-4e24-9102-1708f3a857f9" />

# FILETYPE:
<img width="1874" height="1003" alt="Screenshot 2025-09-19 134127" src="https://github.com/user-attachments/assets/8fe5da48-6116-4bea-8d9b-7995f469339c" />

# INTEXT:
<img width="1919" height="876" alt="image" src="https://github.com/user-attachments/assets/ed2be6fa-5f62-439a-ae09-608813e644ea" />

# LINK:
<img width="1918" height="875" alt="image" src="https://github.com/user-attachments/assets/27b906ee-1b12-4201-80c1-2c49c765f24e" />

# CACHE:
<img width="1919" height="877" alt="image" src="https://github.com/user-attachments/assets/2d925b92-eb81-47d2-88e0-fd537c42bfb0" />

# EXT:
<img width="1919" height="868" alt="image" src="https://github.com/user-attachments/assets/a39995bf-19c1-44e8-8543-11225e82e820" />

# DNS Enumeration
<img width="1919" height="977" alt="Screenshot 2025-09-04 104949" src="https://github.com/user-attachments/assets/a9e9d474-e587-4c7e-b6af-eb5dbf8a9d25" />

## DNS Recon
<img width="1919" height="696" alt="Screenshot 2025-09-04 105116" src="https://github.com/user-attachments/assets/eecaac38-8a30-4602-b053-683defc7ad19" />


| Record Type | Meaning                        | Example Output                   |
| ----------- | ------------------------------ | -------------------------------- |
| A           | Host to IPv4 address           | `example.com -> 93.184.216.34`   |
| AAAA        | Host to IPv6 address           | `example.com -> ::1`             |
| MX          | Mail server info               | `mail.example.com`               |
| NS          | Name servers                   | `ns1.example.com`                |
| TXT         | Misc data (SPF, verifications) | `v=spf1 include:_spf.google.com` |
| CNAME       | Canonical names (aliases)      | `www -> example.com`             |

## Common Tools Used (Kali Linux)

| Tool           | Description                                | Usage Example                           |
| -------------- | ------------------------------------------ | --------------------------------------- |
| `nslookup`     | DNS lookup tool (simple queries)           | `nslookup example.com`                  |
| `dig`          | DNS lookup utility (detailed)              | `dig example.com any`                   |
| `host`         | Simple DNS querying tool                   | `host example.com`                      |
| `dnsenum`      | Perl script to enumerate DNS info          | `dnsenum example.com`                   |
| `fierce`       | DNS scanner to locate non-contiguous IPs   | `fierce -dns example.com`               |
| `dnsrecon`     | Powerful DNS enumeration script            | `dnsrecon -d example.com -a`            |
| `theHarvester` | Subdomain enumeration using search engines | `theHarvester -d example.com -b google` |


## OUTPUT:
# NSLOOKUP:
<img width="1567" height="837" alt="image" src="https://github.com/user-attachments/assets/ad9782b0-d8eb-45de-92fc-d0ae7ad134b1" />

# DIG:
<img width="877" height="772" alt="image" src="https://github.com/user-attachments/assets/3f767427-ee4e-41fa-8cc0-21b571f7f36f" />

# HOST:
<img width="830" height="543" alt="image" src="https://github.com/user-attachments/assets/68065815-addd-44ae-9d2c-6d50566353e7" />

# FIERCE:
<img width="1917" height="832" alt="image" src="https://github.com/user-attachments/assets/6b2b3546-c8c4-4623-a4b1-dd7c96ff93c7" />

# HARVESTER:
<img width="1020" height="757" alt="image" src="https://github.com/user-attachments/assets/303ed9fe-40d0-453b-835f-3adfd1b96b4e" />


## Architecture Diagram 
```
+-------------------+        +------------------+       +------------------+
|                   |        |                  |       |                  |
|   Attacker (You)  +------->|   Target Server   +<----->+    DNS Server    |
| Kali Linux / Parrot|       | (Mail / DNS Host) |       |  (Authoritative) |
+---------+---------+        +---------+--------+       +---------+--------+
          |                            ^                          ^
          |                            |                          |
          |                            |                          |
          |           +-----------------------------+            |
          |           |      Information Tools      |            |
          |           |-----------------------------|            |
          |           | smtp-user-enum              |            |
          |           | nmap --script smtp-enum-*   |            |
          |           | dnsenum                     |<-----------+
          |           +-----------------------------+
          |
          v
+-----------------------------+
|   Output/Report             |
|  - Usernames Found          |
|  - MX Records / Zones       |
|  - Subdomains / IPs         |
+-----------------------------+

```

## dnsenum
**Purpose:** A multithreaded Perl script to enumerate information from DNS servers.

**Use case:** Performs DNS zone transfers, brute force subdomains, and gather host IPs.

```
dnsenum example.com
```

## Output:

<img width="1919" height="977" alt="Screenshot 2025-09-04 104949" src="https://github.com/user-attachments/assets/edd4e1cf-2c71-47e7-9be2-9b97af1b5729" />


## smtp-user-enum
**Purpose:** Standalone tool used to enumerate valid users by using the VRFY, EXPN, or RCPT TO commands.

**Use case:** Brute-forces SMTP to find users.

```
smtp-user-enum -M VRFY -U users.txt -t <target-ip>
```
  
 ## Output
  
<img width="1918" height="548" alt="image" src="https://github.com/user-attachments/assets/e9bfcdf3-b1d9-41c8-b4d5-663de0701f88" />


## nmap –script smtp-enum-users.nse <hostname>

**Purpose:** Uses smtp-enum-users NSE script to enumerate valid users on an SMTP server.

**Use case:** Helps identify email accounts on mail servers.

```
nmap -p 25 --script smtp-enum-users.nse <target-ip>
```
## OUTPUT:
<img width="1917" height="292" alt="image" src="https://github.com/user-attachments/assets/a8642a62-a5f9-415f-817e-14a6c54d7d71" />



## RESULT:
The Google hacking keywords and enumeration tools were identified and executed successfully
