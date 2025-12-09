# Bonus: Reflected XSS via Iframe Injection
**Date:** 2025-12-08
**Tool:** OWASP Juice Shop
**Difficulty:** ⭐
**Category:** Cross-Site Scripting (XSS) / HTML Injection

## 📖 Biblical Reflection
> *"Jesus told them another parable: 'The kingdom of heaven is like a man who sowed good seed in his field. But while everyone was sleeping, his enemy came and sowed weeds among the wheat, and went away.'"* — **Matthew 13:24-25 (NIV)**

**Connection:**
In this exploit, the "field" is the legitimate website. The "weeds" are the foreign HTML code (the iframe) that I "sowed" into the application. Just as the weeds grew alongside the wheat, my injected SoundCloud player rendered alongside the legitimate search results because the application failed to filter out foreign seeds (input).

---

## 🎯 The Goal
Demonstrate that the Reflected XSS vulnerability allows for more than just JavaScript execution; it allows for full HTML injection, enabling the embedding of external content (iframes) into the trusted site.

## 🛠️ Methodology

### 1. The Payload
Instead of a standard `<script>` tag, I used an `<iframe>` tag. This tag instructs the browser to load an external URL inside a window within the current page.

**Payload Used:**
```html
<iframe width="100%" height="166" scrolling="no" 
frameborder="no" allow="autoplay" 
src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/771984076&color=%23ff5500&auto_play=true&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe>
```

### 2. Execution
1.  Navigated to the Juice Shop **Search Bar**.
2.  Pasted the iframe HTML code directly into the search field.
3.  Pressed **Enter**.

### 3. The Result
The application reflected the input without sanitization. The browser parsed the `<iframe>` tag and immediately loaded the SoundCloud API.
* **Visual Proof:** A music player appeared inside the search results area and began auto-playing audio.

## ⚠️ Risk Analysis
While a music player seems harmless, this vulnerability (HTML Injection) allows an attacker to:
* **Phishing:** Embed a fake "Login to continue" iframe that sends credentials to the attacker.
* **Defacement:** Cover the legitimate site with offensive content.
* **Malware:** Load a site hosting browser exploits.

## 🛡️ Remediation
* **Context-Aware Encoding:** The application should convert special HTML characters into their safe entities (e.g., `<` becomes `&lt;`).
* **Content Security Policy (CSP):** Implement a CSP header that restricts where iframes can be loaded from (e.g., `frame-src 'self'`). This would block the browser from loading data from `soundcloud.com`.
