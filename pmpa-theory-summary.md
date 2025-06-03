# 🧠 PMPA Theory Summary

It's just the theory, y'all. 

🧠 PMPA Theory Summary

## 🎯 Purpose

This document summarises core concepts from my ongoing study of the **Practical Mobile Pentester Associate (PMPA)** certification. The goal is to reinforce theoretical knowledge while building a foundation for applied testing in a controlled lab environment.

I'm pairing this with hands-on work in mobile forensics, Wi-Fi exploitation, and SDR signal analysis.

The ongoing means I haven't finished yet, but I am getting there. 
---

## 📚 Topics Covered So Far

### 🔍 Mobile App Architecture
- APK structure: `AndroidManifest.xml`, `classes.dex`, and resources
- Permissions and intents
- Activities, services, content providers

### 🧪 Static Analysis (Ongoing)
- Tools: `JADX`, `MobSF`, `apktool`
- Reading decompiled code to locate:
  - Hardcoded secrets
  - Insecure configurations
  - Broken auth logic

### 🌀 Dynamic Analysis (Ongoing)
- Proxying traffic through `Burp Suite`
- Certificate pinning bypass techniques
- Frida + Objection for runtime analysis

### 🔐 API and Token Security (Ongoing)
- Understanding `JWT` and token-based auth
- Enumerating insecure endpoints
- Session fixation and token leakage

### 📱 Android Device Exploitation (Ongoing) 
- ADB basics: shell access, logcat, sideloading
- APK signing and repacking
- Local data extraction (SQLite, shared prefs)

---

## 🧠 Mind Map

![PMPA Mind Map](../screenshots/pmpa_mindmap.png)

*Visual summary of PMPA topics — updated as learning continues.*

---

## 🔄 What I’m Working On Next

- Deeper Frida scripting
- Custom payload testing in Burp Repeater
- Writing Python tools to automate APK scanning
- Connecting theory to real-world examples from LE/intel perspective

---

## 📓 Takeaways

- Static analysis gives an early look, but dynamic testing reveals the real issues.
- Many mobile apps fail on basic API protection, even those used by major brands.
- Android’s openness makes it ideal for learning, but also a huge attack surface. But then again, if iOS is exploited, it pretty much means they can all be exploited so..... a little from column A and a little from column B.
- Linking teleco metadata and mobile behaviour is an underrated skillset in threat hunting.

---

## ⚠️ Disclaimer

These notes reflect personal study and learning in a safe lab setting. All testing is ethical and does not involve any unauthorised access to systems or data. Just behave yourself.

---


---

## ⚠️ Disclaimer

These notes reflect personal study and learning in a safe lab setting. All testing is ethical and does not involve any unauthorised access to systems or data.

---

