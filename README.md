![Banner image](asset.png)
# Guide To Hacking Android Applications using Kali Linux Tools

## Introduction
This project demonstrates how to hack mobile phones using Kali Linux tools. It allows spying on any mobile device and obtaining various details such as installed applications, geolocation, contacts, and even performing mischievous actions like playing random music files. The main technique is to create a payload using the Kali Linux terminal and send it to the victim's mobile phone. After the installation of the payload app, it sends all the data of the victim's mobile phone, granting remote access to the Android device.

## Installation
1. Install the pentesting tool lPhantom Evasion by cloning from the GitHub link: https://github.com/oddcod3/Phantom-Evasion and running the setup through the command `python3 phantom-evasion.py --setup`.
2. Use Ngrok, a cloud service that allows running a program on your machine and providing it the port of a network service, usually a web server.

## Process
### Payload Generation
1. Launch Phantom-Evasion in interactive mode using the command `python3 phantom-evasion.py`.
2. Choose the Android modules.
3. Use MSFvenom for generating the payload and save it as an APK file.
4. Set up a listener to the Metasploit framework for Android using the default `Android/meterpreter/reverse_tcp` payload.
5. Insert the LHOST (Local Host IP) and LocalPort which will be established in the Ngrok session.

### Signing the APK
Android devices only install signed APK files. Sign the APK file manually in Kali Linux using:
- Keytool (Pre-installed)
- jar signer (Pre-installed)
- zipalign (Included in Phantom Evasion)

Set the name of the generated APK file to something enticing, for example: "PUBG-mod," to increase the chances of the victim installing the app.

### Metasploit Setup
1. Use the Kali Linux tool Metasploit by entering the `msfconsole` command.
2. Use `multi/handler` and set the payload as `android/meterpreter/reverse_tcp`.
3. Set the LHOST (IP address of the hacking PC) and LPORT (typically 4444).
4. Set `ExitOnSession` to `false` to continue searching and creating sessions with the APK without restarting the hacking process.

## Potential Attacks
- Get the system information of the Android device on which the payload APK is installed.
- Get details of the installed apps on the phone.
- Get any application on the victim's mobile to run and open its main activity.
- Get detailed information about the call log of the victim's mobile.
- Maliciously play audio files on the victim's Android device.

## Warning
How to protect your android phone from such attacks?
- Don't allow downloading apps from cloud websites that ask for many unnecessary permissions.
- Don't install apps with unknown resources enabled.
- Use antivirus software on mobile devices to monitor activity.
- Always confirm the source of files before downloading.