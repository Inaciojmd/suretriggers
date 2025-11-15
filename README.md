# SureTriggers <= 1.0.78 Authorization Bypass Exploit Tool

This tool provides a graphical interface (GUI) to exploit the **Authorization Bypass vulnerability** found in the **SureTriggers WordPress plugin (versions ≤ 1.0.78)**. The vulnerability allows unauthorized creation of administrator accounts via the plugin's REST API endpoint.

---

## 📌 Features

- 🔹 **Single Target Mode** – Test and exploit one WordPress site.
- 🔹 **Multiple Targets Mode** – Load a list of URLs from a `.txt` or `.csv` file.
- 🔹 **Automatic Plugin Version Detection** – Reads `readme.txt` to identify the installed plugin version.
- 🔹 **Multithreading Support** – Speed up exploitation across many targets.
- 🔹 **Custom Credentials** – Define email, username, and password for account creation.
- 🔹 **Export Results** – Save the results to `.csv` or `.txt`.
- 🔹 **Terminal‑style Output Window** – Real-time logging.

---

## ⚠️ Disclaimer
This project is for **educational and authorized penetration testing only**.
Unauthorized access to systems is illegal and unethical. The author is **not responsible** for misuse.

---

## 🚀 How It Works

1. The tool checks the plugin version at:
   ```text
   /wp-content/plugins/suretriggers/readme.txt
   ```

2. If the version is **≤ 1.0.78**, the plugin is likely vulnerable.

3. The exploit sends a crafted POST request to:
   ```text
   /wp-json/sure-triggers/v1/automation/action
   ```

4. The payload instructs the plugin to create a new WordPress user.

5. If successful, you will obtain the created **username:password** credentials.

---

## 🛠️ Requirements

- Python 3.8+
- Required modules:
  ```bash
  pip install requests
  ```
  Tkinter is included by default in most Python installations.

---

## 📥 How to Run

1. Save the script as:
   ```text
   suretriggers.py
   ```

2. Run it using:
   ```bash
   python3 suretriggers.py
   ```

3. The GUI window will open.

---

## 📁 File Input Format

### TXT File
```
http://example1.com
http://example2.com
```

### CSV File
```
url
http://example1.com
http://example2.com
```

---

## 🧩 GUI Overview

### **Top Section**
- Single or Multiple Target mode selection.
- Target URL or file selector.

### **Credentials Section**
You can customize:
- Email
- Username
- Password

### **Options Section**
- Number of threads (1–20)
- Delay between requests

### **Output Window**
Shows:
- Version scan results
- Exploit attempt results
- Errors or success messages

---

## 📊 Saving Results
You can export results as:
- `.csv` — Structured data
- `.txt` — Simple readable text

Each result record includes:
- Target URL
- Status (Vulnerable, Exploited, Failed, etc.)
- Plugin version
- Created credentials
- Message/notes

---

## 👨‍💻 Author
**By: Nxploited (Khaled Alenazi)**

This GUI tool was adapted from original exploit research and improved with user-friendly controls.

---

## 📝 License
This project is released for **educational and testing purposes only**. Do not use it unlawfully.

---

## ⭐ Support
If you find this tool useful, consider giving credit to the author.

---

## 📷 Banner
The original ASCII banner prints automatically in the application's output window.

---

Enjoy using the tool responsibly! 🚀

