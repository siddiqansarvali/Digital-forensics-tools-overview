# Ex.No.1    FTK Imager: A Forensic Imaging Tool Overview

## Acquiring Volatile Memory 
<br>


### Steps to Capture RAM Using FTK Imager Application
<br>

### 1. Run as Administrator in your Device
- Open **FTK Imager** and run it as Adminstrator.  
- Right-click the FTK Imager icon and select **Run as administrator**.
<br>
<br>


 <img width="1575" height="763" alt="image" src="https://github.com/user-attachments/assets/739f9871-3976-41c3-be50-b8a8da805b63" />
<br>
<br>

### 2. Initiate Memory Capture
- In the top menu bar, click **File → Capture Memory...** from the dropdown list.
  <br>
<br>

   <img/>
<br>
<br>

### 3. Configure Destination
A dialog box will appear where you configure where and how the memory will be saved.

- **Destination Path:**  
  Click **Browse** to select a folder on an **external drive** (not the system drive).  

- **Destination Filename:**  
  You can keep the default `memdump.mem` or assign a more descriptive name.

- **Optional: Include pagefile.sys**  
  Check this box to capture `pagefile.sys`, which is virtual memory stored on the disk.  
  > Note: This may increase capture size and duration, but can contain valuable artifacts.

- **Optional: Create AD1 file**  
  Saves the memory dump in an AccessData-specific container file.  
  > Generally not necessary if using tools like **Volatility** for analysis.



<br>
<br>

 <img width="1920" height="1080" alt="Screenshot (5)" src="https://github.com/user-attachments/assets/e5750a26-ba08-4f60-ba36-5d9b66b4ddff" />
 

 
<br>
<br>

### 4. Start Capture
- Click the Capture Memory button to begin acquisition.
<br>
<br>


<img width="1920" height="1080" alt="Screenshot (6)" src="https://github.com/user-attachments/assets/7823c21b-3d5e-4f50-9a9e-a5979a598772" />

<br>
<br>

### 5. Wait for Completion
- A progress bar will indicate the capture status.  
- Capture time depends on the system’s RAM size.  
- Once finished, the memory dump file will be available in the destination folder.
---
<br>
<br>

## Acquiring Non-Volatile Memory (Disk Image) Using FTK Imager


### 1. Start the Process
- In FTK Imager, go to the top menu bar: **File → Create Disk Image...**.

<br>
<br>
<img width="1920" height="1080" alt="Screenshot (8)" src="https://github.com/user-attachments/assets/56ad0ec6-f6cb-49e3-9fbc-863f050139d1" />


<br>
<br>

### 2. Select Source Evidence Type
A window will appear asking you to choose the source type:

- **Physical Drive:** Images the entire disk, including all partitions, unallocated space, and the Master Boot Record (MBR).  
- **Logical Drive:** Images a specific partition (e.g., C: drive).  
- **Image File:** Converts or copies an existing image file.  
- **Contents of a Folder:** Creates an image of a specific folder only.  

> **Tip:** For full forensic imaging, select **Physical Drive**.
<br>
<br>
<p align="center">

<img width="640" height="512" alt="Screenshot 2025-09-01 203953" src="https://github.com/user-attachments/assets/80625d36-5231-41d6-be75-e2b67c4665fa" />

</p>
<br>
<br>

### 3. Select the Source Drive
- From the dropdown, choose the physical drive to image (connected via **write-blocker**).  
- Click **Finish**.
 <br>
<br>
<p align="center">
<img width="633" height="472" alt="ftk1" src="https://github.com/user-attachments/assets/86b2f0a2-ba75-4566-8e07-81d529d26219" />

</p>
<br>
<br>

### 4. Configure the Image Destination
- Click **Add...** in the "Create Image" window to define the image **format** and **destination**.
  <br>
<br>
<p align="center">
<img width="553" height="567" alt="ftk2" src="https://github.com/user-attachments/assets/9621ce6c-e766-4114-908d-086e4153a048" />

<br>

#### Options:

- **Image Type:**  
  - **E01 (EnCase Format):** Recommended; includes compression, metadata, and error-checking.  
  - **Raw (DD):** Bit-for-bit copy with no extra features.
<br>
<br>
<p align="center">
<img width="505" height="405" alt="image" src="https://github.com/user-attachments/assets/e5d806b5-edda-4f57-a60b-e4c58b8fd343" />
</p>
<br>
<br>

- **Fill in Evidence Item Information:**  
  - Enter case details, examiner name, and description.  
  - This information is stored in the image metadata (important for documentation).
 <p align="center">
<img width="550" height="536" alt="ftk3" src="https://github.com/user-attachments/assets/a0e074da-bb69-4241-9e87-5c4d31f5af79" />

</p>
<br>
<br>

- **Choose Destination Folder:**  
  - Must be a different drive from the source.  
  - Name the image file (e.g., `Case001_SuspectHDD`).  

- **Image Fragment Size:**  
  - Set a value to split the image into multiple parts.  
  - Set to `0` for a single image file.
  <br>
  <br>
  
<p align="center">
<img width="617" height="593" alt="ftk4" src="https://github.com/user-attachments/assets/2db24fbc-4dcc-4c9d-8826-64ee8ea34ce1" />

</p>
<br>
<br>


### 5. Start the Imaging Process
- Click **Finish** to return to the "Create Image" screen.  
- **Check "Verify images after they are created"** to calculate hash values and ensure integrity.  
- Click **Start**.
  <br>
  <br>
  <p align="center">
  <img width="300"  alt="image" src="https://github.com/user-attachments/assets/739045f1-11bc-474a-9343-2e9aa19ec376" />
  <img width="300"alt="image" src="https://github.com/user-attachments/assets/7bef2114-0017-4a7b-9e19-0f356c3e3236" />
</p>
<br>
<br>

### 6. Completion and Hash Verification
- The imaging process may take time depending on the drive size.  
- After completion, FTK Imager verifies the hashes automatically.  
- A final window shows **MD5** and **SHA1** hashes for both the source drive and image.  
- Matching hashes values with the imager

---
## Notes

- Always use a **write-blocker** to prevent modifications to the evidence.  
- **Hash verification** is critical to maintain a chain of custody and admissibility in court.  
- **Image Fragmentation** is useful for large drives or storage limitations.
---

## References

- [FTK Imager Official Website](https://accessdata.com/product-download/ftk-imager-version-4-5)  
- FTK Imager Documentation

