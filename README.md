# 30-Day-MyDFIR-Microsoft-Challenge

The purpose of this challenge is to demonstrate how to detect and respond on cloud‑based SOC lab using Micrsoft XDR to simulate detection and incident response.

### Skills Learned

  - Triaged real-world simulated alerts across Microsoft Defender and Sentinel
  - Investigated security incidents across endpoints, email, and identity using Microsoft Defender XDR
  - Documented security events and created investigation summaries aligned with MITRE ATT&CK tactics and techniques.
  - Gained hands-on experience with incident escalation, reporting, and detection tuning in a lab environment

## Tools
  - Microsoft Sentinel
  - Defender for Endpoint
  - Entra ID
  - Microsoft office 365
  - Windows 11 Operation System
  - Proton Mail

## Step Taken Before the Simulation.

  - I have onborded the test machine Window 11 VM on Azure Cloud.

  <img width="748" height="556" alt="image" src="https://github.com/user-attachments/assets/926ce34d-9bb4-46a9-872e-1bcf84ffcd09" />

  - I have onboarded the EDR agent to my test machine.

  <img width="375" height="257" alt="image" src="https://github.com/user-attachments/assets/322e2cfe-b335-4da0-946c-a046476b7dbb" />

  - I created Attack Surface Reduction (ASR) rules in Entra ID to help reduce suspicious or risky behaviors commonly used by malware on endpoints.

  <img width="831" height="815" alt="image" src="https://github.com/user-attachments/assets/92d01fe3-6995-4058-8aed-a000206519f9" />

  - I created two users for the simulation Microsoft 365 admin center.

  <img width="911" height="201" alt="image" src="https://github.com/user-attachments/assets/db907904-160a-4828-925c-32f6e99631a9" />
    
  - I created the SafeLink-Test rule in Microsoft Defender (XDR) and ensured that it includes click tracking and blocks malicious links.
  
  <img width="1906" height="913" alt="image" src="https://github.com/user-attachments/assets/9763e035-0ce0-4052-92eb-ea0872143a39" />

  - After completing the lab, I created a Conditional Access policy to block cloud app access from the country Japan in order to test whether the policy was functioning correctly. As shown in the screenshot, the policy is working as expected.
<img width="588" height="660" alt="image" src="https://github.com/user-attachments/assets/7f66b242-d6b7-4fcd-a482-37b0b484c7a6" />

<img width="1242" height="756" alt="image" src="https://github.com/user-attachments/assets/820d4328-150c-47aa-840a-a56bcee6f8b5" />

  


## Incident Scenario 

On the morning of January 27 (Tuesday), Bob and Jenny received an email from an unknown sender named Endy Eanny. Bob immediately suspected the message was a phishing attempt and reported it as phishing in Outlook. Unfortunately, Jenny clicked the link in the email and entered her username and password. When nothing happened afterward, she became suspicious and contacted the SOC team.
Later that same morning, the SOC team received the alert in Microsoft XDR indicating that a hands‑on keyboard attack had been launched from a compromised account. SOC analyst June initiated the investigation and began reviewing the suspicious activity.

## Investigation Report

| Alert                                      | Investigation Report        |
|-----------------------------------------------|----------------------------|
|    a hands‑on keyboard attack had been launched from a compromised account | <a href="https://github.com/Myo-Hset/30-Day-MyDFIR-Microsoft-Challenge/blob/main/Investigation%20Report.md">Investigation Report</a> |


## Summary

By completing this challenge, we demonstrated the ability to build a cloud‑based SOC lab and apply real‑world detection and incident response skills by configuring security controls, simulating phishing attacks, investigating alerts across multiple domains, and documenting findings in structured SOC reports.




  



