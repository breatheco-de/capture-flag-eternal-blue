# ETERNAL BLUE - Remote Access on Windows 7

In this lab, you will analyze a Windows 7 system vulnerable to the famous **EternalBlue** exploit, historically used in real-world attacks. Your goal is to exploit the vulnerability, gain remote access to the system, and retrieve a flag from the user's desktop.

In this lab, you will learn:

- Detecting vulnerabilities in SMB services
- Port scanning and exploitation with `nmap` and `Metasploit`
- Using the `ms17_010_eternalblue` module
- Gaining remote access to Windows systems
- Reading flags as a compromised user

<how-to-start>

## 🌱 How to Start This Lab

Follow these instructions to get started:

1. **Download the virtual machine** from this [link]().
2. **Import the machine** into your preferred virtualization manager (VirtualBox, VMware, etc.).
3. The machine simulates a typical user environment (customized wallpaper, changed username).
4. Once the machine is running, you can start the lab!

</how-to-start>

## 📄 Instructions

You are dealing with a vulnerable Windows system. Your task is to exploit the EternalBlue vulnerability (MS17-010) to gain a remote shell and find the flag.

1. **Discover the IP address of the Windows machine.**  
    - Use tools like `nmap`, `netdiscover`, or `arp-scan` to identify its IP on the network.

2. **Scan ports and look for vulnerable services.**

3. **Launch the exploit with Metasploit.**  
    - Use the module:
      ```
      use exploit/windows/smb/ms17_010_eternalblue
      ```
    - Configure `RHOSTS`, `LHOST`, and select a payload like `windows/x64/meterpreter/reverse_tcp`.

4. **Access the system.**  
    - Once you have the shell, navigate to the user's desktop.

5. **Read the flag.**: The flag should be in a `.txt` file.

**Remember:** This type of vulnerability changed the history of cybersecurity. Use it responsibly!

Happy hacking!
