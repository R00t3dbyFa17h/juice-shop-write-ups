
# 🥤 OWASP Juice Shop Write-ups

![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge&logo=activity)
![Security](https://img.shields.io/badge/Security-Research-blue?style=for-the-badge&logo=kalilinux)
![Platform](https://img.shields.io/badge/Platform-Docker-2496ED?style=for-the-badge&logo=docker)
![Hacker](https://img.shields.io/badge/Hacker-R00t3dbyFa17h-red?style=for-the-badge)

> *"Open my eyes that I may see wonderful things in your law."* > — **Psalm 119:18 (NIV)** >
> **Mission:** Just as the Psalmist seeks deeper understanding of the law, this repository documents my journey to understand the deeper logic of web applications, revealing hidden vulnerabilities to make the digital world safer.

---

## 🕵️‍♂️ About This Project
This repository serves as a documented portfolio of my solutions for **OWASP Juice Shop** — the most modern and sophisticated insecure web application. 

Each folder contains a detailed write-up, including:
* **Reconnaissance:** How the flaw was found.
* **Exploitation:** The specific payloads used.
* **Remediation:** How to fix the code.
* **Biblical Reflection:** Tying technical concepts to spiritual truths.

## ⚡ Quick Start (Docker)
To replicate these findings, spin up the lab using the Docker container:


`docker pull bkimminich/juice-shop`
`docker run --rm -p 3000:3000 bkimminich/juice-shop`

Access the shop at: http://localhost:3000

🏆 Challenge Matrix
ID	Challenge Name	Difficulty	Category	Status	Write-up
01	Score Board	⭐	Misc	✅ Solved	View
02	DOM XSS	⭐	XSS	✅ Solved	View
03	Confidential Document	⭐	Sensitive Data	❌ Pending	...
04	Login Admin	⭐⭐	Injection	❌ Pending	...
05	Error Handling	⭐	Security Misc	❌ Pending	...

(This table will be updated as I progress through the CTF)
⚠️ Disclaimer

All information in this repository is for educational purposes only. The techniques demonstrated here are performed on a locally hosted, intentionally vulnerable application (OWASP Juice Shop).

Do not use these techniques on systems you do not own or do not have explicit permission to test.

Maintained by R00t3dbyFa17h
