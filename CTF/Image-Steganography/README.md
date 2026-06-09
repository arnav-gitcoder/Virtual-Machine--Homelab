# Image Steganography Challenge – Magic Byte Recovery & Hidden Flag Extraction

## Overview

This project documents the investigation and solution of a steganography-based Capture The Flag (CTF) challenge.

The challenge involved recovering a corrupted JPEG image whose file signature (magic bytes) had been intentionally modified. After restoring the image header using CyberChef, further analysis revealed hidden data embedded within the image. The concealed file was extracted using Steghide and decoded from Base64 to obtain the final flag.

---

## Objectives

* Identify and repair corrupted file signatures
* Analyze image files using hexadecimal data
* Recover inaccessible JPEG images
* Extract hidden data from images using Steghide
* Decode Base64-encoded information
* Apply digital forensics and steganography techniques

---

## Tools Used

* Kali Linux
* CyberChef
* Steghide
* Base64

---

## Challenge Workflow

```text
Download Corrupted JPEG
       │
       ▼
Hex Analysis (CyberChef)
       │
       ▼
Magic Byte Restoration
       │
       ▼
Recovered JPEG
       │
       ▼
Steghide Extraction
       │
       ▼
Extract flag.txt
       │
       ▼
Base64 Decoding
       │
       ▼
CTF Flag
```

---

## Step 1 – Download the Image

The challenge image was downloaded using:

```bash
wget <image-url>
```

![Image Download](https://github.com/arnav-gitcoder/Virtual-Machine--Homelab/blob/main/CTF/Image-Steganography/Download_Image.png)
---

## Step 2 – Investigate the File

Attempting to open the image produced an error indicating that the file format was not supported.

![Image Error](/Image_Error.png)

This suggested that the file extension did not match the file's internal structure.

---

## Step 3 – Analyze the File Header

The file was uploaded to CyberChef for hexadecimal analysis.

![Cyberchef Analysis](/Codechef_tool.png)

The JPEG header was found to be corrupted.

**Expected JPEG Signature**

```text
FF D8 FF E0
```

**Observed Header**

```text
00 D8 FF E0
```

The first byte had been altered from `FF` to `00`, preventing the file from being recognized as a valid JPEG image.

---

## Step 4 – Restore the Magic Byte

The corrupted byte was manually corrected in CyberChef.

**Before**

```text
00 D8 FF E0
```

**After**

```text
FF D8 FF E0
```

Once repaired, the image could be rendered successfully.

![Recovered Image](/Restored_Image.png)

---

## Step 5 – Extract Hidden Data

After recovering the image, Steghide was used to inspect the file for embedded content.

```bash
steghide extract -sf cat.jpg
```

The extraction process revealed a hidden file named:

```text
flag.txt
```

![Hidden Flag](/steghide_flag.png)

---

## Step 6 – Decode the Hidden Message

The extracted file contained a Base64-encoded string:

```text
Q1RGe3N0ZWcwXzFzX2NvMGx9
```

Decoding the content revealed the challenge flag.

```bash
base64 -d flag.txt
```

---

## Skills Demonstrated

* Digital Forensics
* Steganography Analysis
* Hexadecimal Inspection
* File Signature Identification
* CyberChef Usage
* Steghide Usage
* Base64 Decoding
* Linux Command Line
* CTF Methodology

---

## Key Takeaways

* File extensions alone do not determine file type.
* Magic bytes are essential for file identification.
* A single-byte modification can render a file unreadable.
* Multiple steganographic techniques may be chained together within a single challenge.
* CyberChef and Steghide are valuable tools for forensic investigations and CTF analysis.

---

## Conclusion

This challenge demonstrated a complete steganography investigation workflow involving file signature analysis, image recovery, hidden data extraction, and encoded message decoding. The exercise provided practical experience with commonly used forensic and steganographic tools while reinforcing the importance of understanding file structures and data concealment techniques.
