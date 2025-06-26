# Phishing-Analysis
#  Phishing Email Analysis Project

##  Objective

The goal of this project is to **analyze a suspicious email** and **identify indicators of phishing** to raise awareness about social engineering threats. Understanding how to dissect a phishing email is essential for improving cybersecurity practices both personally and professionally.

---

##  Tools Used

-  Email client (e.g., Outlook, Thunderbird) or `.eml` / `.txt` email file
-  [MXToolbox Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx) – for examining email headers
-  Manual inspection of:
  - Email body content
  - Links
  - Sender address
  - Header fields

---

##  Sample Email (Sanitized for Safety)

Below is a sample suspicious email used for the analysis:

From: PayPal Security security-update@paypa1.com
Subject: Urgent: Your Account Has Been Locked!
Date: Mon, 10 June 2024 09:32:17 +0000

Dear Customer,

We noticed unusual activity in your PayPal account and have temporarily limited its functionality for your protection.

Please verify your account by clicking the link below:

Verify Now

If you do not verify within 24 hours, your account will be permanently suspended.

Thank you,
PayPal Security Team


---

##  Step-by-Step Analysis

###  Step 1: Check Email Header
Use [MXToolbox](https://mxtoolbox.com/EmailHeaders.aspx) or your email client’s **"View Raw Header"** feature.

**Indicators:**
- `Return-Path`: does not match official PayPal domain.
- `Received:` IP address traced to a foreign or suspicious hosting provider.
- `Reply-To:` different than `From:` → classic phishing trick.

---

###  Step 2: Analyze Sender Address
**From:** `security-update@paypa1.com`  
- The domain is misspelled (`paypa1.com` instead of `paypal.com`)
- The domain is not registered by PayPal → indicates spoofing.

---

###  Step 3: Analyze URLs and Links
**Link text:** `Verify Now`  
**Actual URL:** `http://paypa1.com.verify-account-login.in/secure`

- Uses **misleading subdomains** and **typosquatting**
- No **HTTPS encryption**
- Clearly **not a PayPal-owned domain**

 Use tools like:
- [VirusTotal](https://www.virustotal.com/)
- [URLVoid](https://www.urlvoid.com/)

---

###  Step 4: Inspect the Message Content

#### Phishing Indicators in Content:
- Generic greeting: *“Dear Customer”* (not personalized)
- Urgent tone and threat: *“account will be permanently suspended”*
- Grammatical issues: *“verify within 24 hours”* (poor language)
- No digital signature (e.g., DKIM, SPF fail in headers)

---

## 📊 Summary of Phishing Indicators

| Indicator | Description |
|----------|-------------|
|  Misspelled domain | `paypa1.com` instead of `paypal.com` |
|  Generic greeting | Not addressed to the user personally |
|  Urgency and fear | Threats of account suspension |
|  Suspicious links | Fake URLs redirecting to malicious sites |
|  Header anomalies | `Reply-To` differs from `From`, SPF/DKIM failed |
|  Poor grammar | Unprofessional tone and mistakes |

---


---

##  Lessons Learned

- Always verify sender domains and URLs before clicking.
- Legitimate organizations do not ask for personal credentials via email.
- Email headers can reveal a lot about the true source of a message.
- Use browser security plugins or endpoint tools to detect phishing attempts.

---

##  Deliverable

- A clear report documenting the **phishing indicators found** in the sample email.

You may also create a `.pdf` or `.md` version of the report for submission or sharing.

---

##  References

- [How to Read Email Headers](https://www.cisco.com/c/en/us/support/docs/security/email-security-appliance/212999-how-to-read-email-headers.html)
- [PayPal Phishing Guidelines](https://www.paypal.com/us/webapps/mpp/security/suspicious-email)

---

###  Stay Alert. Think Before You Click!


