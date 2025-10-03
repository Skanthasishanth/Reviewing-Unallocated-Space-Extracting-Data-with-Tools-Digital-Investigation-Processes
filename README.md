# Reviewing-Unallocated-Space-Extracting-Data-with-Tools-Digital-Investigation-Processes
## AIM:
To review unallocated space in a disk image, extract data using forensic tools, and understand the digital investigation process.
## REQUIREMENTS
- Autopsy or FTK Imager
- Sleuth Kit (TSK)
- Hex Editor (e.g., HxD)
- Operating System: Windows 10/11 or Linux (Kali preferred)
## ARCHITECTURE DIAGRAM

<img width="488" height="778" alt="image" src="https://github.com/user-attachments/assets/c423666f-dc8d-4b5b-97b3-c7dc5ad90b63" />

## DESIGN STEPS:
### Step 1 (Acquire Evidence Image):
- Obtain the disk image in ```.dd``` or ```.E01``` format from a trusted forensic acquisition process.
- Verify hash values (MD5/SHA256) to maintain integrity.

### Step 2(Load Image into Forensic Tool):
- Open Autopsy or FTK Imager.
- Create a new case and add the evidence image.

### Step 3(Locate Unallocated Space):
- Navigate to the partition structure view.
- Identify sectors not assigned to any partition (unallocated).
### Step 4(Analyze & Carve Data):
- Use built-in data carving tools to search for file signatures (JPEG, DOCX, PDF, etc.).
- Preview carved files for relevance.
  
## PROGRAM:
| Step | Action                     | Tool Used                   | Output                       |
| ---- | -------------------------- | --------------------------- | ---------------------------- |
| 1    | Load disk image            | Autopsy / FTK Imager        | Partition & unallocated view |
| 2    | Identify unallocated space | Autopsy File System View    | Sector ranges                |
| 3    | Data carving               | Autopsy Data Carving Module | Recovered files              |
| 4    | Export evidence            | Autopsy Export Option       | File copies for analysis     |


## OUTPUT:

```
lsblk
```

<img width="527" height="157" alt="Screenshot 2025-10-03 082848" src="https://github.com/user-attachments/assets/0db6fdc5-1eca-4942-b213-4545274b5770" />


```
sudo dd if=/dev/sda of=/home/kali/disk.img bs=512
```

<img width="678" height="118" alt="Screenshot 2025-10-03 083115" src="https://github.com/user-attachments/assets/3b855026-eca6-4464-b6f7-d7c0ae8acf40" />


```
mmls ~/disk.img
```

<img width="682" height="173" alt="Screenshot 2025-10-03 083213" src="https://github.com/user-attachments/assets/a0bc11fc-b214-40db-b909-87c8865db0ce" />

```
sudo ls -lh disk.img
```

<img width="511" height="72" alt="Screenshot 2025-10-03 083338" src="https://github.com/user-attachments/assets/2f26c273-65f2-450e-b08e-9117586ad135" />

```
strings disk.img | less
```
<img width="483" height="847" alt="Screenshot 2025-10-03 083422" src="https://github.com/user-attachments/assets/8d3eddf0-4ddc-4886-b908-002ed570a562" />


## RESULT:
The unallocated space was successfully analyzed, data was extracted, and the digital investigation process was followed effectively.

