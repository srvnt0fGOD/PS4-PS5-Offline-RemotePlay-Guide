# PS4-PS5-Offline-RemotePlay-Connect
*Activating PS4/PS5 Local account (without PSN) with Apollo/OffAct*
*Connecting Chiaki and Chiaki-ng without PSN*
*Also included official activation with Apollo/OffAct*

**⚠️ DISCLAIMER:** This guide is for educational and informational purpose only. Console modification may violate Sony's ToS, void warranties, and risk bans/data loss. You assume all risks. Always back up data. Use at your own discretion; the author provides no warranties.

## PS4-PS5 Remote Play Guide (Unofficial)

**READ THIS FIRST:** Make sure to create a backup for your games/apps save file. This guide documents methods that **have worked for some users on specific setups**, but **success is NOT guaranteed**. These methods bypass Sony's official activation process.

## **Success Rate Factors:**
- **Firmware Version:** Older firmwares work better
- **Jailbreak Version:** Use latest compatible jailbreak
- **Network Configuration:** Static IP and proper port forwarding help

---

## Table of Contents
- [Prerequisites](#prerequisites)
- [Success Rate by Console](#success-rate-by-console)
- [Method 1: PS4/PS5 Offline Activation with Apollo/OffAct](#method-1-ps4ps5-offline-activation-with-apollooffact)
- [Method 2: PS4/PS5 Official Activation with Apollo/OffAct](#method-2-ps4ps5-official-activation-with-apollooffact)
- [Method 3: Alternative Approaches](#method-3-alternative-approaches)
- [ID Conversion Guide](#id-conversion-guide)
- [App Configuration](#app-configuration)
- [Troubleshooting and Community](#troubleshooting-and-community)
- [Additional Resources](#additional-resources)
- [IMPORTANT SAFETY AND BACKUP WARNING](#important-safety-and-backup-warning)

---

## Prerequisites

### **For Both PS4 & PS5:**
1. **Jailbroken console** with latest exploit
2. **Static IP Address** for your console (set via router DHCP reservation "optional")
3. **Remote Play turned OFF before running jailbreak**
4. **USB drive** for file transfers
5. **Technical patience** - be prepared for trial and error

### **Network Requirements:**
- **Ethernet recommended** for best performance
- **5GHz WiFi** for 1080p/60fps streaming
- **2.4GHz WiFi** use 720p/30fps for stable connection
- **PS4 Fat/Slim** maximum Remote Play resolution: 720p
- **Port forwarding may help** (TCP 9295, UDP 9296-9297, TCP or UDP 9295-9297)

---

## Success Rate by Console

### **PS4 Firmware 9.00 or Lower:**
- **Remote play connection:** high success rate
- **Best method:** GoldHEN latest version

### **PS5 Any Firmware:**
- **Status:** Experimental, YMMV (Your Mileage May Vary)

---

## Method 1: PS4/PS5 Offline Activation with Apollo/OffAct

### **PS4 Instructions:**
1. **Download Apollo Save Tool:**
 - [GitHub Repository](https://github.com/bucanero/apollo-ps4)
 - Install via USB or network

2. **Attempt Activation:**
 ```
 Apollo → User Activation → Activate User
 ```
 - Note down your **16-digit hexadecimal ID**

3. **Enable Remote Play:**
 - Remote Play **OFF** → Run jailbreak → Remote Play **ON** *to avoid crash*
   
---

### **PS5 Instructions:**
1. **Prepare Files:**
 - Download from [PS5 Payload Repository](https://github.com/ps5-payload-dev/websrv/releases)
 - `homebrewloader.pkg`
 - `OffAct.zip`

2. **Installation:**
 ```bash
 USB Root:
 ├── homebrewloader.pkg
 └── homebrew/
     └── OffAct/ (extracted files from OffAct.zip)
 ```

---

### **Transfer Methods:**

#### **Method A (PS5-Xplorer):**
- Launch `Ps5-Xplorer`
- Copy `homebrew` folder `/homebrew/OffAct/` to `/data/` directory
- Install `homebrewloader.pkg` via Package Installer

#### **Method B (FTP):**
- **Note:** If using old jailbreak, `run john-tornblom elfldr` after jailbreak
- Use FTP server to transfer `/homebrew/OffAct/` to `/data/`  directory

 1. **Activation Attempt:**
  - Install homebrewloader.pkg
  - Launch `HomebrewLoader`
  - Press `X` to select `OfflineActivator (OffAct)`
  - Press `O` to close dialog
  - When the Offline Account list appears, Select your local offline account.
  - Press `X` on your local account to generate a random 16-digit ID
  - **Note this ID down for later use**
  - Select done to activate your offline account and Reboot
  - **Back to PC**
  - Download payload injector [NetCat GUI](https://www.sendspace.com/file/5rz4lg)
  - Open `NetCat GUI`  and enter PS5 `ip address` in host box, (port 9021)
  - Download Remote play payload [rp-get-pin.elf](https://github.com/idlesauce/ps5-remoteplay-get-pin/releases)
  - Browse or drag it inside `NetCat GUI` and select "Inject Payload".
  - You will receive a notification on the PS5 after injecting Payload.
  - An 8-digit PIN code and Encoded ID `(Base64-encoded 8-byte (64-bit) Little-Endian ID)` notification will popup .
  - **Note:** Must be in exploit environment before injecting rp-get-pin.elf

  - or you can also directly retrieve your Encoded ID with Python by typing the command with your 16-digit ID `(Hexadecimal)` from activated ID
  - or 19-digit ID `(Decimal)` from ID grabber with (official account) mentioned below at ID Conversion Guide:

---

## Method 2: PS4/PS5 Official Activation with Apollo/OffAct

### **Official Activation Method for PS4/PS5**

1. **PSN Registration:**
 - Create new PSN account
 - Set up your username

2. **Find and Retrieve Your ID:**
 - Enter PSN username into [PSN ID Grabber](https://psn.flipscreen.games)
 - **Encoded ID:** Encoded ID `(Base64-encoded 8-byte (64-bit) Little-Endian ID)` (for Chiaki-ng/Chiaki) from PSN ID grabber
 - **Official Account ID:** `(19-digit Decimal)`(for PSPlay – paid)
 - **Alternative:** Use PlayStation official app to find account ID

3. **Convert IDs:**
 - Activating the Local Account of PS4/PS5 with Official PSN retrieved from ID graber
 - Enter Official 19-digit ID into the [Decimal to HEX Converter](https://www.rapidtables.com/convert/number/decimal-to-hex.html) to get your **16-digit Hex ID**.
 - While activating local account using Apollo/OffAct on your PS4/PS5
 - Replace "random" User ID with your official **16-digit Hex ID** from converter.
 - Select **Done** and **Reboot** to apply changes.
 - You can also convert Decimal to Hex with Python, Mentioned Below at ID Conversion Guide: 

---

## Method 3: Alternative Approaches

<details>
<summary><strong>👉Click to read Alternative Approaches</strong></summary>

### **If Methods 1-3 Fail:**

#### **1. Local Game Streaming (Reliable Alternative):**
 - **Moonlight + Sunshine:** Stream from gaming PC
 - **Steam Link:** Stream Steam games
 - **Parsec:** Low-latency desktop streaming

#### **2. Paid Alternative:**
 - **PSPlay (Paid):** More lenient with activation
 - **Repl4y:** Another third-party app
</details>

---

## ID Conversion Guide 

### **Required Software:**
- **Python latest Version**
- [Official Site](https://www.python.org/downloads/)
- Microsoft Store (Windows)

### **Convert Activated Official or Offline Account from PS4/PS5 for Remote Play**
### Chiaki-ng/Chiaki need Encoded ID (Base64-encoded 8-byte (64-bit) Little-Endian ID)

### Conversion Methods for Chiaki-ng/Chiaki:
#### **Convert PS4/PS5 Activated User Account Hexadecimal (16-digit) to Base64 Encoded ID for Chiaki-ng/Chiaki**
`Python`
```python
import base64
activated_id = "your-16digit-offline-Id"
print(base64.b64encode(int(activated_id, 16).to_bytes(8, 'little')).decode())
```
**Example:**
```python
>>> import base64
... activated_id = "1234567890ABCDEF"
... print(base64.b64encode(int(activated_id, 16).to_bytes(8, 'little')).decode())
...
782rkHhWNBI=
```
add `782rkHhWNBI=` in chiaki-ng/Chiaki encoded ID for connecting remote play

---

### **For PSPlay (Paid) need 19-digit ID**

#### 1. Convert PS4/PS5 Activated User Account Hexadecimal (16-digit) to Decimal (19-digit) for PSPlay
- Use [Hex to Decimal Converter](https://www.rapidtables.com/convert/number/hex-to-decimal.html):
- Or use `Python` to convert Hex to Decimal
```python
hex_id = "1234567890ABCDEF"  # Your 16-digit hex ID
decimal_id = int(hex_id, 16)
print(f"19-digit Decimal ID: {decimal_id}")
```
**Example:**
```python
>>> hex_id = "1234567890ABCDEF"
... decimal_id = int(hex_id, 16)
... print(f"19-digit Decimal ID: {decimal_id}")
...
19-digit Decimal ID: 1311768467294899695 
```

---

### BONUS: Additional Conversions

#### 1. **Convert Decimal (19-digit) to Base64 Encoded ID for Chiaki-ng/Chiaki**
 - Retrieve Decimal (19-digit) Official PSN ID from [PSN ID Grabber](https://psn.flipscreen.games) 

`Python`
```python
import base64
decimal_id = 1311768467294899695 # Your 19-digit decimal ID
print(base64.b64encode(decimal_id.to_bytes(8, 'little')).decode())
```
**Example:**
```python
>>> import base64
... decimal_id = 1311768467294899695
... print(base64.b64encode(decimal_id.to_bytes(8, 'little')).decode())
...
782rkHhWNBI=
```

#### 2. **Convert Decimal (19-digit) to Hexadecimal (16-digit) from Python or Decimal to Hex converter**
 - After activating PS4/PS5 with Apollo/OffAct retrieved Decimal (19-digit) from [PSN ID Grabber](https://psn.flipscreen.games) with your official PSN account
 - Use this [Decimal to Hex Converter](https://www.rapidtables.com/convert/number/hex-to-decimal.html) OR Python:
`python`
```python
decimal_id = 1311768467294899695
hex_id = f'"{decimal_id:016X}"'
print(f"16-digit Hex ID: {hex_id}")
```
**Example:**
```python
>>> decimal_id = 1311768467294899695
... hex_id = f'"{decimal_id:016X}"'
... print(f"16-digit Hex ID: {hex_id}")
...
16-digit Hex ID: "1234567890ABCDEF"
```

---

## App Configuration

### **Chiaki-ng/Chiaki Setup:**
- **Download:** [chiaki-ng](https://github.com/streetpea/chiaki-ng) `or`
- [Chiaki](https://github.com/thestr4ng3r/chiaki)  
- Settings if Activation WORKED:
- **Host:** Console IP (e.g., `192.168.1.50`)
- **AccountID:** Encoded ID (obtained from Python conversion)
- **Remote Play PIN:** 8-digit from PS4/PS5
- **Console PIN [Optional]:** 4-digit PSN profile login passcode (Default: 0000)
- **PS4:** Select 8.0+ (compatible with 9.00+)
- **PS5:** Select PS5

**If Remote Play Connection FAILED**
- Activate PS4/PS5 with Apollo/OffAct using following IDs rather than the generated random ID: 
 - Try: "123456789ABCDEF0"
 - Try: "0000000000000000"
 - Try: "ffffffffffffffff"
 - Try: "DEADBEEFCAFEBABE"

### **PSPlay (Paid) Setup:**
**Downlaod:** [PSPlay Repository](https://github.com/streamingdv/PSPlay-Application-Hosting)
**Manual Registration:**
- Uncheck "automatic connection"
- Advanced → Register manually
- Enter: Console IP + 19-digit Decimal ID
- Enter: 8-digit PIN

### **Performance Settings:**
- **Ethernet:** 1080p @ 60fps
- **5GHz WiFi:** 1080p @ 60fps
- **2.4GHz WiFi:** 720p @ 30fps
- **PS4 Fat/Slim:** Maximum 720p

---

## Troubleshooting and Community

### **Common Issues & Solutions:**

#### **Issue 1: Activation succeeds but can't connect**
- Check firewall settings
- Verify static IP assignment
- Try different port settings
- Test with phone hotspot (isolate network issues)

#### **Issue 2: Intermittent Connections**
- Typical for unofficial methods
- Keep Remote Play disabled until ready to stream
- Jailbreak patches interfering
- Re-run jailbreak before each session

---

### **Diagnostic Checklist:**
- [ ] Remote Play shows in Settings (without jailbreak)
- [ ] Valid 16-digit hex ID obtained
- [ ] Static IP configured correctly
- [ ] Ports forwarded (if behind NAT)
- [ ] Trying multiple Chiaki/PSPlay versions

---

### Community & Support

#### **Where to Get Help:**
 - **Reddit:** r/ps4homebrew, r/ps5homebrew
 - **Discord:** Modded Warfare, PSX-Place
 - **Forums:** PSX-Place.com, GBAtemp.net

#### **When Asking for Help, Include:**
Include in your help request:
 1. Console model and firmware
 2. Jailbreak method used
 3. Specific error messages
 4. What you've already tried

---

## Additional Resources

### **Video Tutorials:**
- [Modded Warfare YouTube](https://www.youtube.com/@MODDEDWARFARE)

### **Community Discussions:**
- [PSX-Place Remote Play Thread](https://www.psx-place.com/threads/remote-play-on-jailbroken-consoles.XXXXX/)

### **Tools & Utilities:**
- **GoldHEN Cheat Manager:** Includes system patches
- **Al-Azif DNS:** For older firmware jailbreaks

---

### Final Reality Check

#### **If It Works:**
 - Document your exact setup
 - Share with community
 - **Don't update firmware!**
 - Stick to `9.00` firmware

#### **If It Doesn't Work:**
 - You're not alone - many face this
 - Consider official Remote Play (requires PSN)
 - Look into PC game streaming alternatives
 - Wait for better exploits/methods

---

**Repository Value:** This guide serves as a comprehensive collection of unofficial/official Remote Play on jailbroken consoles. It provides realistic expectations while offering multiple approaches for different scenarios.

---

## IMPORTANT SAFETY AND BACKUP WARNING

### **READ BEFORE PROCEEDING:**

- **Remember:** before installing games, apps, patches, modifying system files etc... always **back up** your data, In jailbreak exploits, Errors can corrupt your data or cause save files from all **user accounts** to disappear.

- Always be cautious and believe me I know how it feels when you're playing a game, already completed 5%/7% and because of you, all **user accounts** saves also disappear and you need to make excuses when explaining to other users that because of power outage (not a lie, power outage common here) all our data wiped out from the directory and yeah you cant recover disappeared data. You can recover your corrupt data with Itemzflow/Apollo.

- Jokes aside, Last but not least, if possible, Support the developers and creators of the tools mentioned in this guide.

- The entire jailbreak community thrives on developer contributions. Consider donating or supporting their work when you can
Jailbreak scene evolves constantly. What doesn't work today might work tomorrow with new exploits or patches. Regularly check community forums for updates and breakthroughs.
---
📅**Release Date:** 21/01/2026  
🔄**Last Updated:** 27/01/2026  
ℹ️**Status:** Informational/Educational
___
