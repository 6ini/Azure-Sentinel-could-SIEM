# Azure-Sentinel-could-SIEM
Built cloud SIEM using Azure sentinel

# Azure Sentinel (SIEM) - Cloud Security Detection Lab

## 📝 Project Overview
This project focuses on building a cloud-native SIEM (Security Information and Event Management) solution using **Microsoft Sentinel**. The primary objective was to detect and investigate unauthorized resource deployments (specifically Azure Key Vaults) within a cloud environment. I ingested Azure Activity Logs, configured custom analytics rules using **KQL (Kusto Query Language)**, and successfully simulated an attack to validate the detection pipeline.

###  Technologies Used
* **Microsoft Sentinel** (SIEM/SOAR)
* **Azure Monitor** (Log Ingestion)
* **KQL** (Kusto Query Language)
* **Azure Key Vault** (Target Resource)
* **Microsoft Defender for Cloud** (Incident Management)

---

##  Project Steps & Evidence

### 1. Log Analysis (Blue Team)
I verified the attack by querying the raw logs. The query confirmed the unauthorized action was captured with the status `Success`.

![Evidence Log](All%20types%20of%20logs.png)

### 2. The Alert (Detection)
The analytics rule successfully triggered a **High-Severity Incident** based on the custom logic I engineered.

![Detection Alert](Incident%20for%20key%20vault.png)

### 3. Incident Response (Triage)
I triaged the alert in Microsoft Defender, assigned it to the SOC (myself), classified it as a "True Positive," and resolved the case.

![Incident Resolution](Ticketing%20Incident%20.png)

---

##  Future Improvements
* Integrate **Logic Apps (SOAR)** to automatically block the user or delete the unauthorized Key Vault upon detection.
* Expand the KQL query to detect Key Vaults created in non-approved regions (e.g., outside 'East US').
