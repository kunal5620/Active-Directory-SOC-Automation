# Active Directory SOC Automation Project – Unauthorized Login Response
![Alt text](https://github.com/kunal5620/Active-Directory-SOC-Automation/blob/main/Architecture/Active%20Directory%202.0.drawio.png)
## 📌 Project Overview
This project demonstrates an **automated SOC incident response workflow** for handling **unauthorized or suspicious Active Directory logins**.

The solution integrates **Splunk**, **Shuffle SOAR**, **Active Directory**, and **Slack** to enable **analyst-in-the-loop decision making**, where security analysts can choose to automatically **disable a domain user account** or take no action.

---

## 🎯 Objectives
- Detect unauthorized or suspicious logins using **Splunk**
- Automate alert ingestion into **Shuffle**
- Retrieve **Active Directory user attributes**
- Notify SOC analysts via **Slack**
- Allow analysts to decide whether to **disable the domain user**
- Execute response actions in **Active Directory**

---

## 🛠 Tools & Technologies
- **Splunk** – SIEM & Alerting
- **Shuffle** – SOAR Automation Platform
- **Active Directory (Windows Server)**
- **Slack** – SOC Notifications
- **Virtual Machines (Lab Environment)**
- **Webhooks & APIs**

---

## 🏗 Lab Architecture
The lab environment consists of:

- **Windows Domain Controller**
  - Hosts Active Directory
- **Windows Test Machine**
  - Generates authentication events
- **Splunk Server (Ubuntu)**
  - Receives telemetry from Windows systems
- **Shuffle SOAR**
  - Orchestrates automated response actions

### Architecture Flow
1. Authentication events are generated on Windows systems
2. Logs are forwarded to Splunk
3. Splunk detects suspicious or unauthorized login activity
4. Alert is sent to Shuffle via webhook

---

## 🔄 SOC Automation Workflow

### 🔹 Step-by-Step Workflow
1. **Splunk Alert Trigger**
   - Splunk detects a successful but unauthorized login
   - Alert is forwarded to Shuffle

2. **User Attribute Enrichment**
   - Shuffle queries **Active Directory**
   - Retrieves user attributes and account details

3. **SOC Analyst Decision**
   - Alert details are sent to **Slack**
   - Analyst is prompted to choose:
     - ✅ Disable domain user
     - ❌ Take no action

4. **Automated Response**
   - If **YES** → Shuffle disables the AD user account
   - If **NO** → Workflow stops with no action taken

5. **Notification**
   - SOC team is notified of the final action taken

---

## 🧠 Use Case: Unauthorized Active Directory Login

### 🔍 Detection
- Successful authentication from suspicious source
- Abnormal login behavior
- Potential compromised credentials

### 🛡 Response
- Analyst-approved account disablement
- Prevents further lateral movement
- Reduces response time

---

## 📸 Workflow Diagrams
- SOC Architecture Diagram
- Shuffle Automation Workflow

