# 🛡️ Bitdefender GravityZone – Web Access Control Policy Details
This document contains the complete configuration details of the Web Access Control (WAC) policy used for this project.  
It explains exactly which categories were blocked, how URL blacklisting was applied, and what settings were used to enforce web restrictions on the endpoint.

---

## 📌 Policy Name  
**Test_01 – Web Access Control Policy**

---

# 1️⃣ Web Access Control (WAC) – Overview  
The Web Access Control policy was configured to manage and restrict internet access for the endpoint.  
This included:

- 🔒 Category-based filtering  
- 🔗 Custom URL blocking  
- 🕒 Scheduled blocking (24×7)  
- 🖥️ Enforcement on Windows 10 endpoint  

Policy Location:  
**Policies → Test_01 → Network Protection → Content Control**

---

# 2️⃣ Category-Based Web Filtering (Block List)

The following categories were selected and configured to **Block**:

| Category | Action |
|---------|--------|
| Gambling | Block |
| Games | Block |
| Government | Block |
| Hacking | Block |
| Hate | Block |
| Health | Block |
| Ads | Block |
| Adult Content | Block |
| Alcohol | Block |
| Astrology | Block |
| Blogs | Block |
| Business | Block |
| Education | Block |
| Entertainment | Block |
| File Sharing | Block |
| Financial | Block |
| Food | Block |
| Hosting | Block |
| Job Search | Block |
| Kids | Block |
| Life Style | Block |
| Mature Content | Block |
| Narcotics | Block |
| News | Block |
| Occult | Block |
| Online Shopping | Block |
| Photography | Block |
| Pornography | Block |
| Radio | Block |
| Real Estate | Block |
| Religion | Block |
| Scams | Block |
| Social Networks | Block |
| Society | Block |
| Software Piracy | Block |
| Sports | Block |
| Suicide | Block |
| Tabloids | Block |
| Time Wasters | Block |
| Tobacco | Block |
| Travel | Block |
| Videos | Block |
| Violence | Block |
| Web Mail | Block |
| Web Proxy | Block |

📝 **Note:**  
All categories were placed under one scheduler named **“All Sites Block”** covering all days → 00:00 to 23:59.

---

# 3️⃣ Custom URL Blacklist

Along with category filtering, specific URLs were manually added to the blacklist.

| URL | Permission |
|-----|------------|
| www.instagram.com | Block |
| en.wikipedia.org | Block |
| 192.168.248.140 | Allow |
| www.facebook.com | Block |
| testbook.com | Block |

Purpose:
- To simulate enterprise-level content filtering.
- To validate that custom URLs override category settings.
- To test manual site-level restrictions.

---

# 4️⃣ Application Blacklisting  
Status → **Enabled**  

This ensures that restricted applications (if configured) cannot bypass web filtering and network controls.

No individual apps were blocked for this project, but the module was enabled for policy completeness.

---

# 5️⃣ Scheduler Configuration (WAC Scheduler)

Scheduler Name: **All Sites Block**

- 🕒 Time Range: 00:00 – 23:59  
- 📅 Days: Mon, Tue, Wed, Thu, Fri, Sat, Sun  
- Categories included: **All selected categories**  
- Purpose: Ensure 24×7 enforcement without break

---

# 6️⃣ Policy Enforcement Result Summary

- Attempts to access Facebook, Instagram, YouTube (logged), and Testbook resulted in **Block Page** being displayed.
- Custom “Allow” rule for local IP **192.168.248.140** worked successfully.
- All events recorded under **Threats Xplorer → Website category → Blocked**.

---

# 7️⃣ Endpoint Details (Where Policy Applied)
- System: **Windows 10**
- Browser used for testing: **Edge / Chrome / Firefox**
- BEST agent installed and connected to GravityZone
- Policy applied via **Assignment Rules**

---

# 8️⃣ Verification Logs (Threats Xplorer)
All blocked attempts were successfully logged:

Data includes:

- URL  
- Category  
- Action Taken (Blocked)  
- Endpoint Name  
- Timestamp  

These are visible in the screenshot:  
`/screenshots/04-logs.png`

---

# ✔️ Conclusion  
This Web Access Control policy successfully implemented enterprise-grade:

- Category Filtering  
- URL Blacklisting  
- Continuous 24×7 enforcement  
- Real-time endpoint control  
- SOC-ready logging and monitoring  

This documentation serves as a complete reference for how the WAC policy was configured and validated in Bitdefender GravityZone.

---
