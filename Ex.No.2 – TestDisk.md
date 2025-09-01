#  Ex.No.2    TestDisk: Open-Source Data Recovery Application

## Aim :
To use TestDisk step by step to recover a missing partition of data and repair a corrupted one.



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
<img width="1106" height="634" alt="image" src="https://github.com/user-attachments/assets/2364d9ca-bfde-4929-94d3-82dd2b0f35a7" />
</p>
<br>
<br>

### 2. Select the Drive to Analyze
- TestDisk will display a list of all detected storage devices.

- Use the Up/Down arrow keys to highlight the drive that contains your lost data.

<br>
<br>
<p align="center">
<img width="1920" height="1080" alt="Screenshot (9)" src="https://github.com/user-attachments/assets/0722030f-2f36-47f9-b969-4fd8633b87e8" />

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
<img width="1096" height="627" alt="image" src="https://github.com/user-attachments/assets/567649d7-7185-4d09-89bc-d93d249e0aa9" />
</p>
<br>
<br>

### 4. Analyze Current Partition Structure
- From the main menu, choose [Analyse] and press Enter.
<br>
<br>
<p align="center">
<img width="1920" height="1080" alt="Screenshot (11)" src="https://github.com/user-attachments/assets/f7ee17e1-d2b5-40bc-a625-36e6c1ec8bca" />


</p>
<br>
<br>

- This will display the current partition table and check for errors or missing partitions.

### 5. Perform a Quick Search
- After the analysis, you will be prompted to perform a [Quick Search].

<br>
<br>
<p align="center">
<img width="1920" height="1080" alt="Screenshot (12)" src="https://github.com/user-attachments/assets/bf0a8d08-ff2a-4bb2-9342-aeed014b7635" />

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
<img width="1920" height="1080" alt="Screenshot (13)" src="https://github.com/user-attachments/assets/bb4e9e7a-b114-4dd3-87dd-3b72cc72c643" />

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
<img width="1920" height="1080" alt="Screenshot (14)" src="https://github.com/user-attachments/assets/61688417-1a76-40e4-8e08-066dca08ca06" />

</p>
<br>
<br>

- Ensure that the partitions you want to recover are marked as Primary or Logical (and not deleted).
### 8.Deeper Search
- Click on the Deep Search option for doinf Deep Search

### 9. Write the Partition Table
- Once you are confident the partition structure is correct, select [Write] from the menu.

<br>
<br>
<p align="center">
<img width="1920" height="1080" alt="Screenshot (15)" src="https://github.com/user-attachments/assets/6256ee57-931d-4b32-a0f3-fcf8311539c0" />

</p>
<br>
<br>

- Confirm the operation by pressing y (for yes). This will write the new partition table to your disk.

<br>
<br>
<p align="center">
  <img width="1920" height="1080" alt="Screenshot (16)" src="https://github.com/user-attachments/assets/f5bb088d-e2e2-42c1-8c7c-451a70c2b421" />

</p>
<br>
<br>


- WARNING: This is a permanent change. Double-check your selections before writing.

### 10. Recover Files
- If you just need to recover a few files without fixing the partition table, you can do so from the file list (after pressing p).

- Navigate to the folder containing your desired files.

- Use the colon : key to select the files you want to recover.

- Press the uppercase C key to copy the selected file(s).

- Navigate to a safe destination on a different storage device and press uppercase C again to paste.

### 11. Exit and Restart
- Once your task is complete, select [Quit] to exit the program.

- If you wrote a new partition table to the drive, it is recommended to restart your computer to allow the operating system to recognize the changes.
