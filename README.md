
# 🛡️ Cybersecurity Reconnaissance & Network Scanning


## 📌 Project Overview

This repository contains the complete documentation, methodologies, technical findings, and evidence collected during **Week 2 of the Networkwalks Cybersecurity Internship (Batch B082)**.

The project focuses on the initial stages of a professional penetration-testing lifecycle:

* 🔎 Reconnaissance & Footprinting
* 🕵️ Open-Source Intelligence (OSINT)
* 🌐 Web Technology Fingerprinting
* 🔍 Search Engine Reconnaissance
* 🕸️ Infrastructure & Entity Mapping
* 📡 Internal Network Discovery
* 🗺️ Network Topology Mapping

The objective was to understand how a security professional can gather publicly available information, identify exposed assets, build an infrastructure profile, and discover hosts within an authorized local network **before moving toward vulnerability assessment or exploitation**.

All activities were performed within an authorized educational scope and/or against locally owned and controlled systems.

---

## 🎯 Project Objectives

The primary objectives of this project were to:

* Understand the reconnaissance phase of penetration testing.
* Perform active and passive footprinting.
* Collect publicly available domain and DNS information.
* Fingerprint web technologies and security mechanisms.
* Understand Google Hacking Database (GHDB) reconnaissance.
* Identify publicly indexed resources and potential exposures.
* Perform graphical OSINT and infrastructure mapping.
* Aggregate publicly available emails and subdomains.
* Perform local network host discovery.
* Identify active hosts within an authorized subnet.
* Generate a visual network topology.
* Document findings, evidence, risks, and security recommendations.

---

# 🧰 Tools & Technologies

| Category                   | Tools                 |
| -------------------------- | --------------------- |
| 🐉 Security OS             | Kali Linux            |
| 🪟 Operating System        | Windows               |
| 🔎 Domain Reconnaissance   | `WHOIS`, `nslookup`   |
| 🌐 Web Fingerprinting      | `WhatWeb`             |
| 📡 HTTP Analysis           | `curl -I`             |
| 🛡️ WAF Detection          | `Wafw00f`             |
| 🗂️ DNS Enumeration        | `DNSRecon`            |
| 🔍 Search Engine Recon     | GHDB / Google Dorking |
| 🕵️ OSINT Aggregation      | theHarvester          |
| 📡 Network Discovery       | Nmap                  |
| 🖥️ Network Visualization  | Zenmap                |

---

# 📂 Repository Structure

```text
NetworkWalks-B082-Week2-Reconnaissance-and-Scanning/
│
├── 📁 W2 PM1 - Kali Linux Footprinting/
│   └── curl
|   └── dnsrecon
|   └── nslookup
│   └── PM1-a
|   └── PM1-b
|   └── PM1-c
|   └── wafw00f
|   └── whatweb
|   └── whois
|
├── 📁 W2 PM2 - GHDB (Google Hacking Database) Dorking/
│   └── W2-PM2 - Footprinting with GHDB
│
├── 📁 W2 PM3 - Infrastructure Mapping with Maltego/
│   └── PM3-a
|   └── PM-b
│
├── 📁 W2 PM4 - OSNIT Aggregation via theHarvest/
│   └── all
|   └── baidu
|   └── PM4-a
|   └── PM4-b
|   └── PM4-c
|
│
├── 📁 W2 PM5 - Local Network Scanning with Zenmap/
│   └── PM5-a
|   └── PM5-b
|
│
└── 📁 W2 PM-FINAL - Report/
    ├── Penetration Testing Report.pdf
    └── Letter of Authorization.pdf
```

---

# 🧭 Module Navigation

## 🔍 W2-PM1 — Kali Linux Footprinting

**Focus:** Active and passive reconnaissance against an authorized external target.



### 🛠️ Tools Used

* `WHOIS`
* `WhatWeb`
* `nslookup`
* `curl -I`
* `Wafw00f`
* `DNSRecon`

### 🔎 Key Findings

* Extracted domain registrar and registration information.
* Identified **GoDaddy** as the registrar.
* Fingerprinted the target web technologies.
* Identified **WordPress 7.0.4**.
* Identified **WP Download Manager 3.3.58**.
* Identified an **Apache** web server.
* Resolved the target IP address.
* Analyzed HTTP response headers.
* Identified **ModSecurity (SpiderLabs)** as the Web Application Firewall.
* Enumerated DNS infrastructure.
* Identified MX and cPanel-related SRV records.

The report documents PM1 as the active/passive footprinting module and records the results from the six Kali Linux reconnaissance tools. 

---

## 🌐 W2-PM2 — GHDB Dorking

**Focus:** Search-engine reconnaissance using advanced search operators.



### 🛠️ Tool Used

* Google Hacking Database (GHDB)
* Advanced Google search operators

### 🔎 Key Findings

* Studied advanced search-engine reconnaissance.
* Used search operators to identify publicly indexed resources.
* Identified examples of publicly exposed security-camera interfaces.
* Encountered technologies including **webcamXP** and **Axis** camera interfaces.
* Identified open directory listings.
* Located publicly accessible mathematics-related PDF directories.
* Demonstrated how search-engine indexing can unintentionally expose resources.

The report identifies GHDB reconnaissance as a method for discovering information that may already be indexed by public search engines. 

---

## 🕵️ W2-PM3 — OSINT Aggregation via theHarvester

**Focus:** Passive metadata collection and OSINT aggregation.



### 🛠️ Tool Used

* theHarvester

### 🔎 Key Findings

The exercise used a large-scale public scope:

```text
microsoft.com
```

Using publicly available data sources, the assessment:

* Collected publicly indexed corporate email information.
* Identified publicly indexed subdomains.
* Used the **Baidu** data source.
* Extracted one corporate email address.
* Identified four subdomains.
* Identified examples including:

```text
hxd.research.microsoft.com
watson.microsoft.com
```

* Demonstrated the importance of API configuration.
* Observed missing API-key errors from sources such as BeVigil, Shodan, and GitHub Code.

The report documents this as passive OSINT collection without directly interacting with the target's servers. 

---

## 📡 W2-PM4 — Local Network Scanning with Zenmap

**Focus:** Internal network discovery and host mapping.



### 🛠️ Tools Used

* Zenmap
* Nmap

### 🎯 Target Network

```text
10.0.0.0/24
```

### 🔎 Key Findings

An ICMP host-discovery scan was performed using:

```bash
nmap -sn 10.0.0.0/24
```

The scan identified three active hosts:

| IP Address | Identified Environment        |
| ---------- | ----------------------------- |
| `10.0.0.1` | QEMU virtual NIC              |
| `10.0.0.2` | Active virtual host           |
| `10.0.0.3` | Oracle VirtualBox virtual NIC |

Additional network information, including hardware MAC addresses where available, was collected.

Zenmap's topology functionality was then used to create a visual representation of the discovered network.

The report confirms the three active hosts and the subsequent topology mapping. 

---

# 🔄 Penetration Testing Workflow

The five modules demonstrate a progression from external intelligence gathering to internal network discovery.

```text
                    START
                      │
                      ▼
          ┌─────────────────────┐
          │ Reconnaissance      │
          │ & Footprinting      │
          └──────────┬──────────┘
                     │
                     ▼
          ┌─────────────────────┐
          │ Kali Linux Tools    │
          │ WHOIS / WhatWeb     │
          │ DNSRecon / Wafw00f  │
          └──────────┬──────────┘
                     │
                     ▼
          ┌─────────────────────┐
          │ GHDB Dorking        │
          │ Search Engine OSINT │
          └──────────┬──────────┘
                     │
                     ▼
          ┌─────────────────────┐
          │ Maltego Mapping     │
          │ Entity Relationships│
          └──────────┬──────────┘
                     │
                     ▼
          ┌─────────────────────┐
          │ theHarvester OSINT  │
          │ Emails / Subdomains │
          └──────────┬──────────┘
                     │
                     ▼
          ┌─────────────────────┐
          │ Network Discovery   │
          │ Zenmap / Nmap       │
          └──────────┬──────────┘
                     │
                     ▼
          ┌─────────────────────┐
          │ Host Identification │
          │ & Topology Mapping  │
          └──────────┬──────────┘
                     │
                     ▼
                    END
```

---

# 📊 Key Findings Summary

| Module  | Primary Finding                                                  |
| ------- | ---------------------------------------------------------------- |
| 🔍 PM1  | Web technologies, server, WAF and DNS infrastructure identified  |
| 🌐 PM2  | Publicly indexed cameras and open directories identified         |
| 🕵️ PM3 | Public email addresses and subdomains identified                 |
| 📡 PM4  | Three active hosts discovered on the local `10.0.0.0/24` network |

---

# ⚠️ Risk Observations

The Week 2 assessment demonstrated several types of potential security exposure:

### 🟠 Web Technology Information Exposure

Publicly identifiable technologies and versions can help attackers identify software that may require further security review.

### 🟢 WAF Technology Disclosure

The presence of ModSecurity was identifiable during reconnaissance, revealing information about the target's defensive architecture.

### 🟠 DNS Infrastructure Exposure

MX, TXT, and SRV records contributed to a broader understanding of the target's infrastructure.

### 🔴 Publicly Indexed Devices and Directories

GHDB reconnaissance demonstrated that security devices and directories can become publicly discoverable when incorrectly configured.

### 🟠 Public Email and Subdomain Exposure

OSINT sources can reveal corporate email addresses and subdomains that may contribute to phishing or attack-surface discovery.

### 🟠 Internal Host Visibility

Network discovery identified multiple active virtual hosts on the local authorized network.

The formal report categorizes these findings by risk and includes corresponding mitigation recommendations. 

---

# 🧠 Key Learning Outcomes

Through these five modules, I developed practical understanding of:

* 🔎 Active and passive reconnaissance
* 🌐 Domain and DNS enumeration
* 🖥️ Web technology fingerprinting
* 🛡️ WAF identification
* 🔍 Search-engine reconnaissance
* 🕸️ Graph-based OSINT
* 🕵️ Passive metadata aggregation
* 📧 Email and subdomain enumeration
* 📡 Network host discovery
* 🗺️ Network topology mapping
* 📊 Security finding documentation
* ⚠️ Risk identification and analysis
* 🛡️ Ethical and authorized security testing

These exercises reinforced that a significant amount of information about an environment can be learned **before direct exploitation**, simply by analyzing public information and network responses. 

---

# 📸 Evidence & Screenshots

Each individual module folder contains its corresponding evidence screenshots and technical outputs.

The final report contains evidence for:



Evidence 1  → Domain WHOIS Information

<img width="1920" height="1080" alt="PM 1 a" src="https://github.com/user-attachments/assets/2d5482dc-eb51-4d8a-b01f-4b4758a33861" />



Evidence 2  → WhatWeb / Nslookup / Curl / Wafw00f

<img width="1920" height="1080" alt="PM 1 b" src="https://github.com/user-attachments/assets/796a7316-7c9f-4503-a4dc-d7294feeb4b5" />



Evidence 3  → DNSRecon Enumeration

<img width="1920" height="1080" alt="PM 1 c" src="https://github.com/user-attachments/assets/32607823-35c0-4c08-a73b-59e025b4b732" />



Evidence 4  → Maltego Initialization

<img width="1920" height="1080" alt="PM 3 a" src="https://github.com/user-attachments/assets/57fc4c24-a0ac-4f4f-9718-259f8a425981" />



Evidence 5  → Maltego Visual Graph & Email Extraction

<img width="1920" height="1080" alt="PM 3 b" src="https://github.com/user-attachments/assets/439436d8-d071-496a-b51a-089d1584ca08" />


Evidence 6  → theHarvester Help & Syntax

<img width="1920" height="1080" alt="PM 4 a" src="https://github.com/user-attachments/assets/b421c4ba-2746-4aea-a16c-b945ff944929" />



Evidence 7  → theHarvester Data Extraction

<img width="1920" height="1080" alt="PM 4 b" src="https://github.com/user-attachments/assets/1a8ae897-c70b-458c-9322-fe8bed5503e1" />



Evidence 8  → Missing API-Key Demonstration

<img width="1920" height="1080" alt="PM 4 c" src="https://github.com/user-attachments/assets/4fa8ea7e-23b3-4472-a93e-b5f55148981c" />



Evidence 9  → Zenmap Local Ping Scan

<img width="1920" height="1080" alt="PM 5 a" src="https://github.com/user-attachments/assets/4ad91d9f-c643-4b60-8644-70ddae3191b2" />



Evidence 10 → Zenmap Network Topology

<img width="1920" height="1080" alt="PM 5 b" src="https://github.com/user-attachments/assets/7be1eb29-da14-42cf-9883-07e6b5933bef" />




The report documents all ten evidence items across the final deliverable. 

---

# 📑 Final Deliverable

The complete penetration-testing documentation contains:

* Methodology
* Scope
* Tools used
* Commands and activities
* Technical findings
* Evidence screenshots
* Risk analysis
* Security impact
* Recommendations
* Conclusion

---

# 🛡️ Recommendations

Based on the assessment, organizations should consider:

* Regularly reviewing publicly exposed web technologies.
* Keeping CMS and plugins updated.
* Properly configuring and monitoring Web Application Firewalls.
* Reviewing DNS records and unnecessary public infrastructure information.
* Preventing sensitive directories from being indexed by search engines.
* Reviewing publicly indexed devices and services.
* Regularly monitoring corporate email and subdomain exposure.
* Maintaining an accurate internal network asset inventory.
* Investigating unknown or unauthorized devices on internal networks.

The formal report includes detailed recommendations for the identified findings. 

---

# ⚖️ Legal & Ethical Disclaimer

All reconnaissance, OSINT, footprinting, and network-scanning activities documented in this repository were performed strictly within an **authorized educational scope** or against **locally owned and controlled systems**.

A formal authorization/Rules of Engagement process was followed for the applicable assessment scope.

This repository is intended for:

* 🎓 Cybersecurity education
* 🔬 Security research
* 🧪 Authorized penetration testing
* 🛡️ Defensive security learning

> ⚠️ **Never use the tools, commands, techniques, or information in this repository against systems or networks without explicit authorization.**

Unauthorized security testing may violate laws, regulations, organizational policies, and terms of service.

The original report explicitly states that testing was performed only against systems/devices where permission had been secured or that were owned by the tester. 

---

# 📚 Project Information

| Field              | Details                                         |
| ------------------ | ----------------------------------------------- |
| 🎓 Program         | Networkwalks Cybersecurity Internship           |
| 👨‍💻 Batch        | B082                                            |
| 📅 Week            | 02                                              |
| 🛡️ Project        | Cybersecurity Reconnaissance & Network Scanning |
| 🔎 Phase 1         | Reconnaissance & Footprinting                   |
| 📡 Phase 2         | Scanning & Network Discovery                    |
| 👤 Pentester       | Varad Payghan                                   |
| 📅 Assessment Date | 18 August 2026                                  |

---


# 👤 Author

**Varad Payghan**

B.Tech Computer Science Engineering

**Interests:** Cybersecurity • Ethical Hacking • Innovation & Automation

---

## ⭐ Acknowledgement

This project was completed as part of my cybersecurity learning journey and serves as the foundation for future ethical hacking and penetration-testing projects.

---

### 🔐 Cybersecurity Journey — Task 02

> **Reconnaissance → OSINT → Footprinting → Network Discovery → Topology Mapping**

**🔐 Learn responsibly. Test ethically. Document professionally.**
