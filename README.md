# Chinese-APT-Mustang-Panda-Emulation
This is a simulation of an attack carried out by the APT group (Mustang Panda), targeting government entities in Southeast Asia. The attack campaign was active from late September 2023. The attack chain begins with the abuse of Visual Studio Code's reverse shell to execute arbitrary code and deploy additional payloads.
 To abuse Visual Studio Code for malicious purposes, an attacker can use the portable version of code.exe (the executable file for Visual Studio Code), or an already installed version of the software. By running the command code.exe tunnel, an attacker receives a link that requires them to log into GitHub with their own account, I relied on paloalto to figure out the details to make this simulation: https://unit42.paloaltonetworks.com/stately-taurus-abuses-vscode-southeast-asian-espionage/
![mp_full_v2-scaled](https://github.com/user-attachments/assets/3bb8f97a-b7e1-4e1d-9d4f-abffbe6ffd85)

It's important to emphasize that this project is intended solely for educational and research purposes. Any unauthorized use may result in legal consequences.


This attack involved several stages, including a redirection to a Visual Studio Code web environment connected to the compromised machine. From there, the attackers could execute commands and scripts, as well as create new files on the infected system. The APT group Stately Taurus used this technique to deliver malware to infected environments, conduct reconnaissance, and exfiltrate sensitive data. To maintain persistent access to the reverse shell, the attacker created a scheduled task to run a script called "startcode.bat," which was responsible for initiating the reverse shell.

1) They used Visual Studio Code’s reverse shell to execute arbitrary code and deploy additional payloads.

2) Additionally, the attackers utilized ToneShell to archive files for exfiltration, securing the RAR archives with a unique password.


![word-image-391402-136600-1](https://github.com/user-attachments/assets/3fc6c7e2-8ab6-4d5e-9fd8-a7ddd8777156)


## 1° STAGE - DELIVERY
