# 💾 Digital Forensics Workstation — FTK Imager | Volatility | Cyber Triage | Redline

This repository documents the setup and execution of a **Digital Forensics Workstation** developed as part of the *CYT215: Computer Forensics* course at **Seneca Polytechnic**.  
The objective was to design a functional forensic lab environment capable of **capturing and analyzing volatile memory** using industry-grade tools, simulating real-world **DFIR (Digital Forensics and Incident Response)** workflows.

---

## 🎯 Project Objective
Build a fully operational forensic lab that enables:
- Safe and repeatable digital investigations  
- Acquisition of live memory (RAM) from a target system  
- Malware and process analysis using multiple tools  
- Forensic reporting aligned with **chain-of-custody** principles  

---

## ⚙️ Lab Setup Overview

### 🖥️ 1. Virtualized Environment
- Created a **Windows 10 Enterprise VM** (3 vCPUs, 4 GB RAM, 40 GB HDD) using **VMware Workstation**.  
- Configured a **WSL Ubuntu environment** to support Python-based forensic utilities.  
- Installed essential dependencies for forensic tools (Python 3, pip, environment variables).

### 🔍 2. Tools Installed
| Tool | Purpose | Key Functions Used |
|------|----------|--------------------|
| **FTK Imager** | Memory acquisition | Captured `memdump.mem` live memory image |
| **Volatility 3** | Memory analysis (CLI) | `windows.pslist`, `windows.dlllist`, `windows.malfind`, `windows.info` |
| **Cyber Triage** | Automated triage | Incident-based analysis and IOC discovery |
| **Redline** | Malware analysis (GUI) | Session-based analysis of image packages |
| **Python & WSL** | Environment support | Executed Volatility modules and managed dependencies |

---

## 🔬 Analysis Workflow

1. **Memory Acquisition (FTK Imager)**  
   - Captured live system memory to `C:\Cases\Case1\memdump.mem`.  
   - Verified integrity and preserved file for forensic chain of custody.

2. **Volatility Analysis (Command Line)**  
   - `windows.info`: Extracted system build, version, and user data.  
   - `windows.pslist`: Listed active processes and parent-child relationships.  
   - `windows.dlllist`: Enumerated loaded DLLs per process to identify injected modules.  
   - `windows.malfind`: Detected suspicious memory allocations and injected code.

3. **Cyber Triage and Redline (GUI Analysis)**  
   - Performed automated IOC scanning on the acquired image.  
   - Generated incident reports identifying potential anomalies.  
   - Recorded operational issues (e.g., OS-specific incompatibility, missing IOCs).

4. **Reporting and Documentation**  
   - Recorded findings with timestamps, memory offsets, and PIDs.  
   - Documented procedures in compliance with **DFIR investigation standards**.

---

## 📈 Key Findings
- Successfully detected **hidden processes** and **malicious DLLs** via Volatility scans.  
- Identified multiple suspicious executables and persistence keys.  
- Created a **forensically sound workflow** integrating GUI and CLI analysis tools.  
- Demonstrated ability to handle live data acquisition and analysis safely in an isolated lab.

---

## 🧠 Skills Demonstrated
- **Memory Forensics and Malware Analysis**  
- **Digital Evidence Handling & Chain of Custody**  
- **Virtual Machine Configuration (VMware, WSL)**  
- **Volatility Plugin Utilization**  
- **Automated IOC Detection**  
- **Technical Documentation in DFIR context**

---

## 📄 Repository Content
| File | Description |
|------|--------------|
| [Digital-Forensics-Lab-Report.pdf](./Digital-Forensics-Lab-Report.pdf) | Complete report detailing setup, tools, analysis, and learning outcomes |

---

## 🧩 Tools Summary
**FTK Imager** → Memory Capture.
**Volatility 3** → Memory & Process Analysis.
**Cyber Triage** → Automated Incident Triage.
**Redline** → IOC and Threat Scanning.
**VMware & WSL** → Virtualized Testing Environment.

## 🚀 Future Improvements
- Integrate **Rekall** for extended volatility comparison.  
- Use **ELK Stack / Splunk** for centralized event analysis.  
- Add **timeline correlation** (log2timeline + Plaso).  
- Automate reporting workflow with Python scripting.

---

**Author:** *Devarshi Mahadevwala*  
**Course:** CYT215 — Computer Forensics  
**Certifications:** ISC² CC | CySA+ (In Progress)  
*Digital Forensics & Cloud Security Enthusiast*
