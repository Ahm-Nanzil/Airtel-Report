<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:FF4B2B,100:FF416C&height=200&section=header&text=Airtel%20Report%20Automation&fontSize=40&fontColor=fff&fontAlignY=38&desc=Automated%20reporting%20powered%20by%20Python%20%2B%20Playwright&descAlignY=58&descSize=16" width="100%"/>

<br/>

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Playwright](https://img.shields.io/badge/Playwright-Automation-2EAD33?style=for-the-badge&logo=playwright&logoColor=white)](https://playwright.dev)
[![Platform](https://img.shields.io/badge/Platform-Windows%2010+-0078D4?style=for-the-badge&logo=windows&logoColor=white)](https://www.microsoft.com/windows)
[![License](https://img.shields.io/badge/License-Key%20Required-FF4B2B?style=for-the-badge&logo=keycdn&logoColor=white)](#-license-requirement)

<br/>

> **Fully automated Airtel reporting system** — generate hourly reports, backfill missing data, and keep your report history clean with zero manual effort.

<br/>

</div>

---

## 📌 Overview

This project provides a complete automation suite for Airtel report generation:

| Feature | Description |
|---|---|
| ⏱ **Hourly Automation** | Automatically triggers every hour via scheduler |
| 📊 **Current Hour Report** | Generates report for the active hour (`airtel.py`) |
| 🕓 **Custom Range Report** | Backfill any number of past hours (`airtel_manual.py`) |
| 🔁 **Background Scheduler** | Runs silently and continuously (`main.py`) |
| 🧹 **Auto Cleanup** | Deletes future-hour reports before regenerating |

---

## 📂 Project Structure

```text
Airtel-Report/
│
├── 📁 __pycache__/
├── 📁 pyarmor_runtime_000000/
├── 🐍 airtel.py              ← Current hour report generator
├── 🐍 airtel_manual.py       ← Custom range report generator
├── 🐍 main.py                ← Hourly scheduler
├── 🐍 license_check.py       ← License validation module
├── 📄 credentials.txt        ← Portal login credentials
├── 🔑 license.key            ← License key (required)
└── 📁 venv/                  ← Python virtual environment
```

---

## ⚙️ Requirements

Before getting started, make sure you have the following:

- 🖥️ **Windows 10** or later
- 🐍 **Python 3.10+**
- 🌐 Active **internet connection**
- 🔐 Valid **Airtel portal credentials**
- 🔑 A valid **`license.key`** obtained from the administrator

---

## 🛠️ Installation

Follow these steps carefully to set up the project:

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/Ahm-Nanzil/Airtel-Report.git
```

```bash
cd Airtel-Report
```

---

### 2️⃣ Create a Virtual Environment

```bash
python -m venv venv
```

---

### 3️⃣ Activate the Virtual Environment

```bash
venv\Scripts\activate
```

---

### 4️⃣ Upgrade pip

```bash
python -m pip install --upgrade pip
```

---

### 5️⃣ Install Dependencies

```bash
python -m pip install playwright cryptography
```

---

### 6️⃣ Install Playwright Browsers

```bash
python -m playwright install
```

---

## 🔐 Credentials Setup

Open `credentials.txt` and add your Airtel portal login details:

```ini
USERNAME=your_email_here
PASSWORD=your_password_here
```

> ⚠️ **Never share or commit `credentials.txt` to version control.**

---

## 🔑 License Requirement

> This project is **license-protected**. A valid `license.key` file must be present in the root directory before running any script.

📩 Contact the **administrator** to obtain a valid license key.

---

## ▶️ Usage

### 📊 `airtel.py` — Current Hour Report

Generates a report for the **current hour** and removes any future-hour reports to keep data clean.

```bash
python airtel.py
```

**Behavior:**
- ✅ Targets the current hour automatically
- 🧹 Deletes invalid future-hour reports before generation
- 📁 Saves fresh, validated report data

---

### 🕓 `airtel_manual.py` — Custom Range Report

Takes an **integer input** from the user and generates reports for target  hour.

```bash
python airtel_manual.py
```

**Behavior:**
- 🎯 Generates reports for `current hour - N` = `target hour`
- 🧹 Cleans up future-hour reports first
- 🔄 Ideal for backfilling or recovering missing data

---

### ⏱ `main.py` — Hourly Scheduler

Runs **continuously in the background**, automatically triggering `airtel.py` every hour.

```bash
python main.py
```

**Behavior:**
- 🔁 Executes on a precise hourly cycle
- 🧹 Handles cleanup before each generation run
- 📊 Ensures consistent, uninterrupted report history

---

## 🔁 System Behavior Summary

```
Every Hour
    │
    ▼
🧹 Delete future-hour reports
    │
    ▼
📊 Generate current hour report
    │
    ▼
✅ Save clean, valid data
    │
    ▼
⏳ Wait for next cycle...
```

- No duplicate reports
- No invalid future data
- Clean, consistent history — always ✅

---

## 🤝 Support

For licensing, access issues, or technical support, contact the project administrator.

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:FF416C,100:FF4B2B&height=120&section=footer" width="100%"/>

<sub>Built with ❤️ using Python & Playwright</sub>

</div>