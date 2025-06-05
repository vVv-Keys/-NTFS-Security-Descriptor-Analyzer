# NTFS Security Descriptor Analyzer

**Advanced NTFS Forensics Tool** for extracting, parsing, and validating Security Descriptors from the `$SDS` stream of the NTFS `$Secure` metadata file.

---

## 🔍 Features

- Parse `$SDS` entries with full DACL/SACL decoding
- Resolve `SDID` to owner/group SIDs and permissions
- Detect tampered or corrupted `$SDS` entries via hash validation
- Map usage of security descriptors across the `$MFT`
- Output results in JSON, XML, raw hex, or formatted text
- Parallel scanning for large disk images

---

## 📦 Requirements

- Python 3.7+
- [libfsntfs](https://github.com/libyal/libfsntfs)

Install dependencies:
```bash
pip install pyfsntfs
```

---

## 🧪 Usage Examples

### 🔸 Basic Analysis (First 50 `$SDS` Entries):
```bash
python message.txt disk.img --count 50
```

### 🔸 Full Forensic Report with MFT Resolution:
```bash
python message.txt disk.img --full-analysis --output report --format json
```

### 🔸 Extract Specific Security Descriptor ID:
```bash
python message.txt disk.img --security-id 1234 --format raw-hex
```

### 🔸 Parallel Scanning for Performance:
```bash
python message.txt disk.img --parallel --workers 4 --count 200
```

---

## 📁 Output Examples

- JSON: Machine-readable forensic logs
- Text: Analyst-friendly breakdowns
- XML: Structured reporting for external tools
- Raw HEX: For recovery or malware triage workflows

---

## 💡 What Makes It Unique

Unlike other forensic tools that just show SDID values, this tool:
- Fully decodes SID, ACL, ACE entries
- Validates SDS hash integrity
- Matches descriptors to `$MFT` usage
- Works in corrupted or tampered cases

Perfect for:
- Incident response
- Blue team automation
- File system integrity auditing
- NTFS forensics

---

## ⚖ License
This project is open-source under the MIT License.

---

## 📸 Social Preview
![NTFS SDS Flow](A_thumbnail_image_for_the_NTFS_Security_Descriptor.png)

---

> Made with 🔐 by Keys | SkySec
