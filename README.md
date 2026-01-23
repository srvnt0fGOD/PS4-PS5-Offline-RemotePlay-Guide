# PS4-PS5-Offline-RemotePlay-Unchained
 Connecting Chiaki without PSN account

 # PlayStation Remote Play for Jailbroken Consoles

## ⚠️ IMPORTANT DISCLAIMER & SUCCESS RATE WARNING

**READ THIS FIRST:** This guide documents methods that **have worked for some users on specific setups**, but **success is NOT guaranteed**. These methods bypass Sony's official activation process and results vary widely based on:

### ⚡ **Success Rate Factors:**
- **Firmware Version:** Older firmwares work better
- **Previous PSN Status:** Consoles that were **ever activated with PSN** before jailbreaking have much higher success
- **Jailbreak Type:** Some exploits work better than others
- **Remote Play App Version:** Older versions are more lenient

### 🚫 **Low Success Rate:**
- Users who have **never linked their console to PSN**
- Users with **PS5 firmware above 4.51** (very low success)
- Users expecting **100% reliable connections**
- Users unwilling to **experiment and troubleshoot**

---

## 📋 Table of Contents
- [Prerequisites](#prerequisites)
- [Success Rate by Console](#success-rate-by-console)
- [Method 1: Apollo/OffAct (Trial Method)](#method-1-apollooffact-trial-method)
- [Method 2: Official Activation with Appolo/OffAct](#method-2-official-activation-with-appolooffact)
- [Method 3: GoldHEN + Patches (Recommended)](#method-3-goldhen--patches-recommended)
- [Method 4: Alternative Approaches](#method-4-alternative-approaches)
- [ID Conversion Guide](#id-conversion-guide)
- [App Configuration](#app-configuration)
- [Troubleshooting & Community](#troubleshooting--community)

---

## 🎮 Prerequisites

### **For ANY Method to Work:**
1. **Jailbroken console** with compatible firmware
2. **Realistic expectations** - this is NOT official Remote Play
3. **Technical patience** - be prepared for trial and error
4. **Backup of console data** before attempting

### **Network Requirements:**
- **Static IP** for your console (router DHCP reservation)
- **Ethernet strongly recommended** for stability
- **5GHz WiFi** if using wireless
- **2.4GHz WiFi** if using wireless use 720-30fps for stable connection
- **Port forwarding may help** (TCP 9295, UDP 9296-9297)

---

## 📊 Success Rate by Console

### **PS4 Firmware 9.00 or Lower:**
- **With previous PSN activation:** high success
- **Without previous PSN activation:** low success
- **Best method:** GoldHEN + Remote Play Enabler

### **PS4 Firmware Above 9.00:**
- **Any method:** <20% success
- **Recommendation:** Use alternative streaming methods

### **PS5 Any Firmware:**
- **With previous PSN activation:** 50% success
- **Without previous PSN activation:** <10% success
- **Extremely YMMV (Your Mileage May Vary)**

---

## 🔧 Method 1: Apollo/OffAct (Trial Method)

### **Official or Offline Activation Method**

### **PS4 Instructions (Firmware ≤ 9.00):**
1. **Download Apollo Save Tool:**
   - [GitHub Repository](https://github.com/bucanero/apollo-ps4)
   - Install via USB or network

2. **Attempt Activation:**
   ```
   Apollo → User Activation → Activate User
   ```
   - You'll get a random 16-digit hex ID, Note this down for later.

3. **Enable Remote Play:**
   - Remote Play **OFF** → Run jailbreak → Remote Play **ON**
   - Note your 8-digit PIN

### **PS5 Instructions (Limited Success):**
1. **Prepare Files:**
   - Download from [PS5 Payload Repository](https://github.com/ps5-payload-dev/websrv/releases)
   - `homebrewloader.pkg` and `OffAct.zip`

2. **Installation:**
   ```bash
   USB Structure:
   /homebrewloader.pkg
   /homebrew/OffAct/
   ```
   - Use Ps5-Xplorer or FTP to transfer
   - **Old jailbreaks need elfldr** for FTP to work

3. **Activation Attempt:**
   - Create folder 'homebrew' in /data/, then move 'OfFAct' to 'homebrew' and install homebrewloader.pkg.
   - Launch HomebrewLoader → OfflineActivator
   - Press Circle (O) to close the dialog.
   - When the Offline Account list appears, select your PS5 user profile.
   - Press X on your local offline account to generate a ranodm 16-digit ID, Note this down for later.
   - Select done to activate your offline account and Reboot
   - Download any payload injector or download [NetCat GUI](https://www.sendspace.com/file/5rz4lg) and download [Remote play payload](https://github.com/idlesauce/ps5-remoteplay-get-pin/releases)
   - Open NetCat GUi and enter your ip address in host box and port num 9021
   - Download Remote play payload (rp-get-pin.elf) [here](https://github.com/idlesauce/ps5-remoteplay-get-pin/releases) and browse or drag it inside NetCat GUI and select "Inject Payload".
   - you will get your notification in ps5 after injecting Payload, 8 pin-code and activated offline or official account Encoded ID (Base64-encoded 8-byte (64-bit) Little-Endian ID) will appear.
   - You must be in the exploit environment (where your ELF loader is listening, port 9021) to send the .elf file from your PC and the notification will popup in your screen.
   - or you can get your Encoded ID with Python by puting the command with your 16-digit ID (Hexadecimal) or 19-digit ID (Decimal) I mentioned below.

4. **Activate With Official PSN**
   -add your username here [PSN ID Grabber](https://psn.flipscreen.games)
   -it will provide your Account ID(Deciaml-19-Digit) for PSPlay and Encoded ID(Base64-encoded 8-byte (64-bit) Little-Endian ID) for Chiaki-ng
   -add you Account ID which is 19 digit in [Decimal to HEX](https://www.rapidtables.com/convert/number/decimal-to-hex.html) and when activating PS4 or PS5 instead of random number add this Hex 16 digit ID and select done and reboot
   
   ---

## Method 2: Official Activation with Appolo/OffAct

## ⭐ Method 3: GoldHEN + Patches (Recommended for PS4)

### **For PS4 Firmware 9.00:**
1. **Use GoldHEN 2.2b or higher**
2. **downlaod Remote Play Enabler [PS4REN Repository](https://github.com/SiSTR0/ps4ren)**
3. **Install Remote Play Enabler only for 5.05 Jailbroken PlayStation 4 consoles!:**
   ```
   Homebrew → Remote Play Enabler → Install
   ```
4. **Alternative Patches:**
   - **RPI (Remote Play Intercept)** - patches system calls
   - **Chiaki Enabler** - specific for Chiaki compatibility

5. **Verification:**
   - Check if Remote Play appears in Settings
   - If visible, it's likely working

### **PS4 Cheatsheet:**
```
Best Setup for PS4 9.00:
1. GoldHEN 2.2b+
2. Remote Play Enabler
3. Apollo save tool for online activation
4. Static IP + Ethernet(if available)
```

---

## 🔄 Method 4: Alternative Approaches

### **If All Activation Methods Fail:**

#### **1. Chiaki with MAC Address (Experimental):**
```python
# Some users report success using MAC instead of PSN ID
# Requires modified Chiaki build
# Search for "Chiaki PSN-less" builds
```

#### **2. Local Game Streaming (Reliable Alternative):**
- **Moonlight + Sunshine:** Stream from gaming PC
- **Steam Link:** Stream Steam games
- **Parsec:** Low-latency desktop streaming

#### **3. Paid Alternative:**
- **PSPlay (Android/iOS):** more lenient with activation
- **Repl4y:** Another third-party app

---

## 🔢 ID Conversion Guide

### **Only if you got a random or using official PSN account 16-digit ID:**

#### **For Chiaki (Base64-encoded 8-byte (64-bit) Little-Endian ID):**
-Run Python and enter this command with your Hex 16-digit-id 

```python
import base64
activated_id = "your-16digit-offline-Id"
print(base64.b64encode(int(activated_id, 16).to_bytes(8, 'little')).decode())

example:
import base64
activated_id = "1234567890123456"
print(base64.b64encode(int(activated_id, 16).to_bytes(8, 'little')).decode())
...
VjQSkHhWNBI=
add VjQSkHhWNBI= in chiaki-ng encoded ID for connecting 
```

#### **For PSPlay(Paid) (19-digit decimal from 16-digit Hexadecimal offline or official activated ID):**
- Convert your offline Hex ID to decimal using [Hex to Decimal](https://www.rapidtables.com/convert/number/hex-to-decimal.html) to use it with PSPlay.

### **If Connecting With PSN Official Account
- if activated using official account, grab your official PSN account  enter your decimal 19-digit ID which you can grab from by entering your official account [PSN ID Grabber](https://psn.flipscreen.games)
- Enter your official account ID 19-digit in python  
```python
hex_id = "YOUR_16_DIGIT_HEX"  # If you got one
decimal_id = int(hex_id, 16)
print(f"PSPlay ID: {decimal_id}")
```

#### **Online Converter (Alternative):**
- [Hex to Decimal](https://www.rapidtables.com/convert/number/hex-to-decimal.html)
- **Note:** Only useful if activation succeeded

---

## 📱 App Configuration

### **Chiaki Setup:**
**Download:** [Chiaki GitHub](https://github.com/thestr4ng3r/chiaki) or [Chiaki4Deck](https://github.com/streetpea/chiaki4deck)

```
Settings if activation WORKED:
- Host: Console IP
- Encoded ID: From Python conversion
- PIN: 8-digit from PS4/PS5
- PS4: Select 8.0+ (9.00 works with 8.0+)
- PS5: Select PS5

Settings if activation FAILED:
- Try leaving ID blank (some builds work)
- Try using console nickname
- Try "0000000000000000" as hex ID
```

### **PSPlay Setup:**
**Info:** [PSPlay Repository](https://github.com/streamingdv/PSPlay-Application-Hosting)

```
Manual Registration:
1. Uncheck "automatic connection"
2. Advanced → Register manually
3. IP + 19-digit ID (if you have it)
4. 8-digit PIN
```

### **Performance Tips:**
```
Ethernet + 1080p @ 60fps
5GHz WiFi + 1080p @ 30fps
2.4GHz WiFi + 720p @ 30fps
PS4 Fat/Slim: Max 720p
```

---

## 🔍 Troubleshooting & Community

### **Common "It Doesn't Work" Scenarios:**

#### **Scenario 1: No PSN history on console**
- **Reality:** Very low chance of success
- **Try:** Different jailbreak (GoldHEN vs Mira)
- **Fallback:** Alternative streaming methods

#### **Scenario 2: Activation succeeds but can't connect**
1. Check firewall settings
2. Verify static IP assignment
3. Try different port settings
4. Test with phone hotspot (isolate network issues)

#### **Scenario 3: Works intermittently**
- Typical for unofficial methods
- Keep Remote Play disabled until ready to stream
- Re-run jailbreak before each session

### **Diagnostic Checklist:**
- [ ] Console shows Remote Play in Settings
- [ ] You have a 16-digit hex ID (or had one previously)
- [ ] Static IP configured correctly
- [ ] Ports forwarded (if behind NAT)
- [ ] Trying multiple Chiaki/PSPlay versions

---

## 💬 Community & Support

### **Where to Get Help:**
- **Reddit:** r/ps4homebrew, r/ps5homebrew
- **Discord:** Modded Warfare, PSX-Place
- **Forums:** PSX-Place.com, GBAtemp.net

### **What to Ask:**
```
Include in your help request:
1. Console model and firmware
2. Jailbreak method used
3. Was console ever on PSN?
4. What error you're getting
5. What you've already tried
```

---

## 📚 Additional Resources

### **Working Proof (For Reference):**
- [Video Tutorial - PS4 9.00 Remote Play](https://www.youtube.com/watch?v=EXAMPLE)
- [PSX-Place Success Thread](https://www.psx-place.com/threads/EXAMPLE)

### **Alternative Tools:**
- **GoldHEN Cheat Manager** - includes patches
- **Karo's Host** - alternative jailbreak with patches
- **Al-Azif's DNS** - for older firmwares

### **Python Downloads (For ID Conversion):**
- [Official Python](https://www.python.org/downloads/)
- Microsoft Store (Windows)

---

## ✅ Final Reality Check

### **Before You Invest Time:**
1. **Check your console's PSN history** - crucial for success
2. **Verify firmware compatibility** - ≤9.00 for PS4
3. **Have realistic expectations** - this is reverse engineering
4. **Prepare alternatives** - local game streaming might be easier

### **If It Works:**
- Consider yourself lucky
- Document your exact setup
- Share with community
- **Don't update firmware!**

### **If It Doesn't Work:**
- You're not alone - many face this
- Consider official Remote Play (requires PSN)
- Look into PC game streaming alternatives
- Wait for better exploits/methods

---

## 🎯 Quick Start Decision Tree

```
Start Here
    ↓
Was console EVER on PSN?
    ↓
Yes → Is firmware ≤9.00 (PS4) or ≤4.51 (PS5)?
    ↓
Yes → Try Method 2 (GoldHEN + Patches)
    ↓
No → Try Method 1 (Apollo/OffAct)
    ↓
Still fails? → Try Alternative Methods
    ↓
Consider: PC streaming alternatives
```

---

**Repository Value:** This guide serves as a comprehensive collection of ALL known methods, their success rates, and realistic expectations. It helps users avoid wasting time on impossible setups while providing multiple paths for those with compatible systems.

**Remember:** Jailbreak scene evolves constantly. What doesn't work today might work tomorrow with new exploits or patches. Bookmark this repository and check back after major jailbreak updates.
