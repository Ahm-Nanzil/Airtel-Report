# 📡 Airtel Report Automation

Automated Airtel reporting system built using **Python + Playwright**.

---

## 📌 Overview

This project provides:

- ⏱ Hourly automated report generation  
- 📊 Current hour report (`airtel.py`)  
- 🕓 Custom range report (`airtel_manual.py`)  
- 🔁 Scheduled execution (`main.py`)  
- 🧹 Automatic deletion of future-hour reports before regeneration  

---

## 📂 Project Structure

```text
Airtel-Report/
│
├── __pycache__/
├── pyarmor_runtime_000000/
├── airtel.py
├── airtel_manual.py
├── main.py
├── credentials.txt
├── license_check.py
├── license.key
└── venv/
⚙️ Requirements
Windows 10 or later
Python 3.10+
Internet connection
Airtel portal credentials
🔑 Valid license key from administrator (required to run scripts)
🛠️ Installation
1. Clone Repository
git clone https://github.com/Ahm-Nanzil/Airtel-Report.git
cd Airtel-Report
2. Create Virtual Environment
python -m venv venv
3. Activate Environment
venv\Scripts\activate
4. Upgrade pip
python -m pip install --upgrade pip
5. Install Dependencies
python -m pip install playwright cryptography
6. Install Playwright Browsers
python -m playwright install
🔐 Credentials Setup

credentials.txt

Add:

USERNAME=your_email_here
PASSWORD=your_password_here
🔑 License Requirement
A valid license.key is required to run the project
Contact the administrator to obtain a valid license
▶️ Usage & Script Behavior
📊 airtel.py (Current Hour Report)
Generates report for the current hour
Deletes any future-hour reports before generating
Ensures only valid latest data exists

Run:

python airtel.py
🕓 airtel_manual.py (Custom Range Report)
Takes user input (Integer)

Generates reports for:

current hour - given input

Deletes future-hour reports before generating
Useful for backfilling or regenerating missing reports

Run:

python airtel_manual.py
⏱ main.py (Scheduler)
Runs continuously in the background
Automatically triggers airtel.py every hour
Handles:
Scheduled execution
Future report cleanup
Consistent hourly data generation

Run:

python main.py
🔁 Overall Behavior
System runs on an hourly cycle
Always deletes future reports before generating new ones
Prevents duplicate or invalid data
Maintains clean and consistent report history