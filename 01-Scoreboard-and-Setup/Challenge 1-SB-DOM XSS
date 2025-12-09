# Challenge 1: Finding the Score Board & DOM XSS
**Date:** 2025-12-08
**Tool:** OWASP Juice Shop (Docker)
**Difficulty:** ⭐

## 📖 Biblical Reflection
> *"It is the glory of God to conceal a matter; to search out a matter is the glory of kings."* — **Proverbs 25:2 (NIV)**

**Connection:**
The Juice Shop "conceals" its vulnerabilities and its Score Board behind the facade of a normal store. It was my job to "search out" the hidden logic to reveal the challenges.

---

## 🎯 The Goal
Locate the hidden "Score Board" page which tracks progress for the CTF, and perform a DOM-based XSS attack.

## 🛠️ Methodology

### 1. Discovery (finding the Score Board)
I inspected the source code (`main-es20XX.js`) and searched for the string "score". I found a defined path for the scoreboard.
* **Hidden URL:** `http://localhost:3000/#/score-board`

### 2. The Vulnerability (DOM XSS)
The search bar takes user input and renders it directly to the page without sanitization.
* **Payload Used:** `<iframe src="javascript:alert('xss')">`

### 3. Execution
1. Navigated to the Search Bar.
2. Pasted the payload.
3. Hit Enter.
4. **Result:** An alert box appeared, and the challenge was marked as solved on the Score Board.

## 🛡️ Mitigation
To fix this, the developers should implement **Input Sanitization** (stripping dangerous characters like `<` and `>`) or use **Output Encoding** (converting `<` to `&lt;`) so the browser interprets the input as text, not code.
