# Networkwalks B084 — Week 3 Cybersecurity Lab

**Password Cracking, Hash Analysis and Security Tool Integration**

**Intern:** Yusuff Abiola Abdullahi  
**Programme:** Networkwalks Cybersecurity Internship — Batch B084  
**Week:** 3  
**Focus:** Password Security, Ethical Hacking and Security Tool Integration

---

## 1. Project Overview

This repository documents my practical cybersecurity activities during Week 3 of the Networkwalks Cybersecurity Internship.

The project focuses on understanding password protection, extracting password-related data from encrypted PDF files, performing authorised password recovery and exploring cybersecurity tools.

The two compulsory project modules are:

- **PM1:** Password Cracking with John the Ripper (JTR)
- **PM2:** Password Cracking with Networkwalks Tools

Additional practical work includes exploring HexStrike AI integration with Claude Desktop through the Model Context Protocol (MCP).

The exercises are intended for ethical hacking education and authorised security testing.

## 2. Project Objectives

The objectives of this project are to:

1. Understand password cracking and its role in cybersecurity.
2. Explore password recovery techniques using John the Ripper.
3. Extract password-related hashes from protected PDF files.
4. Investigate dictionary-based password attacks.
5. Use Networkwalks browser-based cybersecurity tools.
6. Understand the security risks associated with weak passwords.
7. Explore AI-assisted cybersecurity workflows and tool integration.
8. Develop practical documentation and troubleshooting skills.

## 3. Lab Environment

| Component | Description |
|---|---|
| Host operating system | Windows 11 |
| Virtualisation platform | Oracle VirtualBox |
| Security operating system | Kali Linux |
| Password recovery tool | John the Ripper |
| Graphical interface | Johnny GUI |
| Online hash tool | Networkwalks Hash Calculator |
| Online password recovery | Networkwalks Password Cracker |
| Additional security framework | HexStrike AI |
| AI desktop application | Claude Desktop |
| Integration protocol | Model Context Protocol (MCP) |
| Version control | GitHub |

---

# 4. Project Module 1 — Password Cracking with John the Ripper

## 4.1 Introduction

John the Ripper is a password auditing and recovery tool commonly used by cybersecurity professionals to assess password strength.

It supports multiple password hash formats and can be used in authorised password recovery exercises.

In this module, the objective was to recover the password protecting the provided laboratory file:

`My Locked PDF1.pdf`

The assignment introduces both the command-line version of John the Ripper and its graphical interface, Johnny.

## 4.2 Practical Methodology

The practical workflow involved:

1. Preparing the password-protected PDF file.
2. Identifying the PDF password hash format.
3. Preparing the extracted hash for John the Ripper.
4. Performing password recovery using John the Ripper.
5. Checking the recovered password.
6. Verifying the result against the original PDF.

### Password Recovery Commands

The following commands illustrate the Kali Linux workflow used to extract and test the PDF password hash.

```bash
pdf2john "My Locked PDF1.pdf" > pdf_hash.txt
```

Run John the Ripper:

```bash
john pdf_hash.txt
```

Display recovered credentials:

```bash
john --show pdf_hash.txt
```

## 4.3 Practical Result

The John the Ripper investigation successfully recovered the password of the authorised laboratory PDF.

**Recovered password:**

```text
good-luck
```

The result was confirmed using the following John the Ripper output:

```text
/home/kali/Desktop/My Locked PDF1.pdf:good-luck

1 password hash cracked, 0 left
```

This demonstrates how password auditing tools can recover weak or guessable passwords from protected files.

## 4.4 Security Observations

The exercise demonstrated that:

- Password protection does not guarantee security when weak passwords are used.
- Password recovery tools can identify vulnerable passwords through offline testing.
- Password complexity and unpredictability are important security considerations.
- Hash extraction and password recovery are separate stages of the investigation.
- Recovered passwords should only be used on files and systems where testing is authorised.

---

# 5. Project Module 2 — Password Cracking with Networkwalks Tools

## 5.1 Introduction

Project Module 2 introduces browser-based password auditing tools developed by Networkwalks.

The two tools are:

**Networkwalks Hash Calculator**  
https://networkwalks.com/hash-calculator/

**Networkwalks Password Cracker**  
https://networkwalks.com/password-cracker/

The objective was to extract password-related information from the supplied encrypted PDF and attempt password recovery using the provided online tools.

## 5.2 Practical Methodology

The module follows this process:

### Step 1 — Prepare the Protected PDF

Obtain the authorised laboratory file:

`My Locked PDF1.pdf`

### Step 2 — Extract the PDF Hash

Open the Networkwalks Hash Calculator and select the PDF extraction feature.

Upload the supplied laboratory PDF.

The tool extracts a password-cracking representation beginning with:

```text
$pdf$
```

### Step 3 — Copy the Extracted Hash

Copy the complete hash without omitting characters.

### Step 4 — Open the Password Cracker

Navigate to the Networkwalks Password Cracker.

Paste the extracted hash into the provided input field.

### Step 5 — Perform Dictionary-Based Recovery

Start the password recovery process using the tool's supported dictionary.

Observe the password candidates tested and the result displayed by the tool.

### Step 6 — Verify the Result

Use the recovered password to attempt to open the protected PDF.

Successful access provides confirmation that the password is correct.

## 5.3 Security Observations

This module demonstrates:

- How browser-based tools can support password auditing.
- The role of dictionary attacks in password recovery.
- Why common passwords are vulnerable to guessing attacks.
- The importance of validating recovered passwords.
- Why sensitive or confidential documents should not be uploaded to untrusted online services.

## 5.4 Lessons Learnt

The exercise reinforced the importance of using strong, unique passwords and understanding the limitations of password-based file protection.

It also provided exposure to a different approach to password recovery compared with command-line tools such as John the Ripper.

---

# 6. Additional Practical Work — HexStrike AI and Claude Desktop

## 6.1 Introduction

As an additional cybersecurity learning activity, I explored the integration of HexStrike AI with Claude Desktop through the Model Context Protocol (MCP).

HexStrike AI is a cybersecurity tooling framework designed to support security-related workflows.

MCP provides a standardised approach for connecting AI applications with external tools and services.

## 6.2 Learning Objectives

The objectives of this exploration were to:

- Understand the role of AI-assisted tools in cybersecurity.
- Explore the relationship between an MCP client and server.
- Study how external security tools can be exposed to an AI application.
- Develop familiarity with security tool configuration and troubleshooting.
- Understand the importance of controlling tool permissions and execution scope.

## 6.3 Security Considerations

AI-assisted security tools must be used responsibly.

Important considerations include:

- Restricting security testing to authorised environments.
- Reviewing commands before execution.
- Protecting API keys and configuration secrets.
- Avoiding unnecessary exposure of local files or credentials.
- Monitoring tool activity and validating generated results.

---

# 7. Practical Evidence and Screenshots

Screenshots collected during the Week 3 practical exercises are stored in the repository's `screenshots/` directory.

**Screenshot directory:** [View Week 3 Screenshots](./screenshots/)

The evidence covers the practical activities and tool interfaces used throughout the project.

The screenshots are retained with their original filenames to preserve the uploaded evidence.

---

# 8. Key Security Findings

| Finding | Security implication | Recommendation |
|---|---|---|
| Weak passwords may be recovered | Increased risk of unauthorised file access | Use long, unique passwords |
| Dictionary attacks test predictable passwords | Common passwords are particularly vulnerable | Avoid common words and predictable patterns |
| Protected PDFs can be subjected to offline password guessing | Password protection depends partly on password strength | Use strong passwords and appropriate encryption settings |
| Online password recovery tools process sensitive inputs | Potential confidentiality risks | Use trusted tools and authorised test files |
| AI-connected security tools can execute external operations | Misconfiguration may introduce security risks | Apply least privilege and review tool permissions |

---

# 9. Skills Demonstrated

Through this project, I developed or practised skills in:

- Linux command-line operations
- Password auditing fundamentals
- John the Ripper usage
- PDF password hash extraction
- Dictionary-based password recovery
- Cybersecurity tool configuration
- Troubleshooting security tools
- Understanding password protection mechanisms
- AI-assisted cybersecurity concepts
- Model Context Protocol fundamentals
- Technical documentation
- GitHub repository organisation

---

# 10. Challenges and Troubleshooting

Password recovery exercises can involve several practical challenges, including:

**Hash format compatibility:** Ensuring the extracted password hash is supported by the recovery tool.

**Password recovery sessions:** Understanding that John the Ripper stores previously recovered passwords and may report that no hashes remain to be cracked.

**Tool configuration:** Correctly locating executable files, configuring tool interfaces and preparing inputs.

**Result verification:** Confirming that a reported password actually unlocks the authorised test document.

These challenges reinforced the importance of interpreting command-line output correctly rather than relying solely on whether a tool reports success.

---

# 11. Conclusion

The Week 3 Networkwalks Cybersecurity Internship project provided practical exposure to password auditing, protected PDF analysis and cybersecurity tooling.

Through John the Ripper and the Networkwalks tools, I explored different approaches to password recovery and gained a better understanding of why weak passwords create security risks.

The additional exploration of HexStrike AI, Claude Desktop and MCP introduced concepts relating to AI-assisted security workflows and external tool integration.

Overall, the project strengthened my practical understanding of password security, ethical hacking methodologies, Linux tools and technical documentation.

---

# 12. Ethical Use Disclaimer

All password recovery exercises documented in this repository are intended for educational purposes and authorised laboratory testing.

The techniques demonstrated must not be used to access files, accounts, networks or systems without explicit permission.

---

**Author:** Yusuff Abiola Abdullahi  
**Cybersecurity Student | Network Security & Ethical Hacking**

**Networkwalks Cybersecurity Internship — Batch B084 | Week 3**# networkwalks-B084-week3-cybersecurity-lab
Week 3 Networkwalks Cybersecurity Internship project covering PDF password cracking with John the Ripper, Networkwalks tools, and HexStrike AI integration with Claude Desktop via MCP.
