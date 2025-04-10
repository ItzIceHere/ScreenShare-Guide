# RedLotus SS Basic to Advanced Guides.

This repository hosts the **RedLotus SS Basic to Advanced Guides**, comprehensive guides designed to provide a clear and structured understanding of hack checks, commonly known as screenshares (SS), particularly within gaming communities like Minecraft and FiveM. The guide focuses on the procedures, tools, and ethical considerations involved in ensuring fair play.

Whether you are a server staff member learning the ropes, an experienced PC checker looking to refine techniques, or simply interested in the technical side of SS practices, this guides offer valuable insights and detailed procedures.

**Note:** I have tried to maintain in both the introductory and more in-depth guides a preicise but easy-to-understand language without going into too much detail of technicalities so as not to overload you with information  

## Key Topics Covered:

### 1. Introduction & Fundamentals
*   **What is a Screenshare?** Definition and purpose.
*   **Goal:** Demonstrating cheat usage (Possession vs. Execution).
*   **Execution Context:** Importance of game instance/boot instance.
*   **Tools Overview:** Screen sharing (AnyDesk), Manual tools (Process Hacker/System Informer), Automatic tools (Echo, Ocean).
*   **Staffer Perspective:** Ethical goals, learning from failure, integrity.

### 2. Red Lotus Principles (Ethical Framework)
*   **Core Principles:** Player Safety > Accuracy, Data Security, Upholding Fair Play.
*   **Security & Privacy:** Player well-being, data protection, mandatory video recording.
*   **ScreenSharer Requirements:** Age, experience, verified skills, country info (for legal only).
*   **Protocols:** Mandatory video recording, purposes, consequences, evidence review rights.
*   **Anti-Corruption:** Preventing bribery, evidence scrutiny.

### 3. Windows Fundamentals for SS
*   **File Systems:** NTFS, FAT32, Journaling (`$USNJrnl`, `$LogFile`).
*   **Timestamps:** MACB (Modified, Access, Changed, Birth) definition and significance (especially unreliability of Access time).
*   **Key NTFS Components:** `$MFT` (Master File Table), `$USNJrnl` (USN Records), `$LogFile`, Alternate Data Streams (ADS), File Attributes.

### 4. Common Windows Artifacts & Basic Analysis
*   **Execution Traces:** Prefetch (`.pf` files, WinPrefetchView, PECmd), Temporary Files (`%temp%`, JnativeHook).
*   **Recent Activity:** Recent Items (`shell:recent`, `.lnk` files), Recycle Bin (`$Recycle.bin`, `$I`/`$R` files).
*   **Other Locations:** Task Scheduler, PCA, PowerShell History, User Assist.
*   **Registry Introduction:** Hives, Keys, Values, Basic Types (`REG_SZ`, `REG_DWORD`, etc.), Tools (`regedit`, Registry Explorer).
*   **Event Logs Introduction:** Purpose, `.evtx` files, Channels (Application, Security, System), EventLog Service, Event Viewer (`eventvwr.msc`), Key Event IDs (4616, 1102, 3079, 104).

### 5. Minecraft Specific Analysis
*   **Architecture:** Java/JVM (`javaw.exe`), Launchers (Official, Custom), `.minecraft` folder (finding the correct one).
*   **Forge Mod Analysis:** Locating `mods` folder, size analysis, decompilation (Luyten, Recaf), hash checks (SHA256), detecting "unloaded" mods (System Informer memory strings), HabibiModAnalyzer.
*   **Javaedit Detection:** Hash checking core Minecraft `.jar` files.

### 6. Mouse, Macro & Input Analysis
*   **Macros:** Definition, detection strategies (checking mouse software config files - Logitech, Razer, SteelSeries, Roccat, Red Dragon, Glorious, etc.).
*   **Debounce Time:** Definition, "mouse abuse", server rules context, detection via mouse software settings (Glorious, Cooler Master, Roccat, Bloody, etc.).

### 7. Manual SS Techniques (Tools & Methods)
*   **Process/Memory Analysis:** System Informer (Process Hacker) - configuration (Kernel Driver), string searching specific processes (`explorer.exe`, `csrss.exe`, `svchost.exe -s dps`, PlugPlay/DCOMLaunch, PcaSvc).
*   **Prefetch Analysis:** In-depth review using WinPrefetchView/PECmd, troubleshooting bypasses.
*   **LastActivityView:** Aggregating artifacts (Prefetch, Registry, Event Logs).
*   **Search Everything:** Rapid file searching, advanced syntax (sorting, filtering, content search).
*   **Journal Analysis:** `$USNJrnl` analysis using JournalTrace or Echo Easy Journal Viewer.
*   **Registry Viewers:** Basic usage of `regedit` and Registry Explorer for relevant keys (Prefetch, PCA, BAM, RecentDocs, etc.).
*   **Event Viewer:** Basic usage focusing on key Event IDs for bypass detection.
*   **Recuva:** Deleted file recovery attempts.

### 8. Common Bypass Techniques & Detection
*   **Concealment:** Spoofed Extensions, Unicode Characters, Alternate Data Streams (ADS), Code Obfuscation, Steganography.
*   **Manipulation:** Timestomping ($SI vs $FN, $UsnJrnl checks), Hex Editing (hash changes, $UsnJrnl logging), Read-Only Attribute ($UsnJrnl checks), Service Thread Suspension, CMD Obfuscation, Disabling Features (Registry/Group Policy).
*   **Clearing:** Prefetch, Registry (BAM, RecentDocs), USN Journal (`fsutil`), Event Logs (`wevtutil`, service stop), Recycle Bin, File Replacement Method.
*   **Permissions:** `cacls`/`icacls` usage (Prefetch folder), Disabling Inheritance (Registry/Folders).
*   **Environment:** Disk Partition Manipulation, Task Scheduler Abuse, Scripting Languages (PowerShell, Batch, VBS, Python, AutoIt, HTA), Fileless Malware/LOLBins, COM Hijacking, Shellcode Injection, PowerShell Remoting, External USB (FAT32 vs NTFS), VMs, Cloud Storage.
*   **Advanced Techniques:** Suspicious DLLs (Standard/Reflective Injection, Hijacking, Proxying), Process Hollowing, .NET/Assembly Abuse, Fake Digital Signatures.

### 9. More Artifact Analysis (Advanced Tools & Techniques)
*   **Deep File System:** `$MFT` (MFTECmd), `$LogFile` (NTFS Log Parser), JumpLists/RecentDocs (JumpList Explorer, LECmd), `$INDX`/`$i30` (INDXRipper).
*   **Execution/Activity:** Amcache/Syscache/RecentFileCache (AmcacheParser, Ruedas, RecentFileCacheParser), Activities Cache (WxTCmd), SRUM (SrumECmd).
*   **System State:** Volume Shadow Copies (VSS - `vssadmin`, ShadowExplorer, EZ Tools `--vss` flag).
*   **Memory:** Process/Memory Dump Analysis (Volatility, MemProcFS, `strings64`), Kernel Live Dumps.
*   **Specialized Tools:** YARA Rules, File Entropy Analysis, Detect It Easy (DiE), Velociraptor (VQL, NTFS Parsers, YARA Hunts), Magnet EDD, Rancio's Tools (DDFO, Unicode Detector, Ocean, GlobalLister, Maceta), Echo's Tools (BAM, Journal, UserAssist, Strings, USB), Spok's Tools (Replaceparser, JournalTrace, PathsParser, BAM-parser, etc.), Specific PowerShell Scripts (Signature Checks, Artifact Parsers, Info Gathering).

### 10. Ban Evasion & Alt Account Detection
*   **Concept:** Understanding evasion tactics (Alts, HWID changes, VMs, IP changes).
*   **Detection Methods:** Username artifacts in files/logs, Registry analysis, File system metadata, Event Logs, HWID linking.
*   **Policy & Documentation:** Importance of clear server rules and meticulous evidence recording.

---

*Note: The information provided in the guide is intended for educational purposes within the context of legitimate anti-cheat and fair play enforcement. Misuse of this information is discouraged.*
