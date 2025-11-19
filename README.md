# Windows 10 STIG Remediation Scripts

This repository contains a growing collection of **Windows 10 Security Technical Implementation Guide (STIG)** remediation scripts written in PowerShell. Each script enforces a specific DoD STIG requirement by configuring the appropriate registry settings, audit policies, or system parameters to a compliant state.

The purpose of this collection is to provide:

- **Reliable, repeatable automation** for securing Windows 10 systems  
- **Clear and auditable** configuration changes  
- A lightweight alternative to enterprise-level compliance tools when targeted, script-based hardening is preferred  
- A reference library for learning PowerShell, system hardening, and security compliance automation  

All scripts follow a strict, consistent structure to ensure maintainability and ease of use.

---

## 🔧 Script Structure & Conventions

Every remediation script includes:

### **1. A Standardized Metadata Block**
This appears at the top of each `.ps1` file and documents:
- STIG ID  
- Synopsis  
- Author info  
- Versioning  
- Testing log fields  
- Usage instructions  

This ensures each script is self-explanatory and traceable.

### **2. A STIG-Specific Configuration Section**
Only this section varies between scripts.  
It defines:
- Registry paths & values  
- Audit policy subcategories  
- System configuration requirements  

Everything else is standardized.

### **3. Protected Execution & Verification Logic**
Each script includes:
- Administrator privilege checks  
- Automatic creation of missing registry keys  
- Remediation of incorrect or missing settings  
- Verification of applied changes  
- Meaningful success/error output  
- Exit codes (`0` = success, `1` = non-compliant/failure)

This provides reliable enforcement and easy integration into automation pipelines.

---

## 🛡️ Security Philosophy

These scripts enforce a **strict-compliance model**:

- Required values are applied exactly as the STIG mandates  
- Existing incorrect settings are overwritten  
- Missing keys are created  
- Final verification ensures the endpoint is compliant  

This makes them ideal for:
- Manual system hardening  
- Automated baselines  
- Compliance auditing  
- Vulnerability remediation workflows  
- Lab and enterprise environments  

---

## 📁 Repository Structure

A suggested structure:

```
/Scripts
    WN10-XX-XXXXX_<ShortName>.ps1         # Individual remediation scripts

/Checks
    Test-WN10-XX-XXXXX_<ShortName>.ps1    # Optional compliance-only scripts

README.md                                 # This file
```

Use whatever directory layout best fits your workflow—this is simply a common approach.

---

## 🚀 Usage

Run any script individually:

```powershell
PS C:\> .\WN10-CC-000XXX_<Name>.ps1
```

Requirements:
- Windows 10 OS  
- Elevated PowerShell session  
- Execution policy set appropriately (ex: `RemoteSigned`, `Unrestricted`, or `Bypass`)  

Scripts are self-contained and do not require additional modules.

---

## 📈 Roadmap

Planned enhancements include:

- A **master remediation script** (runs all modules sequentially)  
- A library of **check-only** compliance scripts  
- Markdown/HTML compliance reports  
- Log and transcript support  
- Batch file wrapper for enterprise deployment  
- CI pipeline for automated validation  

---

## 🤝 Contributions & Expansion

This project is actively expanding.  
If you'd like help with:

- Adding more STIG IDs  
- Writing verification-only scripts  
- Improving repo structure  
- Creating documentation or reports  

Just ask — happy to assist.
