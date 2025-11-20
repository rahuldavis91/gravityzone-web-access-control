# Web Access Control using Bitdefender GravityZone

This project demonstrates how I implemented Web Access Control using Bitdefender GravityZone Business Security.  
It includes:  
- Category-based Web Filtering  
- Custom URL Blacklisting  
- Endpoint Enforcement Testing  
- Log Monitoring using Threats Xplorer  

---

## 🔧 Tools Used
- Bitdefender GravityZone (Cloud Console)
- Bitdefender Endpoint Security Tools (BEST)
- Windows 10 endpoint

---

## 📌 1. Policy Creation (Category-Based Filtering)
Configured Web Access Control with multiple blocked categories including Gambling, Games, Adult Content, Hacking, Hate, etc.

📸 **Screenshot:**  
`/screenshots/01-policy-creation.png`

---

## 📌 2. Custom URL Blacklisting
Blocked specific test URLs such as social media and test sites to validate the blacklist.

📸 **Screenshot:**  
`/screenshots/02-url-blacklist.png`

---

## 📌 3. Endpoint Enforcement Test
Attempted to access blocked websites on Windows 10 → Bitdefender Endpoint blocked the request.

📸 **Screenshot:**  
`/screenshots/03-blocked-page.png`

---

## 📌 4. Log Monitoring (Threats Xplorer)
Verified logs for all blocked attempts in GravityZone → Threats Xplorer.

📸 **Screenshot:**  
`/screenshots/04-logs.png`

---

## 🎯 Skills Demonstrated

- Endpoint Security
- Web Access Control
- URL Filtering
- Policy Enforcement
- SOC-style Event Monitoring
- Log Analysis
- Cloud Console Management

---

## 📂 Project Structure

bitdefender-web-access-control/
│
├── README.md
└── screenshots/
├── 01-policy-creation.png
├── 02-url-blacklist.png
├── 03-blocked-page.png
└── 04-logs.png
