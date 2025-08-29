#  Ex.No.2    TestDisk: Open-Source Data Recovery Tool

## Aim :
To use TestDisk step by step to recover a missing partition and repair a corrupted one.



## 🛠️ Installation
Linux (Debian/Ubuntu): sudo apt-get install testdisk

macOS (Homebrew): brew install testdisk

Windows: Download the executable from the official CGSecurity website.

## Procedure

### 1. Create a Log File
- Launch TestDisk from your terminal or command prompt using sudo testdisk (or testdisk_win.exe on Windows).

- Select the [Create] option to generate a log file of the recovery session. This is helpful for future reference or troubleshooting.
<br>
<br>
<p align="center">
<img width="1106" height="635" alt="image" src="https://github.com/user-attachments/assets/e8a9203d-b855-436d-93b1-acc965956c93" />

</p>
<br>
<br>

### 2. Select the Drive to Analyze
- TestDisk will display a list of all detected storage devices.

- Use the Up/Down arrow keys to highlight the drive that contains your lost data.

<br>
<br>
<p align="center">
<img width="1098" height="635" alt="image" src="https://github.com/user-attachments/assets/ab73948e-e51b-40e4-8ee7-018213426f0e" />

</p>
<br>
<br>

- Select [Proceed] to move to the next step.

### 3. Choose the Partition Table Type
- TestDisk will automatically suggest the most likely partition table type (e.g., Intel/PC, EFI GPT).

- The default value is usually correct. Confirm the selection by pressing Enter.
<br>
<br>
<p align="center">
<img width="1097" height="644" alt="image" src="https://github.com/user-attachments/assets/3c4156ec-95bc-400e-8bfb-8bfcf0d1955c" />

</p>
<br>
<br>

### 4. Analyze Current Partition Structure
- From the main menu, choose [Analyse] and press Enter.
<br>
<br>
<p align="center">
<img width="1103" height="633" alt="image" src="https://github.com/user-attachments/assets/6533e8ad-c50d-4d0e-85df-ed8d363c0218" />

</p>
<br>
<br>

- This will display the current partition table and check for errors or missing partitions.

### 5. Perform a Quick Search
- After the analysis, you will be prompted to perform a [Quick Search].

<br>
<br>
<p align="center">
<img width="1098" height="637" alt="image" src="https://github.com/user-attachments/assets/c4d01faa-441c-4789-93d7-c8ac5b6ec88b" />
</p>
<br>
<br>

- Select it and press Enter to scan the drive for lost partitions.

- Once a partition is found, you can press p to list its files. Deleted files and folders often appear in red.

- Press q to return to the search results.

  ### 6. Perform a Deeper Search
- If the Quick Search fails to find your lost partitions, select [Deeper Search].

-<br>
<br>
<p align="center"> 
<img width="1099" height="637" alt="image" src="https://github.com/user-attachments/assets/5f7a6814-4f1d-425a-bd40-579ebc1a9671" />

</p>
<br>
<br>

- This process can take a long time, as it scans the entire drive, block by block, to find remnants of partition structures.

- Again, use p to preview files and confirm if a found partition is the one you are looking for.

### 7. Modify Partition Status
- After finding the correct partitions, use the Left/Right arrow keys to set their status.

- Use **Left/Right arrow keys** to change status:  
  - **P**: Primary  
  - ***:** Bootable  
  - **L**: Logical  
  - **D**: Deleted

    <br>
<br>
<p align="center">
<img width="1100" height="638" alt="image" src="https://github.com/user-attachments/assets/bec038c0-7c0d-4e7c-a0a0-84dbeee45bae" />

</p>
<br>
<br>

- Ensure that the partitions you want to recover are marked as Primary or Logical (and not deleted).

### 8. Write the Partition Table
- Once you are confident the partition structure is correct, select [Write] from the menu.

<br>
<br>
<p align="center">
<img width="1089" height="643" alt="image" src="https://github.com/user-attachments/assets/0c163668-bbd8-4220-a926-8255f93e49a0" />

<br>
<br>

- Confirm the operation by pressing y (for yes). This will write the new partition table to your disk.

<br>
<br>
<p align="center">
  <img width="1101" height="637" alt="image" src="https://github.com/user-attachments/assets/bfcaefe2-abce-44ee-b6e6-b9e9fd25bcc4" />

</p>
<br>
<br>


- WARNING: This is a permanent change. Double-check your selections before writing.

### 9. Recover Files
- If you just need to recover a few files without fixing the partition table, you can do so from the file list (after pressing p).

- Navigate to the folder containing your desired files.

- Use the colon : key to select the files you want to recover.

- Press the uppercase C key to copy the selected file(s).

- Navigate to a safe destination on a different storage device and press uppercase C again to paste.

### 10. Exit and Restart
- Once your task is complete, select [Quit] to exit the program.

- If you wrote a new partition table to the drive, it is recommended to restart your computer to allow the operating system to recognize the changes.
