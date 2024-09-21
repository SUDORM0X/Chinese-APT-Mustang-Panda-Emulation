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

To exploit Visual Studio Code for malicious purposes, an attacker can use either the portable version of code.exe (the executable for Visual Studio Code) or a pre-installed version of the software. By executing the command code.exe tunnel, the attacker receives a link that prompts them to log into GitHub with their own account. One of the innovative techniques employed by Stately Taurus to bypass security protections utilizes Visual Studio Code’s embedded reverse shell feature to execute arbitrary code and deploy additional payloads. Truvis Thornton detailed this technique in a Medium post: Visual Studio Code Embedded Reverse Shell (https://medium.com/@truvis.thornton/visual-studio-code-embedded-reverse-shell-and-how-to-block-create-sentinel-detection-and-add-e864ebafaf6d).

Initially, I downloaded Visual Studio Code on the Windows target machine, then logged into my GitHub account via the browser, and subsequently logged into my Visual Studio Code account through GitHub.

![366228791-f691cecf-c1c5-4404-af2a-c89589c585db (1)](https://github.com/user-attachments/assets/8144483c-6f97-46a5-9343-7644003fb535)

To complete the account linking process with Visual Studio Code, I open CMD on Windows and enter the command code tunnel. This command prompts the terminal to provide a link that we will use to finalize the authentication process.

![366228962-baaa7152-4263-4b4f-9e7e-694f2a42f52d](https://github.com/user-attachments/assets/e3ff7b17-fabf-46a5-9445-64be453f1c48)

To grant accesso to the server, log into the link and put the activation code

After running the command, the link will appear in CMD. I can then open this link in the attacker’s browser to gain control over the victim’s Visual Studio Code.

![366234421-2a7236ba-bf11-4d56-b71a-346c509f165d](https://github.com/user-attachments/assets/d6b93de4-6936-4013-9fe9-75615c8fdc78)

I now have control over the target machine through my browser in Kali Linux.

![366229616-c87e61d8-fbe6-4ef7-8b29-606aab7432fe](https://github.com/user-attachments/assets/146019b7-913d-463b-87de-050f5616e1f0)





