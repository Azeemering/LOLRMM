+++
description = "AnyDesk is a popular remote desktop software that enables users to access and control a computer or device from a remote location. It was developed with the primary goal of facilitating remote work, technical support, and collaboration between individuals and teams."
title = "AnyDesk"
weight = 10
displayTitle = "AnyDesk"
+++


{{< block "grid-1" >}}
{{< column "mt-2 pt-1">}}

# AnyDesk

**Category**: RMM

### Description

AnyDesk is a popular remote desktop software that enables users to access and control a computer or device from a remote location. It was developed with the primary goal of facilitating remote work, technical support, and collaboration between individuals and teams.

**Author**: Ali Alwashali, Nasreddine Bencherchali

**Created**: 2023-09-29

**Last Modified**: 2024-08-02

### Details

- **Website**: [https://anydesk.com/en](https://anydesk.com/en)

#### PE Metadata
- **Filename**: anydesk.exe**Original File Name**: AnyDesk.exe**Description**: AnyDesk**Product**: AnyDesk
- **Privileges**: User

- **Free**: Yes

- **Verification**: No

#### Supported Operating Systems
- Android
- ChromeOS
- IOS
- Linux
- Mac
- Windows

#### Capabilities
- File Transfer
- File System Access
- Remote Control
- GUI Support
- Command line Support

#### Known Vulnerabilities
- [https://www.cvedetails.com/vulnerability-list/vendor_id-16953/product_id-40173/Anydesk-Anydesk.html](https://www.cvedetails.com/vulnerability-list/vendor_id-16953/product_id-40173/Anydesk-Anydesk.html)

#### Installation Paths
- `C:\Program Files (x86)\AnyDesk\*`
- `C:\Program Files\AnyDesk\*`

### Forensic Artifacts

#### Disk Artifacts

- **File**: `%programdata%\AnyDesk\ad_svc.trace`
  **Description**: AnyDesk service log file. As well as ad.trace, we can determine the IP address of the other participant and its AnyDesk ID when a connection is established.

  **Example**:
  ```
  ['info 2022-08-23 10:20:11.969       gsvc   4628   3528    3                anynet.relay_conn - External address: 34.xx.xx.123:46798']
  ```

  **OS**: Windows

- **File**: `%programdata%\AnyDesk\connection_trace.txt`
  **Description**: Incoming connection logs, contains IP Address of the remote machine and file transfer activity. Only generated on target side. The content indicates how the connection was approved (e.g. the local user authorized it, or a password was used)

  **Example**:
  ```
  ['Incoming 2022-08-23, 10:23 Passwd 547911884 547911884', 'Incoming 2022-09-28, 12:39 User 442226597 442226597']
  ```

  **OS**: Windows

- **File**: `%APPDATA%\AnyDesk\connection_trace.txt`
  **Description**: Incoming connection logs, contains IP Address of the remote machine and file transfer activity. Only generated on target side. The content indicates how the connection was approved (e.g. the local user authorized it, or a password was used)

  **Example**:
  ```
  ['Incoming 2022-08-23, 10:23 Passwd 547911884 547911884', 'Incoming 2022-09-28, 12:39 User 442226597 442226597']
  ```

  **OS**: Windows

- **File**: `%APPDATA%\AnyDesk\ad.trace`
  **Description**: AnyDesk user interface log file. In this log file, we can determine the IP address of the other participant and its AnyDesk ID. It is also possible to track events of file transfer. Below is the Client ID and external IP address of the remote participant.

  **Example**:
  ```
  ['info 2022-09-28 12:39:26.845       lsvc   9952   9944   21                anynet.any_socket - Client-ID: 442226597 (FPR: 8e28a2a25b30).', 'info 2022-09-28 12:39:26.845       lsvc   9952   9944   21                anynet.any_socket - Logged in from 12.xx.xx.21:59562 on relay 80e496c0.']
  ```

  **OS**: Windows

- **File**: `%APPDATA%\AnyDesk\chat\*.txt`
  **Description**: If the chat functionality is used, its entries will be printed in a text file in this folder.


  **OS**: Windows

- **File**: `%APPDATA%\AnyDesk\user.conf`
  **Description**: N/A


  **OS**: Windows

- **File**: `%PROGRAMDATA%\AnyDesk\service.conf`
  **Description**: Password can be set to auto-validate the session. The password will be saved in a salted hash format.


  **OS**: Windows

- **File**: `%APPDATA%\AnyDesk\service.conf`
  **Description**: N/A


  **OS**: Windows

- **File**: `%APPDATA%\AnyDesk\system.conf`
  **Description**: N/A


  **OS**: Windows

- **File**: `%PROGRAMDATA%\AnyDesk\system.conf`
  **Description**: N/A


  **OS**: Windows

- **File**: `%PROGRAMDATA%\Microsoft\Windows\Start Menu\Programs\StartUp\AnyDesk.lnk`
  **Description**: N/A


  **OS**: Windows

- **File**: `%PROGRAMDATA%\Microsoft\Windows\Start Menu\Programs\AnyDesk\Uninstall AnyDesk.lnk`
  **Description**: N/A


  **OS**: Windows

- **File**: `C:\Users\*\Videos\AnyDesk\*.anydesk`
  **Description**: N/A


  **OS**: Windows

- **File**: `C:\Windows\SysWOW64\config\systemprofile\AppData\Roaming\AnyDesk\*`
  **Description**: N/A


  **OS**: Windows


#### Event Log Artifacts
- Event Details:
  - **Event ID**: 7045
  - **Provider Name**: Service Control Manager
  - **Log File**: System.evtx
  - **Service Name**: AnyDesk Service
  - **Image Path**: "C:\\Program Files (x86)\\AnyDesk\\AnyDesk.exe" --service
  - **Description**: Service installation event as result of AnyDesk installation.

#### Registry Artifacts
- **Path**: `HKLM\SOFTWARE\Clients\Media\AnyDesk`
  **Description**: N/A

- **Path**: `HKLM\SYSTEM\CurrentControlSet\Services\AnyDesk`
  **Description**: N/A

- **Path**: `HKLM\SOFTWARE\Classes\.anydesk\shell\open\command`
  **Description**: N/A

- **Path**: `HKLM\SOFTWARE\Classes\AnyDesk\shell\open\command`
  **Description**: N/A

- **Path**: `HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Print\Printers\AnyDesk Printer\*`
  **Description**: N/A

- **Path**: `HKLM\DRIVERS\DriverDatabase\DeviceIds\USBPRINT\AnyDesk`
  **Description**: N/A

- **Path**: `HKLM\DRIVERS\DriverDatabase\DeviceIds\WSDPRINT\AnyDesk`
  **Description**: N/A

- **Path**: `HKLM\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\AnyDesk`
  **Description**: N/A


#### Network Artifacts

- **Description**: During setup the boot.net.anydesk.com domain is request over port 443
  **Domain**:
    `boot.net.anydesk.com`

  **Port**: `443`

- **Description**: N/A
  **Domain**:
    `relay-[a-f0-9]{8}.net.anydesk.com:443`

  **Port**: `443`

- **Description**: N/A
  **Domain**:
    `*.anydesk.com`

  **Port**: `443`


#### Other Artifacts
- **Type**: User-Agent
  **Value**: AnyDesk/*
- **Type**: NamedPipe
  **Value**: adprinterpipe

### Detections
-   [Sigma rule](https://github.com/SigmaHQ/sigma/blob/43277f26fc1c81fc98fc79147b711189e901b757/rules/windows/builtin/system/service_control_manager/win_system_service_install_anydesk.yml)

  Anydesk Remote Access Software Service Installation


  
-   [Sigma rule](https://github.com/SigmaHQ/sigma/blob/43277f26fc1c81fc98fc79147b711189e901b757/rules/windows/file/file_event/file_event_win_anydesk_artefact.yml)

  N/A


  
-   [Sigma rule](https://github.com/SigmaHQ/sigma/blob/43277f26fc1c81fc98fc79147b711189e901b757/rules/windows/process_creation/proc_creation_win_remote_access_tools_anydesk.yml)

  N/A


  
-   [Sigma rule](https://github.com/SigmaHQ/sigma/blob/782f0f524e6f797ea114fe0d87b22cb4abaa6b7c/rules/windows/process_creation/proc_creation_win_remote_access_tools_anydesk_silent_install.yml)

  Remote Access Tool - AnyDesk Silent Installation


  

### References
- [https://support.anydesk.com/knowledge/firewall](https://support.anydesk.com/knowledge/firewall)
- [https://www.synacktiv.com/publications/legitimate-rats-a-comprehensive-forensic-analysis-of-the-usual-suspects.html](https://www.synacktiv.com/publications/legitimate-rats-a-comprehensive-forensic-analysis-of-the-usual-suspects.html)
- [https://github.com/mthcht/awesome-lists/tree/79ced75eebe53bcabf1235b3c17eb11788875482/Lists/RMM/anydesk](https://github.com/mthcht/awesome-lists/tree/79ced75eebe53bcabf1235b3c17eb11788875482/Lists/RMM/anydesk)

### Acknowledgements
- Ali Alwashali (@ali_alwashali)- Théo Letailleur (in/theosyn)

{{< /column >}}
{{< /block >}}