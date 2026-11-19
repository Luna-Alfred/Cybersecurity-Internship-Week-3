# Cybersecurity Internship – Week 3
## Password Cracking and Password Security Assessment

## Project Overview

Week 3 focused on password security assessment through two practical exercises involving password recovery from protected PDF documents.

The exercises explored two different approaches:

- **Module 1:** Password Cracking with John the Ripper (JTR).
- **Module 2:** Password Cracking with Networkwalks Tools.

The activities provided hands-on experience with PDF hash extraction, dictionary-based password attacks, browser-based password-cracking tools, and password verification.

## Objectives

- Understand how password-protected PDF documents can be assessed.
- Learn how to extract password hashes from PDF files.
- Practice password recovery using John the Ripper.
- Understand dictionary-based password attacks.
- Explore browser-based password-cracking tools.
- Compare different password-recovery approaches.
- Understand the importance of strong passwords.

## Tools and Technologies

| Module 1 – John the Ripper | Module 2 – Networkwalks |
|---|---|
| Kali Linux | Windows Web Browser |
| John the Ripper | Networkwalks Hash Calculator |
| pdf2john | Networkwalks Password Cracker |
| RockYou Wordlist | Kali Linux Web Browser |
| Terminal | Protected PDF Sample |

---

## Module 1: Password Cracking with John the Ripper

### Methodology

**1. Environment Preparation**

- Used Kali Linux as the testing environment.
- Checked the installed John the Ripper version.
- Located the `pdf2john` utility.

**2. Wordlist Preparation**

The RockYou wordlist was initially compressed and was decompressed using:

```bash
sudo gzip -d /usr/share/wordlists/rockyou.txt.gz
```

**3. PDF Hash Extraction**

Three protected PDF samples were processed using `pdf2john`.

```bash
pdf2john "My-Locked-PDF1.pdf" > hash.txt
pdf2john "My-Locked-PDF2.pdf" > hash2.txt
pdf2john "My-locked-PDF3.pdf" > hash3.txt
```

**4. Password Cracking**

John the Ripper was executed against the extracted hashes using the RockYou wordlist.

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
john --wordlist=/usr/share/wordlists/rockyou.txt hash2.txt
john --wordlist=/usr/share/wordlists/rockyou.txt hash3.txt
```

**5. Verification**

The recovered password for the third PDF was also checked using:

```bash
john --show --format=PDF hash3.txt
```

All three recovered passwords were tested by opening their respective PDF documents.

### Results

| PDF Sample | Result |
|---|---|
| My-Locked-PDF1.pdf | Password recovered |
| My-Locked-PDF2.pdf | Password recovered |
| My-locked-PDF3.pdf | Password recovered |

All three PDF documents were successfully unlocked.

---

## Module 2: Password Cracking with Networkwalks Tools

### Methodology

**1. PDF Hash Extraction**

- Opened the Networkwalks Hash Calculator.
- Selected the PDF option.
- Uploaded `My-Locked-PDF1.pdf`.
- Extracted the PDF-specific hash beginning with `$pdf$`.
- Compared the results from Windows and Kali Linux browsers.

Both browsers generated identical hashes.

**2. Password Cracking**

- Opened the Networkwalks Password Cracker.
- Submitted the extracted PDF hash.
- Initiated the password-cracking process.
- Waited for the tool to recover the password.

**3. Password Verification**

The tool successfully recovered the password. It was entered into the protected PDF, and the document opened successfully.

### Result

- Hash extraction: Successful.
- Password-cracking process: Successful.
- Password recovery: Successful.
- PDF unlocking and verification: Successful.

---

## Comparison of Both Modules

| Feature | Module 1 | Module 2 |
|---|---|---|
| Password-cracking tool | John the Ripper | Networkwalks Password Cracker |
| Hash extraction | pdf2john | Networkwalks Hash Calculator |
| Password candidates | RockYou wordlist | Networkwalks tool |
| Environment | Kali Linux | Web browsers |
| PDF samples | Three | One |
| Outcome | Successful | Successful |

Both methods successfully recovered the password of the first PDF sample.

## Challenges and Troubleshooting

1. **Compressed wordlist:** The RockYou wordlist was initially compressed. I resolved this by decompressing it using the `gzip` command.
2. **PDF hash extraction:** I used `pdf2john` to extract the required hashes and saved them in separate text files.
3. **Hash calculator selection:** The ordinary file mode generated standard file checksums. I selected PDF mode to extract the required `$pdf$` hash.
4. **Cross-browser verification:** I compared the hash generated in Windows and Kali Linux and confirmed that both results matched.

## Key Learning Outcomes

Through these exercises, I gained practical experience in:

- PDF password-hash extraction.
- Using `pdf2john` to prepare PDF hashes for auditing.
- Using John the Ripper with a dictionary wordlist.
- Understanding dictionary-based password attacks.
- Using browser-based password-cracking tools.
- Distinguishing ordinary file checksums from PDF password hashes.
- Understanding the difference between hash extraction and password cracking.
- Verifying recovered passwords against protected documents.
- Recognising the importance of strong and unpredictable passwords.

## Evidence and Screenshots

Screenshots documenting the practical exercises are organised into separate module folders.

### Module 1 – John the Ripper

- John the Ripper version.
- RockYou wordlist preparation.
- PDF hash extraction.
- Password-cracking commands and results.
- Successful PDF unlocking.

### Module 2 – Networkwalks Tools

- Networkwalks Hash Calculator.
- Extracted PDF hash.
- Networkwalks Password Cracker.
- Successful password recovery.
- Successfully unlocked PDF.

## Conclusion

Week 3 provided practical exposure to password security assessment through two different password-recovery approaches.

Module 1 demonstrated password recovery using John the Ripper, pdf2john and the RockYou wordlist in Kali Linux.

Module 2 demonstrated PDF hash extraction and password recovery using Networkwalks' browser-based tools.

Both exercises were completed successfully, strengthening my understanding of password security, hash extraction, dictionary attacks and the use of cybersecurity tools during authorised security assessments.

**Project Status:** Both practical modules completed successfully.

*All exercises were conducted using sample PDF files provided for cybersecurity training purposes.*
