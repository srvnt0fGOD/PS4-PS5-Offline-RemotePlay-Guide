# PS4-PS5-Offline-RemotePlay-Connect
 Connecting Chiaki and Chiaki-ng without PSN account

 # PlayStation Remote Play

## ⚠️ IMPORTANT DISCLAIMER & SUCCESS RATE WARNING

**READ THIS FIRST:** This guide documents methods that **have worked for some users on specific setups**, but **success is NOT guaranteed**. These methods bypass Sony's official activation process and results vary widely based on:

### ⚡ **Success Rate Factors:**
- **Firmware Version:** Older firmwares work better
- **Jailbreak** Run latest

---

## 📋 Table of Contents
- [Prerequisites](#prerequisites)
- [Success Rate by Console](#success-rate-by-console)
- [Method 1: PS4/PS5 Offline Activation with Apollo/OffAct](#method-1-ps4ps5-offline-activation-with-apollooffact)
- [Method 2: PS4/PS5 Official Activation with Appolo/OffAct](#method-2-ps4ps5-official-activation-with-appolooffact)
- [Method 3: GoldHEN + Patches (Recommended)](#method-3-goldhen--patches-recommended)
- [Method 4: Alternative Approaches](#method-4-alternative-approaches)
- [ID Conversion Guide](#id-conversion-guide)
- [App Configuration](#app-configuration)
- [Troubleshooting & Community](#troubleshooting--community)

---

## 🎮 Prerequisites

### **For ANY Method to Work:**
1. **Jailbroken console** with latest exploit
2. **Static IP Address** for your console (set via router DHCP reservation)
3. **Remote Play turned OFF before running jailbreak**
4. **USB drive** for file transfers
5. **Realistic expectations** - this is NOT official Remote Play
6. **Technical patience** - be prepared for trial and error

### **Network Requirements:**
- **Ethernet strongly recommended** for stability
- **5GHz WiFi** for 1080p/60fps streaming
- **2.4GHz WiFi** if using wireless use 720-30fps for stable connection
- **PS4 Fat/Slim** max resolution: 720p
- **Port forwarding may help** (TCP 9295, UDP 9296-9297)

---

## 📊 Success Rate by Console

### **PS4 Firmware 9.00 or Lower:**
- **Remote play Connection:** high success
- **Best method:** GoldHEN latest version
- **Remote play enabler:** only for 5.05 firmware

### **PS4 Firmware Above 9.00:**
- **Any method:** <20% success
- **Recommendation:** Use alternative streaming methods

### **PS5 Any Firmware:**
- **Extremely YMMV (Your Mileage May Vary)**

---

## 🔧 Method 1: PS4/PS5 Offline Activation with Apollo/OffAct

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
       └── OffAct/ (OffAct.zip extracted files)
           /homebrew/OffAct/
### **Method A (Recommended):**
   
   - Install and launch `Ps5-Xplorer`
   - Copy `homebrew` folder to `/data/` directory
   - Install `homebrewloader.pkg` via Package Installer

### **Method B (FTP - latest Jailbreak):**

   - **If using old jailbreak, `run john-tornblom elfldr` after loading jailbreak
   - Use FTP server to transfer `/homebrew/OffAct/` to `/data/`  directory

4. **Activation Attempt:**

   - Install homebrewloader.pkg, Launch `HomebrewLoader`
   - Press `X` to select `OfflineActivator (OffAct)`
   - Press `O` to close dialog
   - When the Offline Account list appears, Select your local offline account.
   - Press `X` on your local offline account to generate a ranodm 16-digit ID, Note this down for later.
   - Select done to activate your offline account and Reboot
   - Download any payload injector or download [NetCat GUI](https://www.sendspace.com/file/5rz4lg)
   - Download [Remote play payload](https://github.com/idlesauce/ps5-remoteplay-get-pin/releases)
   - Open NetCat GUi and enter PS5 `ip address` in host box and port num `9021`
   - Download Remote play payload [rp-get-pin.elf](https://github.com/idlesauce/ps5-remoteplay-get-pin/releases)
   - Browse or drag it inside NetCat GUI and select "Inject Payload".
   - you will get your notification in ps5 after injecting Payload
   - 8 pin-code and activated offline or official account Encoded ID `(Base64-encoded 8-byte (64-bit) Little-Endian ID)` will popup .
   - You must be in the exploit environment (where your ELF loader is listening, port 9021)
   - or you can get your Encoded ID with Python by puting the command with your 16-digit ID `(Hexadecimal)` or 19-digit ID `(Decimal)` I mentioned below.
   
   ---

## 🛠️ Method 2: PS4/PS5 Official Activation with Appolo/OffAct

### **Official Activation Method for PS4/PS5**

   - **PSN Registeration** create new PSN account and create your username
   - **Find your ID:** Enter your PSN username into the [PSN ID Grabber](https://psn.flipscreen.games)
   - **Retrieve your official Account ID** `(19-digit Decimal)` for PSPlay and your Encoded ID `(Base64-encoded 8-byte (64-bit) Little-Endian ID)` for Chiaki-ng or Chiaki from PSN ID grabber
   - Enter 19-digit ID into the [Decimal to HEX Converter](https://www.rapidtables.com/convert/number/decimal-to-hex.html) to get your **16-digit Hex ID**.
   -  While activating local Account using Apollo or OffAct on your PS4/PS5, replace the replace the "random" User ID with your official **16-digit Hex ID**.
   - Select **Done** and **Reboot** your console to apply the changes.
   
## ⭐ Method 3: GoldHEN + Patches (Only for PS4 5.05)

### **For PS4 Firmware 9.00:**
1. **Use Latest GoldHEN**
2. **downlaod Remote Play Enabler ps4ren.bin [PS4REN Repository](https://github.com/SiSTR0/ps4ren)**
3. **inject payload through NetCat GUI**
4. **Verification:**
   - Check if Remote Play appears in Settings
   - If visible, it's likely working


## 🔄 Method 4: Alternative Approaches

### **If All Activation Methods Fail:**

#### **2. Local Game Streaming (Reliable Alternative):**
- **Moonlight + Sunshine:** Stream from gaming PC
- **Steam Link:** Stream Steam games
- **Parsec:** Low-latency desktop streaming

#### **3. Paid Alternative:**
- **PSPlay:** more lenient with activation
- **Repl4y:** Another third-party app

---

## 🔢 ID Conversion Guide 

### **Required Software:**

  - **Python latest `version`** - Download from:
  - [Official Site](https://www.python.org/downloads/)
  - Microsoft Store (Windows)

### **Convert Activated Official and Offline Account for Connecting Remote Play**

  - [For Chiaki-ng/Chiaki need Encoded ID (Base64-encoded 8-byte (64-bit) Little-Endian ID](#for-chiaki-ng-chiaki-need-encoded-id-base64-encoded-8-byte-64-bit-little-endian-id)
  - [For PSPlay (Paid) need 19-digit ID](#for-psplay-paid-need-19-digit-id)

##  For Chiaki-ng/Chiaki need Encoded ID (Base64-encoded 8-byte (64-bit) Little-Endian ID

### Conversion Methods:

#### 2. Activated Account Hexadecimal (16-digit) → Base64 Encoded ID for Chiaki

```python
import base64
activated_id = "your-16digit-offline-Id"
print(base64.b64encode(int(activated_id, 16).to_bytes(8, 'little')).decode())
```
example:

```
>>> import base64
... activated_id = "1234567890123456"
... print(base64.b64encode(int(activated_id, 16).to_bytes(8, 'little')).decode())
...
VjQSkHhWNBI=
```
add `VjQSkHhWNBI=` in chiaki-ng/Chiaki encoded ID for connecting 


#### 3. Decimal (19-digit) for Official Account  → Base64 Encoded ID for Chiaki  (Bonus)
```python
import base64

# For 19-digit decimal ID (from PSPlay conversion)
activated_id = 1234567890123456789  # Your 19-digit ID
encoded_id = base64.b64encode(activated_id.to_bytes(8, 'little')).decode()
print(f"Encoded ID for Chiaki: {encoded_id}")
```

---


#### 1. Hexadecimal (16-digit) → Decimal (19-digit) for PSPlay

Use this [Hex to Decimal Converter](https://www.rapidtables.com/convert/number/hex-to-decimal.html) OR Python:

```python
hex_id = "1234567890ABCDEF"  # Your 16-digit hex ID
decimal_id = int(hex_id, 16)
print(f"19-digit ID: {decimal_id}")
```


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

#### **For PSPlay(Paid)

#### **Offline Activatd (need 19-digit decimal ID converted from 16-digit Hex ID):**
- Convert your activated offline 16-digit Hex ID to 19-digit decimal ID using [Hex to Decimal](https://www.rapidtables.com/convert/number/hex-to-decimal.html) for connect with PSPlay.

### **If Connecting With PSN Official Account**
- if activated using official account, grab your official PSN account 19 digit for PSPlay(Paid)
- Enter your official account username in [PSN ID Grabber](https://psn.flipscreen.games)
-  
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
