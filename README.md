# OSINT Threat Intelligence Assessment

## Overview

This project presents a comprehensive Open-Source Intelligence (OSINT) and Threat Intelligence assessment conducted on **Kortnit Hospitality**, a global hospitality organization used as a cybersecurity case study.

The purpose of this project was to identify publicly accessible information, evaluate exposed digital infrastructure, analyze potential security risks, and profile real-world threat actors targeting the hospitality industry using strictly passive reconnaissance techniques.

The assessment combines:
- OSINT gathering
- Google Dorking
- DNS Analysis
- Maltego Visualization
- Shodan Reconnaissance
- theHarvester Enumeration
- Threat Actor Profiling
- MITRE ATT&CK Mapping
- Risk Assessment and Security Recommendations

---

# Project Objectives

The key objectives of this project were to:

- Conduct passive reconnaissance on Kortnit Hospitality
- Identify publicly exposed assets and infrastructure
- Analyze the organization’s attack surface
- Investigate publicly available security risks
- Profile advanced threat actors targeting hospitality organizations
- Apply MITRE ATT&CK framework concepts
- Recommend layered cybersecurity defenses

---

# Rules of Engagement

All activities conducted during this project strictly followed ethical cybersecurity and passive reconnaissance guidelines.

## Ethical Scope
- No active exploitation
- No brute-force attacks
- No unauthorized access
- No disruption of services
- No vulnerability exploitation
- OSINT-only methodology

The entire assessment relied exclusively on publicly accessible information.

---

# Technologies and Tools Used

|Tool | Purpose |
|------|---------|
| Kali Linux | Reconnaissance platform |
| Google Dorking | Public information discovery |
| theHarvester | Subdomain and infrastructure enumeration |
| Shodan | Internet-facing service discovery |
| Maltego Community Edition | Infrastructure visualization |
| nslookup | DNS validation |
| MITRE ATT&CK | Threat actor mapping |
| OSINT Methodologies | Passive intelligence gathering |

---

# Company Profile

## Target Organization

|Category | Details |
|----------|---------|
| Company | Kortnit Hospitality |
| Sector | Hospitality |
| Primary Domain | kortnit.com |
| Analyst | Alex Morgan |
| Role | Threat Intelligence Analyst |
| Division | Kortnit Hospitality Security |

Kortnit Hospitality operates hotels, resorts, residential properties, customer portals, booking systems, loyalty platforms, and mobile applications worldwide.

---

# Digital Presence

Kortnit Hospitality maintains a significant online presence including:

- Main corporate website
- Booking and reservation systems
- Customer portals
- Mobile applications
- Loyalty platforms
- Employee access systems
- Regional subdomains
- Third-party integrations

---

# Global Presence

- Over 9,000 properties worldwide
- Operations in more than 140 countries
- Large global workforce
- One of the world’s largest hospitality organizations

---

# Data Potentially Managed

## Customer Data
- Names
- Email addresses
- Phone numbers
- Passport details
- Travel history

## Financial Data
- Payment card information
- Billing records

## Loyalty Data
- Loyalty account information
- Customer preferences

---

# Step 1 – Company Profiling

The company profiling phase focused on understanding:
- Business operations
- Infrastructure complexity
- Cybersecurity relevance
- Attack surface exposure

## Key Findings

Kortnit Hospitality:
- Stores highly sensitive customer information
- Maintains a large global attack surface
- Uses cloud and CDN infrastructure extensively
- Relies on interconnected digital services
- Has experienced significant historical cyber incidents

### Known Cybersecurity History
Kortnit Hospitality has experienced major data breaches involving exposure of:
- Customer names
- Email addresses
- Passport details
- Travel records

Example:
- 2018 “Starwood Incident”

---

# Step 2 – Google Dorking

Google Dorking techniques were used to identify publicly indexed resources and exposed services.

## Queries Used

```bash
site:kortnit.com filetype:pdf
site:kortnit.com intitle:login
site:kortnit.com "sign in"
site:*.kortnit.com -www
```

## Findings

### Public Documents
Publicly accessible PDF documents revealed:
- Operational materials
- FAQs
- Internal workflows
- Instructional guides

### Login Pages
Several employee and partner authentication portals were discovered.

### Sign-in Pages
Publicly accessible customer login interfaces were identified.

### Subdomains
Numerous subdomains associated with booking, loyalty, and partnership services increased the organization’s attack surface.

---

# Step 3 – theHarvester and Shodan Analysis

## theHarvester Enumeration

### Command Used

```bash
theHarvester -d kortnit.com -b all
```

## Results

The scan identified:
- Over 100 subdomains
- Multiple IP addresses
- CDN infrastructure
- Public-facing services
- Employee and HR portals

### Infrastructure Observed
The organization heavily relied on:
- Akamai Technologies (AS16625)
- Akamai International B.V. (AS20940)

This indicates extensive use of:
- CDN services
- DDoS protection
- Distributed infrastructure

---

# Shodan Analysis

Shodan searches were conducted to identify publicly exposed systems and services.

## Observed Services

| Port | Service |
|------|---------|
| 80 | HTTP |
| 443 | HTTPS |
| 25 | SMTP |
| 53 | DNS |
| 161 | SNMP |

## Geographic Distribution

Infrastructure was identified across:
- United States
- Japan
- Singapore
- Ireland
- India
- Brazil
- China

## Key Observations

The exposed infrastructure suggests:
- Large digital footprint
- Distributed infrastructure
- Broad attack surface
- Multiple internet-facing services

---

# Step 4 – Maltego Visualization Report

Maltego Community Edition was used to map relationships between:
- Domains
- Subdomains
- IP addresses
- Netblocks
- Email accounts
- Infrastructure ownership

---

# Methodology

The investigation began with the primary domain:

```text
kortnit.com
```

The analysis focused on:
- DNS resolution
- IP mapping
- ASN identification
- Subdomain enumeration
- Email discovery
- Infrastructure correlation

---

# DNS to IP Mapping

Resolved IP addresses included:

```text
193.108.91.7
193.108.91.22
23.211.133.65
84.53.139.64
35.100.174.64
35.100.168.64
```

---

# ASN and Netblock Analysis

Associated netblocks included:

```text
193.108.91.0 – 193.108.91.255
23.211.133.0 – 23.211.133.255
84.53.139.0 – 84.53.139.255
```

These ranges were linked to:
- Akamai Technologies
- CDN infrastructure
- Distributed DNS systems

---

# Subdomain Discovery

Examples of discovered subdomains:

```text
ns1-7.akam.net
ns1-22.akam.net
use4.akam.net
eur4.akam.net
```

This demonstrates strong reliance on Akamai infrastructure.

---

# Email Discovery

Sample email addresses discovered:

```text
affiliate.manager@kortnit.com
privacy@kortnit.com
```

These addresses were linked to:
- Marketing operations
- Privacy and compliance functions

---

# External Integrations

Digital integrations identified included:
- LinkedIn
- Facebook
- Instagram
- TikTok
- Reddit
- Pinterest
- Partnerize
- Affiliate platforms

---

# Limitations

The Maltego Community Edition imposed several limitations:
- Restricted number of results
- Incomplete infrastructure mapping
- Limited ASN depth
- Partial subdomain discovery

---

# Step 5 – DNS Lookup Validation

DNS validation was conducted using:

```bash
nslookup
```

---

# DNS Lookup Summary

| Target | Result | Status |
|--------|---------|--------|
| api.kortnit.com | NXDOMAIN | Unresolved |
| jobs.kortnit.com | Akamai CDN IPs | Live |
| mail.kortnit.com | Timeout | Stale |
| smtp1.kortnit.com | No Response | Unresolved |
| portal.kornit.com | Cloudflare IP | Live |
| extranet.kortnit.com | Timeout | Stale |
| 23.62.104.124 | Akamai Reverse DNS | Live |
| 3.231.19.6 | AWS Reverse DNS | Live |
| 64.29.17.65 | No Reverse | Unresolved |
| 72.246.29.19 | Akamai | Live |
| 92.123.164.29 | Akamai | Live |

---

# DNS Analysis Findings

The DNS analysis identified:
- Active infrastructure
- Stale assets
- Unresolved services
- CDN and cloud dependencies

Infrastructure providers identified:
- Akamai
- Amazon AWS
- Cloudflare

---

# Step 6 – Threat Actor Profiling

Two major threat groups targeting hospitality organizations were analyzed:
- Darkhotel
- FIN5

---

# Threat Actor – Darkhotel

## Overview

Darkhotel is an advanced persistent threat (APT) group primarily associated with cyber espionage activities targeting:
- Hotels
- Executives
- Government officials
- High-value travelers

---

# Darkhotel TTPs

| Technique | MITRE ID |
|-----------|----------|
| Registry Run Keys | T1547.001 |
| Command Shell | T1059.003 |
| Drive-by Compromise | T1189 |
| Spearphishing Attachment | T1566.001 |
| Keylogging | T1056.001 |
| Obfuscation | T1027 |
| File Discovery | T1083 |
| Encrypted Channel | T1573.001 |

---

# Darkhotel Indicators of Compromise

Observed IOC patterns include:
- Malicious hotel login redirects
- Fake software updates
- Embedded malicious iframes
- Malicious `.LNK` and `.RAR` files

---

# Threat Actor – FIN5

## Overview

FIN5 is a financially motivated cybercriminal group known for targeting:
- Hotels
- Restaurants
- Gaming organizations
- POS systems

Primary objectives include:
- Payment card theft
- PII theft
- Credential compromise
- Financial fraud

---

# FIN5 TTPs

| Technique | MITRE ID |
|-----------|----------|
| Brute Force | T1110 |
| Credential Dumping | T1003 |
| Valid Accounts | T1078 |
| Remote Services | T1021 |
| Automated Collection | T1119 |
| Proxy Usage | T1090.002 |
| Clear Logs | T1070.001 |
| File Deletion | T1070.004 |

---

# FIN5 Indicators of Compromise

Associated tools and indicators include:
- RawPOS
- PsExec
- pwdump
- SDelete
- Suspicious VPN/RDP logins
- Memory scraping activity

---

# Threat Comparison

| Feature | Darkhotel | FIN5 |
|---------|-----------|------|
| Type | APT Group | Cybercrime Group |
| Motivation | Espionage | Financial Gain |
| Target | VIP Guests | Hospitality Businesses |
| Entry Method | Wi-Fi / Phishing | Credential Abuse |
| Impact | Data Espionage | Financial Theft |
| Sophistication | Very High | High |

---

# Higher Risk Assessment

## Higher Risk Group: FIN5

FIN5 was assessed as the higher-risk threat group because:
- It directly targets hospitality infrastructure
- Focuses on financial theft
- Targets payment systems
- Causes immediate business damage
- Exploits customer financial data

---

# Risk Assessment

| Risk Factor | Assessment |
|-------------|------------|
| Likelihood | High |
| Impact | Very High |
| Detection Difficulty | Difficult |
| Spread Potential | High |

---

# Security Recommendations

## 1. Secure Hotel Wi-Fi Infrastructure
- Network segmentation
- Secure captive portals
- Rogue access point monitoring

## 2. Improve Phishing Protection
- Advanced email filtering
- Attachment sandboxing
- Employee security awareness training

## 3. Enforce Multi-Factor Authentication
- MFA implementation
- Login anomaly detection
- Privileged account monitoring

## 4. Strengthen POS Security
- End-to-end encryption
- Payment tokenization
- Memory scraping detection

## 5. Deploy Endpoint Detection & Response (EDR)
- Detect PowerShell abuse
- Detect credential dumping
- Automated threat response

## 6. Centralized Logging and SIEM
- Log aggregation
- Authentication monitoring
- Incident response planning

---

# Ethical Considerations

## OSINT Usage
All research relied strictly on:
- Publicly accessible information
- Passive reconnaissance
- Ethical intelligence gathering

## Privacy and Confidentiality
- No real customer data was accessed
- No exploitation was performed
- Analysis remained theoretical and research-based

## Legal Compliance
- No scanning of live systems
- No unauthorized testing
- No harmful actions conducted

---

# Lessons Learned

## Key Lessons
- Human error remains a major cybersecurity weakness
- Hospitality organizations are high-value targets
- Threat actors combine multiple attack techniques
- Credential abuse remains highly effective

## Interesting Findings
- Hotel Wi-Fi used as an attack vector
- Legitimate credentials used to evade detection
- Scale of exposed infrastructure

## Future Improvements
- Develop MITRE ATT&CK Navigator visualizations
- Include deeper breach case studies
- Expand infrastructure correlation analysis

---

# Conclusion

This project demonstrates the importance of proactive and layered cybersecurity strategies within the hospitality sector.

Through OSINT techniques and threat intelligence analysis, the assessment identified:
- Publicly exposed infrastructure
- Potential attack vectors
- Realistic threat scenarios
- Threat actor methodologies
- Defensive security recommendations

The findings reinforce the importance of:
- Continuous monitoring
- Defense-in-depth strategies
- Security awareness training
- Incident response readiness
- Strong authentication controls

Cybersecurity is not only about prevention, but also:
- Detection
- Response
- Continuous improvement
[Read Me](https://drive.google.com/file/d/12pDFUxGSfUcu2XEAXT74lp-IgOC1CueU/view?usp=sharing)

# Author

## Iyabo Uwadiae

Cybersecurity Analyst | OSINT Researcher | Threat Intelligence Enthusiast
