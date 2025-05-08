
# Arena Simulation Installation Guide – Checks & Setup Commands

---

## 1. Check Prerequisites


### A) .NET Framework 4.8+

```cmd
:: Check if installed in CMD
reg query "HKLM\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full" /v Release
```
```PowerShell
:: Check if installed in PowerShell
(Get-ItemProperty "HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release
```
### Interpreting the Result:

If you see a value like **528040** (or **0x80xxx**), it means you have **.NET Framework 4.8** installed, which is the latest version of the **.NET Framework**.

### Common Values:

* **528040** = **.NET 4.8** (on **Windows 10** or **Windows 11**).
* **533320** = **.NET 4.8.1** (on **Windows 11** only).
### If the Value is Lees them: [Download .NET Framework 4.8](Arena/NDP481-Web.exe)



---

### B) Visual C++ Redistributable (x64) 2015–2022

```cmd
:: Check if installed
wmic product where "name like '%%Visual C++%%'" get name, version

```
### Exmpel output
```cmd
Name                                                            Version
Microsoft Visual C++ 2010  x64 Redistributable - 10.0.40219     10.0.40219
Microsoft Visual C++ 2013 x86 Minimum Runtime - 12.0.40664      12.0.40664
Microsoft Visual C++ 2010  x86 Redistributable - 10.0.40219     10.0.40219
Microsoft Visual C++ 2013 x64 Minimum Runtime - 12.0.40664      12.0.40664
Microsoft Visual C++ 2022 X64 Minimum Runtime - 14.40.33816     14.40.33816
Microsoft Visual C++ 2022 X86 Minimum Runtime - 14.40.33816     14.40.33816
Microsoft Visual C++ 2008 Redistributable - x64 9.0.30729.6161  9.0.30729.6161
Microsoft Visual C++ 2012 x64 Additional Runtime - 11.0.61030   11.0.61030
Microsoft Visual C++ 2022 X64 Debug Runtime - 14.40.33816       14.40.33816
Microsoft Visual C++ 2022 X86 Additional Runtime - 14.40.33816  14.40.33816
Microsoft Visual C++ 2013 x64 Additional Runtime - 12.0.40664   12.0.40664
Microsoft Visual C++ 2022 X64 Additional Runtime - 14.40.33816  14.40.33816
Microsoft Visual C++ 2012 x86 Additional Runtime - 11.0.61030   11.0.61030
Microsoft Visual C++ 2005 Redistributable                       8.0.61001
Microsoft Visual C++ 2012 x64 Minimum Runtime - 11.0.61030      11.0.61030
Microsoft Visual C++ 2013 x86 Additional Runtime - 12.0.40664   12.0.40664
Microsoft Visual C++ 2012 x86 Minimum Runtime - 11.0.61030      11.0.61030
Microsoft Visual C++ 2022 X86 Debug Runtime - 14.40.33816       14.40.33816
```
### If not installed: [Download VC++ Redist x64](Arena/VC_redist.x64.exe)

---

### C) SQL Server Compact 4.0

```cmd
:: Check if installed
reg query "HKLM\SOFTWARE\Microsoft\Microsoft SQL Server Compact Edition\v4.0" /v Version

```
### Exmpel output
```cmd
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Compact Edition\v4.0
    Version    REG_SZ    4.0.8876.1
```
### If this error appears to you: [Download SQL Server Compact 4.0](Arena/SSCERuntime_x64-ENU.exe)
```cmd
ERROR: The system was unable to find the specified registry key or value.
```


---

### D) Microsoft Office (64-bit)

```cmd
:: Check if Office is 64-bit
reg query "HKLM\SOFTWARE\Microsoft\Office\ClickToRun\Configuration" /v Platform

```
### Exmpel output
```cmd
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Configuration
    Platform    REG_SZ    x64
```
### If this error appears to you: [Download Microsoft Office 64-bit](https://www.microsoft.com/microsoft-365)
```cmd
ERROR: The system was unable to find the specified registry key or value
OR
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Configuration
    Platform    REG_SZ    x86
```


---

## 2. Check System Specifications

### A) **RAM**

```cmd
systeminfo | find "Total Physical Memory"
```

**Minimum Requirement**: **4 GB** of RAM.
**Recommended**: **8 GB** or more for better performance, especially when working with larger projects.

---

### B) **Disk Space**

```cmd
wmic diskdrive get size
```

**Minimum Requirement**: **2 GB** of free disk space.
**Recommended**: **10 GB** or more to ensure sufficient space for Arena files and projects.

---

### C) **Windows Version**

```cmd
ver
```

**Minimum Requirement**: **Windows 10** or **Windows 11** (latest versions).
**Recommended**: Use the latest version of **Windows 10** or **Windows 11** for better performance and support.

---


## 3. Install Arena Simulation [Download ](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/buying-options/download.html)

### A) For Students (No License)

```cmd
:: Write Your Name
```

### B) For Licensed Users

```cmd
:: Enter the serial number provided by your university/company
:: Zagazig University
```
### C) For Students (No License)

```cmd
:: Use "STUDENT" when asked for a serial number
```

---

## Important Notes

1. **Run as Administrator**: Always open Command Prompt as admin  
2. **Restart Required**: Reboot your PC after each installation  
3. **Recommended Order**:  
   - .NET Framework → Visual C++ → SQL Compact → Arena  

---

## Additional Resources

- [Download Arena Trial](https://www.rockwellautomation.com/en-us/products/software/arena-simulation.html)  
- [Official User Manual](https://literature.rockwellautomation.com/idc/groups/literature/documents/um/arena-um001_-en-p.pdf)

---
