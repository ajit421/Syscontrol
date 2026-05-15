# 🛡️ SysControl

**SysControl** is a personal remote administration tool **(RAT)** that allows you to control and monitor your Windows computer entirely through **Telegram**.

It runs invisibly in the background and can automatically start when you turn on your computer.

> **⚠️ Disclaimer:** This tool is for educational purposes and personal use on your **own devices only**. Using this to control computers without permission is illegal.

---

## 🚀 Key Features

* **📸 Surveillance:** Take screenshots (`/screen`) and capture webcam images (`/webcam`).
* **💻 Remote Control:** Lock the screen, shutdown the PC, or run shell commands.
* **📂 File Manager:** View files, change folders, and download files from your PC to your phone.
* **🔊 Text-to-Speech:** Make your computer "speak" any text you send (`/speech`).
* **📋 Clipboard:** Read what is currently copied to your PC's clipboard.
* **👻 Hidden Mode:** Runs silently in the background without any visible windows.
* **🔌 Auto-Connect:** Can automatically connect to Wi-Fi and start upon boot.

---

## 🛠️ Installation Guide

Follow these steps to set up the bot on your computer.

### 1. Download & Prepare
1.  Download this project folder to your computer. (choose any secret path) (Recommended path: `C:\Users\<username>/syscontrol`).
2.  Make sure you have **Python** installed.


### 2. Install Dependencies (All Platforms)

Open your terminal (Command Prompt, PowerShell, or Terminal) inside the project folder and run the commands for your system.

```Bash
cd Syscontrol

```

**🪟 For Windows:**

```powershell
# 1. Create a virtual environment
python -m venv .venv

# 2. Activate the environment
.venv\Scripts\activate

# 3. Install required libraries
pip install -r requirements.txt

```

**🍎 For Mac & 🐧 Linux:**

```bash
# 1. Create a virtual environment
python3 -m venv .venv

# 2. Activate the environment
source .venv/bin/activate

# 3. Install required libraries
pip install -r requirements.txt

```

### 3. Configure the Bot

1. Create a new file named `.env` in the project root folder.
2. Open `.env` with a text editor and add the following lines:
```env
TOKEN=YOUR_TELEGRAM_BOT_TOKEN
CHAT_ID=YOUR_TELEGRAM_CHAT_ID
```
3. Replace `YOUR_TELEGRAM_BOT_TOKEN` with your bot's Token from BotFather.
4. Replace `YOUR_TELEGRAM_CHAT_ID` with your Telegram chat ID.

---

## 🔄 How to Run Automatically (Startup Setup)

To make the bot start automatically every time you turn on your computer, follow these steps using the **VBS script**.

**1. Edit the VBS Script**
Open `rat_wifi_venv_bot.vbs` in Notepad and make sure the paths match exactly where your folder is located.

*Example (if your project is in D:\Code\Syscontrol):*

```vbscript
cmd = """D:\Code\Syscontrol\.venv\Scripts\pythonw.exe"" ""D:\Code\Syscontrol\syscontrol_bot.py"""

```

**2. Move to Startup Folder**
Copy the `rat_wifi_venv_bot.vbs` file and paste it into your Windows Startup folder.

**Startup Folder Path:**

```text
C:\Users\YOUR_USERNAME\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup

```

*(Replace `YOUR_USERNAME` with your actual PC username, e.g., `binod`)*

**3. Test It**

* Restart your computer.
* Wait for 1-2 minutes.
* Check your Telegram bot—it should be online automatically!

---

## 📱 Command List

Once the bot is running, open Telegram and use these commands:

| Command | Description |
| --- | --- |
| `/auth [password]` | **First Step:** Login to the bot using your password. |
| `/start` | Show the main menu and list of commands. |
| `/screen` | Take a screenshot of the desktop. |
| `/webcam` | Take a photo using the webcam. |
| `/sys` | Show system info (CPU, RAM, OS). |
| `/ip` | Show the public IP address of the computer. |
| `/ls` | List files in the current folder. |
| `/cd [folder]` | Change directory (e.g., `/cd Desktop`). |
| `/upload [file]` | Upload a specific file from PC to your Telegram. |
| `/clipboard` | Show the current text in the clipboard. |
| `/speech [text]` | Play a voice message on the computer speakers. |
| `/lock` | Lock the computer screen immediately. |
| `/shutdown` | Turn off the computer remotely. |
| `/wifi` | Display saved Wi-Fi profiles and passwords. |
| `/shell` | Enter "Shell Mode" to run CMD commands directly. |

---

## ❓ Troubleshooting

**Bot not responding?**

1. Check your internet connection.
2. Open Task Manager and look for a `python` or `pythonw` process.
3. If it's not running, double-click `syscontrol_bot.py` manually to see if any errors appear.

**VBS Script Error?**

* Ensure the paths in `rat_wifi_venv_bot.vbs` point to the correct `.venv` folder and `.py` file.
* Make sure you used `pythonw.exe` (with a **w**) to keep it hidden.