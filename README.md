# 30-Day MyDFIR Microsoft Challenge: Cloud SOC & XDR Investigation

## Objective
This project demonstrates threat detection and incident response capabilities within a cloud-based SOC environment using Microsoft Defender XDR and Microsoft Sentinel. The challenge focuses on simulating real-world attacks, triaging alerts, and executing full-cycle incident response across endpoints, identities, and email.

### Skills Learned
* **Alert Triage:** Analyzed and triaged real-world simulated alerts across Microsoft Defender XDR and Microsoft Sentinel.
* **Cross-Domain Investigation:** Hunted for security incidents across endpoints (EDR), email workloads, and cloud identities.
* **Incident Documentation:** Documented security events and created investigation summaries aligned with MITRE ATT&CK tactics and techniques.
* **Security Engineering:** Gained hands-on experience with incident escalation, reporting, preventative policy creation, and detection tuning in an enterprise lab environment.

### Tools & Technologies Used
* **Microsoft Sentinel** (Cloud-native SIEM)
* **Microsoft Defender for Endpoint** (EDR)
* **Microsoft Entra ID** (Identity and Access Management)
* **Microsoft 365 Defender** (Email and Collaboration Security)
* **Windows 11 Operating System** (Azure Virtual Machine)
* **Proton Mail** (External attacker email simulation)

---

## Pre-Simulation Configuration (Lab Setup)

Before executing the attack scenario, I provisioned and secured the cloud infrastructure to ensure proper telemetry collection and policy enforcement:

* **Endpoint Provisioning:** I deployed and onboarded a Windows 11 test virtual machine within Azure Cloud.
<img width="748" height="556" alt="image" src="https://github.com/user-attachments/assets/926ce34d-9bb4-46a9-872e-1bcf84ffcd09" />

* **EDR Deployment:** I successfully onboarded the Microsoft Defender for Endpoint (MDE) agent to the test machine to capture advanced host-level telemetry.
<img width="375" height="257" alt="image" src="https://github.com/user-attachments/assets/322e2cfe-b335-4da0-946c-a046476b7dbb" />

* **Attack Surface Reduction (ASR):** I created ASR rules in Microsoft Entra ID to proactively block suspicious or risky behaviors commonly leveraged by malware on Windows endpoints.
<img width="831" height="815" alt="image" src="https://github.com/user-attachments/assets/92d01fe3-6995-4058-8aed-a000206519f9" />

* **Identity Creation:** I provisioned two test user accounts (Bob and Jenny) within the Microsoft 365 Admin Center to serve as targets for the phishing simulation.
<img width="911" height="201" alt="image" src="https://github.com/user-attachments/assets/db907904-160a-4828-925c-32f6e99631a9" />
    
* **Email Security (Safe Links):** I created a `SafeLink-Test` rule in Microsoft Defender XDR, enabling click-tracking and automatic blocking of known malicious URLs.
<img width="1906" height="913" alt="image" src="https://github.com/user-attachments/assets/9763e035-0ce0-4052-92eb-ea0872143a39" />

* **Identity Protection (Conditional Access):** To validate access controls, I created a Conditional Access policy in Microsoft Entra ID designed to block all cloud app authentications originating from Japan. The screenshots below validate that the geographic block is functioning exactly as expected.
<img width="588" height="660" alt="image" src="https://github.com/user-attachments/assets/7f66b242-d6b7-4fcd-a482-37b0b484c7a6" />
<img width="1242" height="756" alt="image" src="https://github.com/user-attachments/assets/820d4328-150c-47aa-840a-a56bcee6f8b5" />

---

## Incident Scenario

On the morning of Tuesday, January 27th, two employees (Bob and Jenny) received a suspicious email from an unknown external sender named "Endy Eanny." 

Bob immediately identified the threat and reported it using the Outlook Phish button. Unfortunately, Jenny clicked the malicious link embedded in the email and submitted her corporate username and password into a credential-harvesting page. When the page failed to load a subsequent prompt, she became suspicious and escalated the issue to the SOC team.

Later that same morning, the SOC received a high-severity alert in Microsoft Defender XDR indicating that **"A hands-on keyboard attack had been launched from a compromised account."** Acting as the responding SOC Analyst, I initiated a full investigation to track the threat actor's movements across our cloud environment.

---

## Investigation Report

The table below links to the full incident write-up, detailing the timeline of the attack, the telemetry analyzed, and the remediation steps taken to secure the compromised user and endpoint.

| Alert Name                                                              | Investigation Report          |
|-------------------------------------------------------------------------|-------------------------------|
| A hands-on keyboard attack had been launched from a compromised account | <a href="https://github.com/Myo-Hset/30-Day-MyDFIR-Microsoft-Challenge/blob/main/Investigation%20Report.md">View Full Investigation Report</a> |

---

## Summary

By completing this challenge, I demonstrated the ability to architect a cloud-based SOC lab and apply real-world incident response methodologies. This included configuring preventative security controls, simulating credential-harvesting phishing attacks, hunting across multiple Microsoft security domains, and documenting the findings in a structured, professional SOC investigation report.
