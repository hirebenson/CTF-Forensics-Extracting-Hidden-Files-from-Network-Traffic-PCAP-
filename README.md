# CTF-Forensics-Extracting-Hidden-Files-from-Network-Traffic-PCAP-
This Capture The Flag (CTF) forensic lab guides students through the manual extraction of files transmitted via HTTP traffic in a captured network session (bns_captured_activity.pcap). Without using code or automation, students will use only Wireshark and HxD Hex Editor to uncover hidden files embedded within HTTP packets.

Learning Objectives:
- Open and inspect HTTP streams using Wireshark
- Follow TCP streams and identify transferred files
- Recognize file signatures using hex (magic numbers)
- Reconstruct `.jpg`, `.png`, `.pdf`, and `.zip` files manually
- Document findings in a forensic report

Tools Required:
- Wireshark – for following TCP/HTTP streams
- HxD Hex Editor – for carving and saving binary data

Why This Lab Matters:
This lab teaches students how to manually inspect and extract files from HTTP traffic, a skill vital in situations like:
- Investigating data leaks or unauthorized file transfers
- Reconstructing digital evidence for legal or compliance cases
- Analyzing malware delivery through web traffic
- Participating in CTF competitions and threat hunting exercises

Files to Extract:
Your goal is to find and recover the following:
- JPG image (BNS01.jpg)
- PNG image (BNS02.png)
- PDF file  (BNS03.pdf)
- ZIP file  (BNS04.zip)

Tips for Extraction
- Use Wireshark filter: http , http.request.method == "POST", http.request.method == "GET", 
- Right-click a packet and choose Follow → TCP Stream
- Look for content that starts with file signatures like:
  - JPG: `FF D8 FF`
  - PNG: `89 50 4E 47`
  - PDF: `25 50 44 46`
  - ZIP: `50 4B 03 04` 
- Copy the raw file and paste it into HxD
- save as the correct file extension i.e if it is a png file, save as example.png

 
