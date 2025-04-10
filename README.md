# RedLotus SS GUIDE Remastered - 

This repository hosts key resources for understanding and performing ScreenShares (SS) or Hack Checks, maintained under the RedLotus umbrella. It contains two primary guides:

1.  **`The RedLotus Introductory Guide to SS ENG.pdf`**: This document serves as an initial introduction, designed for those less experienced in the world of SS. It focuses on explaining the absolute basics and foundational concepts of ScreenSharing.
2.  **`The RedLotus SS GUIDE Remastered (index.html)`**: This is the main, comprehensive guide hosted within the `index.html` file in this repository. You can view it directly via GitHub Pages at: **[Insert Link Here]** (*Replace this with the actual link once deployed*).

The remainder of this README describes the extensive content found within the **`RedLotus SS GUIDE Remastered (index.html)`**.

---

The **SS GUIDE Remastered** is meticulously crafted to provide a deep, structured understanding of screensharing practices. Primarily focused on the Windows environment and its application within gaming communities like Minecraft and FiveM, this guide delves into the procedures, essential tools, ethical considerations, common bypass techniques, and advanced forensic artifact analysis required for effective fair play enforcement.

Whether you're a new server staff member taking your first steps (perhaps after reading the introductory PDF), an experienced PC checker aiming to sharpen your skills, a cybersecurity enthusiast interested in practical digital forensics, or simply curious about anti-cheat methodologies, this guide offers invaluable insights.

## What You'll Find Inside the Remastered Guide (`index.html`):

This guide is structured to build knowledge progressively, from foundational concepts covered briefly in the introductory PDF to advanced techniques unique to this remastered version:

1.  **Introduction & Core Concepts:**
    *   Defining Screenshares (Hack Checks): Purpose, goals, and ethical considerations.
    *   The critical distinction: Proving cheat **Possession vs. Execution**.
    *   Understanding **Execution Context** (Game/Boot Instance) for accurate analysis.
    *   Overview of **Essential Tool Categories**: Remote Access (AnyDesk), Manual Analysis (System Informer), and Automated Scanners (Echo, Ocean).
    *   The **Staffer's Mindset**: Ethical conduct, learning from checks, and maintaining integrity.

2.  **Red Lotus Principles - An Ethical Framework:**
    *   Establishing ethical guidelines for screensharing.
    *   Prioritizing **Player Safety & Data Security**.
    *   **Mandatory Video Recording** protocols and their importance.
    *   Requirements for ScreenSharers (experience, verification).
    *   Anti-corruption measures and evidence handling.

3.  **Windows Fundamentals for Screensharing:**
    *   Deep dive into **File Systems**: NTFS vs. FAT32, focusing on NTFS **Journaling** (`$USNJrnl`, `$LogFile`).
    *   Understanding **MACB Timestamps** and the (un)reliability of Access Time.
    *   Key **NTFS Metafiles & Structures**: `$MFT`, Alternate Data Streams (ADS), File Attributes, and their significance in detection.

4.  **Common Windows Artifacts & Basic Analysis:**
    *   Parsing crucial evidence sources for execution and activity traces.
    *   **Execution Artifacts**: Prefetch (`.pf` files, analysis with WinPrefetchView/PECmd), Temporary Files (`%temp%`, JnativeHook traces).
    *   **User Activity**: Recent Items (`shell:recent`, `.lnk` files), Recycle Bin (`$Recycle.bin`, `$I`/`$R` metadata).
    *   Introduction to the **Windows Registry**: Structure (Hives, Keys, Values), key locations for forensic data (PCA, BAM, RecentDocs), and analysis tools (Regedit, Registry Explorer).
    *   Introduction to **Windows Event Logs**: Structure (`.evtx`), key channels (Security, System, Application), Event Viewer usage, and critical Event IDs for detecting tampering (4616, 1102, 3079, 104).

5.  **Minecraft-Specific Analysis:**
    *   Understanding Minecraft's **Java/JVM Architecture** (`javaw.exe`).
    *   Dealing with various **Launchers** (Official, Lunar, Badlion, etc.).
    *   Reliably locating the active **`.minecraft` Folder**.
    *   **Detailed Forge Mod Analysis**: Size checks, decompilation (Luyten/Recaf), SHA256 hash verification, detecting "unloaded" mods via memory analysis (System Informer), using HabibiModAnalyzer.
    *   Detecting **Javaedit** (modified client JARs) via hash comparison.

6.  **Mouse, Macro & Input Device Analysis:**
    *   Investigating **Macros** via mouse software configuration files (Logitech, Razer, SteelSeries, Roccat, Red Dragon, Glorious, etc.).
    *   Understanding **Debounce Time**, "mouse abuse" techniques, and server rules.
    *   Detecting **lowered debounce settings** in supported mice (Glorious, Roccat, Bloody, etc.).

7.  **Manual Screensharing Techniques (Core Tools & Methods):**
    *   **Process & Memory Analysis**: Mastering **System Informer** (Process Hacker) - configuration (Kernel Driver), targeted **string searching** in crucial processes (`explorer.exe`, `csrss.exe`, `svchost.exe -s dps`, PlugPlay, PcaSvc).
    *   **Artifact Examination**: In-depth Prefetch analysis, using LastActivityView for artifact aggregation, leveraging **Search Everything** for rapid file system investigation (advanced queries), parsing the **USN Journal** (JournalTrace, Echo Journal Tool), basic registry and event log checks, and attempting deleted file recovery (Recuva).

8.  **Comprehensive Bypass Techniques & Detection Strategies:**
    *   **Concealment & Obfuscation**: Spoofed Extensions, Unicode Characters, Alternate Data Streams (ADS), Code Obfuscation, Steganography.
    *   **System & Artifact Manipulation**: Timestomping ($SI vs $FN analysis), Hex Editing (hash changes, USN logs), Read-Only Attribute bypasses, Service Thread Suspension, CMD Obfuscation, Disabling OS Features (Registry/Group Policy).
    *   **Evidence Clearing**: Prefetch, Registry Keys (BAM, RecentDocs, UserAssist), USN Journal (`fsutil`), Event Logs (`wevtutil`), Recycle Bin, File Replacement method.
    *   **Permission Abuse**: `cacls`/`icacls` for folder permissions (e.g., Prefetch), Disabling Inheritance (Registry/Folders).
    *   **Environment & Advanced Evasion**: Disk Partition manipulation, Task Scheduler abuse, Scripting Languages (PowerShell, Batch, VBS, etc.), Fileless Malware & LOLBins, COM Hijacking, Shellcode Injection, PowerShell Remoting, External USB Drives (FAT32 vs. NTFS), Virtual Machines, Cloud Storage sync abuse.
    *   **Code/Signature Evasion**: Suspicious DLLs (Injection Methods: Standard, Reflective, Hijacking, Proxying), Process Hollowing, .NET Assembly abuse, Fake Digital Signatures.

9.  **Advanced Artifact Analysis & Specialized Tools:**
    *   **Deep File System Forensics**: `$MFT` (MFTECmd), `$LogFile` (NTFS Log Parser), Advanced JumpLists/RecentDocs (JumpList Explorer, LECmd), `$INDX`/`$i30` Index Attributes (INDXRipper).
    *   **Advanced Execution/Activity Tracking**: Amcache/Syscache/RecentFileCache (Parsers by Zimmerman, Ruedas), Activities Cache (WxTCmd), SRUM analysis (SrumECmd).
    *   **Historical System State**: Leveraging Volume Shadow Copies (VSS) for deleted file recovery and timeline extension (ShadowExplorer, EZ Tools `--vss` flag).
    *   **Memory Forensics**: Process/Memory Dump Analysis basics (Volatility, MemProcFS, `strings64` for command recovery).
    *   **Specialized Detection & Analysis Tools**: Using **YARA Rules**, File **Entropy Analysis**, **Detect It Easy (DiE)** for PE analysis, **Velociraptor** for advanced live response and hunting, **Magnet EDD** for encrypted disk detection, and dedicated community tools from **Rancio**, **Echo**, and **Spok** (e.g., JournalTrace, PathsParser, BAM-parser).
    *   Leveraging **Specific PowerShell Scripts** for automation (signature checking, artifact parsing, information gathering).

10. **Ban Evasion & Alternate Account Detection:**
    *   Understanding common **ban evasion tactics** (Alts, HWID spoofing, VMs).
    *   Techniques for **identifying alternate accounts** during screenshares (username artifacts, registry analysis, file system metadata, event logs, HWID linking).
    *   The crucial role of clear **server policies** and meticulous **evidence documentation**.

---

**A Note on Scope:**

This guide aims to be comprehensive but cannot cover every conceivable niche technique or outdated method. If certain topics appear omitted or are not explored in exhaustive detail, it is likely for one of these reasons:
*   They are largely **outdated**, and practical knowledge of them is rarely required in modern SS scenarios.
*   The underlying principle or detection method is **reproducible** using other techniques already detailed within the guide.
*   They involve highly **complex** procedures (e.g., deep kernel debugging, advanced reverse engineering) that, while powerful, are not considered fundamental for the majority of screenshares and were omitted to avoid overwhelming the reader.

The focus remains on providing the most relevant, effective, and broadly applicable knowledge for conducting thorough and ethical screenshares.

---


## How to Use This Resource:

*   **For Beginners:** Start with the **`Introductory Guide PDF`**, then move to the **`Remastered Guide (index.html)`**, reading sequentially to build a strong foundation.
*   **For Experienced Users:** Use the **`Remastered Guide (index.html)`** as a reference for specific techniques, advanced artifacts, tool usage, and understanding bypass methods.
*   **Tool Reference:** Quickly look up commands, file paths, registry keys, and recommended tools for specific analysis tasks within the Remastered Guide.

---

***Disclaimer:*** *The information provided in these guides is intended for educational purposes related to legitimate anti-cheat enforcement and digital forensics investigation to promote fair play. Misuse of this information for malicious activities is strongly discouraged.*
