# 🕵️‍♂️ **Experiment No. 06 — Digital Forensic Analysis using Sleuth Kit (TSK)**

## 🔍 **Overview**

The **Sleuth Kit (TSK)** 🧰 is a versatile suite of command-line tools used in **digital forensics**.  
It enables investigators to analyze disk images 🖥️, uncover deleted files 🗑️, and extract critical digital evidence 🔎 from storage devices.  
This document walks through the complete process of using Sleuth Kit on a **Windows** system to perform forensic analysis.

---

## ⚙️ **Step 1: Installing Sleuth Kit**

1. **Download the Tool:**  
   - Head over to the official Sleuth Kit page or use this link:  
     👉 [Download Sleuth Kit](https://drive.google.com/drive/u/1/folders/1ilSFY7Tqn2L7AjQGhq8yJ8kixc_xTU-v)  
   - Choose the latest stable **Windows-compatible** version.

2. **Installation Process:**  
   - Run the installer and follow the setup wizard 🪄.  
   - Once done, TSK will be ready to use on your system!

---

## 💾 **Step 2: Acquire the Disk Image**

Before analysis, a **forensic disk image** (a perfect bit-by-bit copy) of the device is needed.

1. **Create Disk Image:**  
   - Use tools like **FTK Imager** 🧮 or **`dd`** to create an exact copy.  
   - Save it in a TSK-supported format: `.dd`, `.raw`, `.img`, or `.E01`.

2. **Sample Evidence Files:**  
   - For this lab, download the following from the provided link:  
     📁 `4Dell Latitude CPi.E01`  
     📁 `4Dell Latitude CPi.E02`

---

## 💽 **Step 3: Mounting the Disk Image (Optional)**

Mounting lets you access the disk image as if it were a normal drive.

- Use **OSFMount** 🧷 to mount the image in **read-only mode**.  
- 🔒 *Note: This is optional but helps when browsing the file system.*

---

## 🧭 **Step 4: File System Analysis with TSK**

Now let’s dive into Sleuth Kit tools 🧠 to inspect the file system.

### 🧑‍💻 Navigate to the TSK Directory

```bash
cd "C:\Program Files (x86)\sleuthkit-4.14.0-win32\bin"
```
📸  
![WhatsApp Image 2025-10-26 at 22 56 05_65118f3f](https://github.com/user-attachments/assets/1a5bb3c1-d5e1-4180-8013-8354de89377b)

---

### 🔍 Identify File System Type

```bash
.\fsstat.exe -o 63 "C:\Users\Sai Kumar\Downloads\4Dell Latitude CPi.E01"
```
🧾  
![WhatsApp Image 2025-10-26 at 22 57 05_2472a29b](https://github.com/user-attachments/assets/66b80eaa-1bd8-48bc-b82e-6f601dcfce8b)

💡 *Displays key details about the file system type and structure.*

---

### 🧩 View Partition Layout

```bash
.\mmls.exe "C:\Users\Sai Kumar\Downloads\4Dell Latitude CPi.E01"

```
📊  
![WhatsApp Image 2025-10-26 at 22 57 55_4fd5fb79](https://github.com/user-attachments/assets/0a8fbb53-c1d6-437f-ab40-29e67b3907c4)

➡️ *Lists all partitions and their respective start/end addresses.*

---

### 📂 List Files and Directories

```bash
.\fls.exe -o 63 "C:\Users\Sai Kumar\Downloads\4Dell Latitude CPi.E01"

```
🧾  
![WhatsApp Image 2025-10-26 at 22 58 13_4fca9801](https://github.com/user-attachments/assets/7f1886fc-8cf9-465e-adf6-8272817d4b70)


🔸 *Recursively lists files and folders with their inode details.*

---

### 🗃️ Recover Deleted Files

```bash
.\icat.exe -o 63 "C:\Users\Sai Kumar\Downloads\4Dell Latitude CPi.E01" 119 > "C:\Users\Sai Kumar\Downloads\BOOTLOG_recovered.TXT"
```
🖼️  
![WhatsApp Image 2025-10-26 at 22 58 27_cffedd9f](https://github.com/user-attachments/assets/ea65f7a8-8836-42b6-92ab-12034d04ad10)

💾 *Recovers a deleted or existing file by its inode number.*

---

## 🕰️ **Step 5: Metadata Analysis**

To uncover file history and access details, view the file’s metadata.

```bash
.\istat.exe -o 63 "C:\Users\Sai Kumar\Downloads\4Dell Latitude CPi.E01" 119 > "C:\Users\Sai Kumar\Downloads\BOOTLOG_recovered.TXT" 
```
🧠  
![WhatsApp Image 2025-10-26 at 22 58 58_65998012](https://github.com/user-attachments/assets/48b51664-732c-44ae-98d5-1c27a22069e3)

📘 *Displays file attributes such as MAC times (Modified, Accessed, Changed), size, and allocation info.*

---


## 📜 **Step 6: Report Generation**

After completing your analysis:

1. **Compile All Outputs:**  
   Collect files like `filesystem_info.txt`, `partitions.txt`, `file_list.txt`, and `timeline.txt`.

2. **Interpret and Document:**  
   Write a clear summary 📑 explaining your findings, methods used, and any key recovered evidence.

---

## 🔐 **Step 7: Evidence Preservation**

Ensuring the integrity of evidence is the final and most important step 🧳.

1. **Archive Evidence Securely:**  
   Use encryption 🔒 and hashing 🧮 to store your disk image and findings.

2. **Maintain Chain of Custody:**  
   Keep the evidence in a secure location following proper forensic protocols ⚖️.

---

## ✅ **Conclusion**

Using the **Sleuth Kit (TSK)**, investigators can efficiently extract, analyze, and preserve digital evidence 💾.  
It remains one of the most reliable and open-source forensic toolkits for digital investigation 🚔.
