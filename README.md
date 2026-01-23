# PS4-Offline-RemotePlay-Unchained
 Connecting Chiaki &amp; PSPlay without PSN account

#PlayStation Remote Play Setup Guide (Chiaki & PSPlay)
📋 Table of Contents
Prerequisites

PS4 Setup

PS5 Setup

ID Conversion Guide

Remote App Configuration

Troubleshooting

🎮 Prerequisites
For Both PS4 & PS5:
Jailbroken console with latest exploit

Static IP Address for your console (set via router DHCP reservation)

Remote Play turned OFF before running jailbreak

USB drive for file transfers

Basic Python knowledge for ID conversion

Network Requirements:
Ethernet recommended for best performance

5GHz WiFi for 1080p/60fps streaming

2.4GHz WiFi limited to 720p/30fps

PS4 Fat/Slim max resolution: 720p

🖥️ PS4 Setup
Step 1: Activate Your Account Offline
Download Apollo Save Tool from:

GitHub Repository

Install Apollo on your PS4 via USB

In Apollo:

Navigate to User Activation

Select Activate User

Note down your 16-digit hexadecimal ID

Step 2: Transfer Files
Use Apollo's built-in USB transfer features

OR use FTP server (requires additional setup)

Step 3: Enable Remote Play
Run jailbreak exploit

After jailbreak loads, enable Remote Play in Settings

Note your 8-digit Remote Play PIN

🎯 PS5 Setup
Step 1: Prepare Files
Download from PS5 Payload Repository:

homebrewloader.pkg

OffAct.zip

Prepare USB drive:

text
USB Root/
├── homebrewloader.pkg
└── homebrew/
    └── OffAct/ (extracted files)
Step 2: Transfer Files to PS5
Method A (Recommended):

Install and launch Ps5-Xplorer

Copy homebrew folder to /data/ directory

Install homebrewloader.pkg via Package Installer

Method B (FTP - Old Jailbreaks):

If using old jailbreak, run john-tornblom elfldr after loading jailbreak

Use FTP server to transfer files to /data/

Step 3: Activate Account
Launch HomebrewLoader from PS5 menu

Press X to select OfflineActivator (OffAct)

Press O to close dialog

Select your local offline account with X

Write down the 16-digit hexadecimal ID shown

Select Done to activate

Reboot your PS5

Step 4: Enable Remote Play
Run jailbreak exploit

After jailbreak loads, enable Remote Play in Settings

Note your 8-digit Remote Play PIN

🔄 ID Conversion Guide
Required Software:
Python 3.x - Download from:

Official Site

Microsoft Store (Windows)

Conversion Methods:
1. Hexadecimal (16-digit) → Decimal (19-digit) for PSPlay
Use this Hex to Decimal Converter OR Python:

python
hex_id = "1234567890ABCDEF"  # Your 16-digit hex ID
decimal_id = int(hex_id, 16)
print(f"19-digit ID: {decimal_id}")
2. Hexadecimal (16-digit) → Base64 Encoded ID for Chiaki
python
import base64

# For 16-digit hexadecimal ID
activated_id = "1234567890ABCDEF"  # Your PS4/PS5 ID
encoded_id = base64.b64encode(int(activated_id, 16).to_bytes(8, 'little')).decode()
print(f"Encoded ID for Chiaki: {encoded_id}")
3. Decimal (19-digit) → Base64 Encoded ID for Chiaki (Bonus)
python
import base64

# For 19-digit decimal ID (from PSPlay conversion)
activated_id = 1234567890123456789  # Your 19-digit ID
encoded_id = base64.b64encode(activated_id.to_bytes(8, 'little')).decode()
print(f"Encoded ID for Chiaki: {encoded_id}")
📱 Remote App Configuration
Chiaki Setup (Open Source):
Download: Chiaki GitHub

First Launch:

Click "Add Host"

Host: Console's local IP address

Encoded ID: Base64 encoded ID (from Python conversion)

PIN: 8-digit Remote Play PIN

Firmware: Select "8.0+" for PS4, "PS5" for PS5

Registration:

Click "Register"

Select firmware version matching your console

PS4: Choose 8.0+ or specific version (5/6/7)

PS5: Select PS5 option

PSPlay Setup:
Download: PSPlay Application Hosting

Initial Setup:

Uncheck "Enable automatic remote connection"

Select "New Device"

Choose your console type

Manual Registration:

Check "Advanced setting"

Select "Register PS manually"

IP Address: Console's local IP

PSN Account ID: 19-digit decimal ID

Registration Number: 8-digit PIN

Select appropriate console version

Performance Settings:
720p @ 30fps: 2.4GHz WiFi or unstable connections

1080p @ 30/60fps: 5GHz WiFi or Ethernet

PS4 Fat/Slim: Maximum 720p in both apps

⚠️ Troubleshooting
Common Issues & Solutions:
"Connection Failed" Errors:

Ensure jailbreak is ACTIVE

Remote Play turned ON after jailbreak

Console has static IP address

PS5 File Transfer Problems:

Old jailbreaks require elfldr for FTP

Use Ps5-Xplorer as alternative

Check USB format (exFAT/FAT32)

ID Conversion Errors:

Verify 16-digit hexadecimal format

Ensure Python bytes conversion uses 'little' endian

Double-check Remote Play PIN

Stream Quality Issues:

Use Ethernet when possible

Reduce resolution on 2.4GHz networks

Close other network-intensive applications

Activation Problems:

Re-run activation process

Ensure console is offline during activation

Reboot console after activation

Important Notes:
✅ No PSN account required for offline activation

✅ Works completely offline after setup

✅ Both Chiaki and PSPlay support offline-activated consoles

❌ Remote Play must be OFF during jailbreak loading

❌ Don't update console firmware after jailbreak

🔗 Useful Resources
Essential Tools:
Hex Converter: RapidTables

Python Downloads: python.org

GitHub Repositories:
Chiaki: github.com/thestr4ng3r/chiaki

PSPlay: github.com/streamingdv/PSPlay-Application-Hosting

Apollo (PS4): github.com/bucanero/apollo-ps4

PS5 OffAct: github.com/ps5-payload-dev/websrv

📝 Final Checklist
Before Starting:
Console jailbroken

Static IP configured

Remote Play disabled

USB drive prepared

Python installed

After Setup:
Account activated offline

IDs converted properly

Remote Play enabled

Apps configured correctly

Connection tested

