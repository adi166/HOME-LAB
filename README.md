# SETTING UP A HOME LAB 

## Objective

This project is perfect for beginners who want to start their journey in cybersecurity. It guides you through creating a basic home lab using VirtualBox, a safe and isolated environment to explore tools and techniques without risking your main system. You’ll set up and run different operating systems like Windows 10 and Kali Linux, step by step, building a strong foundation for hands-on learning.

### Skills Learned

- How to set up a VIRTUAL MACHINE on your host desktop/laptop.

### Tools Used

- VirtualBox by ORACLE 

## Steps
1. Installing VirtualBox
- Visit <a href="https://www.virtualbox.org/wiki/Downloads" target="_blank"> VirtualBox.org</a> and download the appropriate version for your operating system.
- Since I am using a Windows I am going to download Windows HOST. (If you are using a MAC machine follow the instruction on this <a href="https://cs.hofstra.edu/docs/pages/guides/vbox_mac.html "> website </a>)

2. Downloading OS Image
- After we have installed our VirtualBox we are now going to install our OS Image.
- Go to this <a href="https://www.microsoft.com/en-us/evalcenter/download-windows-10-enterprise">link</a> to download iso image file. Since I am using a 64 bit OS, I will download 64-bit ediction.
- To Install Kali Linux we are going to use prebuilt machine provided by Kali Linux itself. Download the using the given <a href="https://www.kali.org/get-kali/#kali-virtual-machines">link</a>.
- Also download <a href="https://www.7-zip.org/">7zip</a> inorder to extract files.
- Open the Documents folder. Create a new folder named Virtual Machines. Inside it, create another folder named Projects.
- Move the iso image and Kali linux in the project folder.

3. Setting up Virtual Machine (WINDOWS)
- Open VirtualBox and click on NEW. You will displayed with this screen.

![image](https://github.com/user-attachments/assets/e465d6a1-3de8-4492-bbf6-29452a374161)

- Now follow all the details accordingly.(NOTE :- tick on skip unattended installation inorder to install manually)

  ![image](https://github.com/user-attachments/assets/2a0b89c4-53e6-4fbb-8239-2e1feac0154a)

- Depending on your HOST machine hardware capabilities, select RAM and CPU Processr Count according to your needs. Then assign virtual hard disk space around 50 GB and click next. At end you would be greated with the summary, here you could check and change if you have done any mistakes. Then click on Finish.

  ![image](https://github.com/user-attachments/assets/c5a96218-12bd-4a01-b011-8a9cd825550c)

- In order to Power On you Windows VM, click on Start. Once its running we would be greated with the Windows setup. Go ahead and select next and click Install Now.
- Windows Setup would appear. Click on AGREE with liscense aggrement. CLick on CUSTOM INSTALL WINDOWS. CLick next. Now Windows 10 would be installing.

![image](https://github.com/user-attachments/assets/feab27b0-3968-4c14-83c3-8d851433db1c)

- After installing, select which keyboard layout you want. Then you would greated with login screen. Instead of using microsoft login click on Domain Join instead. Fill the following details NAME, PASSWORD, and turn off all the microsoft privacy options.

  ![image](https://github.com/user-attachments/assets/b9cfa872-9d1f-496c-9365-cce2f4180c1c)

  ![image](https://github.com/user-attachments/assets/9109c646-9968-44c8-aec0-24d3cffd7b78)

- Now you would be displayed with the WINDOWS home screen. Its in a cropped box, so inorder to get full screen follow the folloing steps. Go to devices and click on Insert Guest Addition CD Image. Go to File Explorer -> This PC -> click on VirtualBox Guest Addition -> click on VBoxWindowsAdditions-amd64. Install the following file and reboot the VM.

  ![image](https://github.com/user-attachments/assets/9e8281b3-584c-483c-ba87-2055b54c435b)

  ![image](https://github.com/user-attachments/assets/52d90c3f-aa11-474b-a290-0c678df1f168)

- Now go on View Tab and click on full screen mode.

  ![image](https://github.com/user-attachments/assets/a1ba5e98-919b-4e34-bc65-3485d4113544)

- Now you would be able to view WINDOWS in full screen.
- The above step would also allow you to copy commands and files for your host machine to your virtual machine. Inorder to enable this we need to select Devices tab in VirtualBox -> Drag and Drop -> Click on bidirectional And Go to Shared Clipboard -> click on bidirectional.

  ![image](https://github.com/user-attachments/assets/0588fd2d-25af-4f2c-9041-53a90718b2c3)

4. Setting up Virtual Machine (Kali Linux)
- In your PROJECTS folder -> extract Kali Linux file using 7-zip. Go to the extracted file -> click on kallinux vbox extension. Kali Linux would be automatically imported to your VirtualBox.

  ![image](https://github.com/user-attachments/assets/47e81a71-cfa1-44c3-914e-aba847c9d1f3)

  ![image](https://github.com/user-attachments/assets/e98c76d7-e2a7-4706-8ee1-53079c0a0b31)

  ![image](https://github.com/user-attachments/assets/ff3c7137-c010-4f37-88c2-6b3bbf637759)

5. Configuration
- In this step we are going to set up Windows in such a way that we are able to run malware or viruse on our computer. For this we need to turn off windows security.
- For this we must first take snapshot of our Windows VM. Open VirtualBox -> Open VirtualBox -> Select your Windows VM -> Go to the Snapshots tab -> Click Take Snapshot. A snapshot creates a backup of your VM, so you can restore it if something goes wrong.
  
  ![image](https://github.com/user-attachments/assets/42741d60-768c-4417-be0e-53bb12a88337)

- Start your Windows Virtual Machine. Open the search bar, type Windows Security, and select it. Go to Virus & Threat Protection. Click Manage Settings under Virus & Threat Protection Settings. Toggle Tamper Protection to Off.

![image](https://github.com/user-attachments/assets/f32bc7f3-aceb-4bb6-8f6f-463a72ca1d1e)

- Next run powershell as administrator and Run the following commands
  1. Disable real-time protection :-
    Set-MpPreference -DisableRealtimeMonitoring $true

  2. Disable the scanning of network files :-
    Set-MpPreference -DisableScanningNetworkFiles $true

  3. Disable the blocking of files at first sight :-
    Set-MpPreference -DisableBlockAtFirstSeen $true

  4. Disable Windows Defender AntiSpyware :-
    reg add "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender" /v DisableAntiSpyware /t REG_DWORD /d 1 /f

- This would disable your windows protection. 

![image](https://github.com/user-attachments/assets/3ce76a50-4d17-47ab-a655-3e930ee2ed71)

![image](https://github.com/user-attachments/assets/b1202dcf-c76f-44f7-92ad-5df8c31cbb8b)













