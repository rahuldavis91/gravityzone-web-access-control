# 🧪 Testing Methodology – Web Access Control (Bitdefender GravityZone)
This document describes the complete testing methodology used to validate the Web Access Control (WAC) policy, URL blacklisting, and endpoint enforcement.  
It provides SOC-style testing steps, test cases, expected behavior, and validation methods.

---

# 🎯 1️⃣ Test Environment Setup

### 🖥️ **Endpoint (Client Machine)**
- OS: **Windows 10**
- Browser(s): **Edge, Chrome, Firefox**
- BEST (Bitdefender Endpoint Security Tools) installed & up-to-date  
- Internet connection active  
- Policy assignment confirmed  

### ☁️ **GravityZone Console**
- Policy used: **Test_01 – Web Access Control**
- Features enabled:
  - Web Access Control (Category filtering)
  - Custom URL Blacklisting
  - Real-time reporting
  - Threats Xplorer monitoring

---

# 🛠️ 2️⃣ Pre-Testing Validation Steps

Before starting the main testing:

1. ✔ BEST agent connection verified (Status: Online)  
2. ✔ Policy assignment confirmed under “Network Protection → Content Control”  
3. ✔ Categories configured as **Block**  
4. ✔ Custom URLs saved and enforced  
5. ✔ WAC scheduler active for 24×7  
6. ✔ Logs retention enabled in GravityZone  

---

# 🔍 3️⃣ Test Cases & Procedures

Below are the detailed test procedures used to validate Web Access Control.

---

## 🧪 **Test Case 1 – Category Block (Gambling)**

**Goal:** Verify that category-based filtering works.

**Steps:**
1. Open browser on Windows 10  
2. Visit a known gambling test website  
3. Example:  
   - https://example-gambling-site.test  
4. Observe response

**Expected Result:**  
🚫 **Bitdefender Block Page** appears with reason “Category blocked: Gambling”

**Validation:**  
✔ Confirm block page → SCREENSHOT 03  
✔ Check logs → Threats Xplorer → Category “Website”

---

## 🧪 **Test Case 2 – Category Block (Games)**

**Steps:**
1. Visit any online gaming site  
   - example: https://free-online-games.test  
2. Browser should not load site

**Expected:**  
❌ Access denied by BEST agent

---

## 🧪 **Test Case 3 – Custom URL Blacklist (Facebook)**

**Steps:**
1. URL added in blacklist: `www.facebook.com`  
2. Open Facebook in browser  
3. Observe block behavior

**Expected:**  
🚫 BEST should block instantly

**Validation:**  
✔ Block page visible  
✔ Action logged under “Website blocked → Facebook”

---

## 🧪 **Test Case 4 – Custom URL Blacklist (Instagram)**

**Steps:**
1. Visit `www.instagram.com`  
2. Observe browser

**Expected:**  
🚫 Block page appears  
(with GravityZone block message)

**Validation:**  
✔ Screenshot stored in `/screenshots/02-url-blacklist.png`

---

## 🧪 **Test Case 5 – Allowed URL Override**

**Goal:** Validate allow rule priority in blacklist.

**Steps:**
1. URL/IP marked as **Allow**: `192.168.248.140`  
2. Visit this IP in browser  
3. Observe

**Expected:**  
✔ Page must load normally  
✔ No block event should be generated

---

## 🧪 **Test Case 6 – Mixed Category + URL Exception**

**Steps:**
1. Add website under a blocked category (e.g., Social Networks)  
2. Also add the same website in **Allow List**  
3. Load website

**Expected Behavior:**  
✔ If Allow List takes priority → Site loads  
✔ If Category overrides → Block page appears

(This tests real-world conflict resolution)

---

# 📊 4️⃣ Logs & Monitoring Validation

After each test, the following logs were checked:

### 📍 **Threats Xplorer → General View**
- Action: **Blocked**  
- Category: **Website**  
- URL details  
- Endpoint name: *Rahulkumar*  
- Timestamp  
- Reason: *Content Control*  

### 📍 **WAC Scheduler Logs**  
Used to confirm whether schedule-based execution was correct.

### 📍 **URL Blacklist Logs**  
Verified if blacklist entries were matched correctly.

All results stored in:  
`/screenshots/04-logs.png`

---

# 🧩 5️⃣ Negative Testing (Edge Cases)

These tests ensure system is reliable in tricky situations:

- 🔸 Open site in **Incognito mode** → Still blocked  
- 🔸 Change browser → Still blocked  
- 🔸 Use “http” instead of “https” → Still blocked  
- 🔸 Try with VPN / Proxy → BEST still enforces control  
- 🔸 Disable browser security → BEST still blocks  

✔ Result: All negative tests worked as expected.

---

# 🔚 6️⃣ Final Conclusion

The Web Access Control implementation successfully:

- Blocked risky website categories  
- Enforced custom URL blacklisting  
- Displayed block page consistently  
- Logged all attempts in Threats Xplorer  
- Allowed exception rules correctly  
- Demonstrated enterprise-level policy control  

This testing methodology proves the WAC configuration is functional, robust, and SOC-ready.

---
