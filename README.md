
# **PowerShell Cheat Sheet**

## **Overview**
Welcome to the PowerShell Cheat Sheet repository! This repository is a compilation of all PowerShell cmdlets, labs, and classwork completed during the course. It serves as a quick reference and a valuable learning resource for mastering PowerShell.

## **Table of Contents**
## 1. [Introduction]
## 2. [Cmdlets Overview]
## 3. [Labs]
  - [Lab 1: Server Core and ADDS Setup]
  - [Lab 2: PowerShell Automation and PSRemoting]
  - [Lab 3: File Shares and Permissions]
  - [Lab 4: AD Management]
## 4. [Classwork]
   - Classwork 1
   - Classwork 2
   - Classwork 3
   - Classwork 4
   - Classwork 5
   - Classwork 6
   - Classwork 7
   - Classwork 8
   - Classwork 9
   - Classwork 10


---

## **Introduction**

This repository contains:
- Descriptions and practical examples of cmdlets.
- Step-by-step summaries of lab exercises.
- Custom scripts and solutions for classwork assignments.


---

## **Cmdlets Overview**
**Cmdlets Overview** section, detailing their functions and examples:

**1. Get-Help**
- **Description**: Provides detailed information about cmdlets, including syntax, examples, and parameters.
- **Syntax**:
  Get-Help <Cmdlet-Name>
- **Example**:
  Get-Help Get-Service

**2. Set-ExecutionPolicy**
- **Description**: Configures the execution policy for running PowerShell scripts.
- **Syntax**:
  Set-ExecutionPolicy <Policy> [-Scope <Scope>]
- **Example**:
  Set-ExecutionPolicy RemoteSigned

**3. Export-Csv**
- **Description**: Exports objects to a CSV file.
- **Syntax**:
  Export-Csv -Path <FilePath> -NoTypeInformation
- **Example**:
  Get-Process | Export-Csv -Path "Processes.csv" -NoTypeInformation

**4. Select-Object**
- **Description**: Selects specified properties of an object or a set of objects.
- **Syntax**:
  Select-Object -Property <PropertyNames>
- **Example**:
  Get-Service | Select-Object -Property Name, Status

**5. Get-Process**
- **Description**: Retrieves information about processes running on a computer.
- **Syntax**:
  Get-Process [-Name <String[]>]
- **Example**:
  Get-Process -Name "notepad"

**6. Stop-Process**
- **Description**: Stops one or more running processes.
- **Syntax**:
  Stop-Process [-Name <String[]>]
- **Example**:
  Stop-Process -Name "notepad"

**7. Get-Service**
- **Description**: Retrieves the status of services on a local or remote machine.
- **Syntax**:
  Get-Service [-Name <String[]>]
- **Example**:
  Get-Service -Name "wuauserv"

**8. Get-WMIObject**
- **Description**: Retrieves instances of WMI classes or information about the available classes.
- **Syntax**:
  Get-WmiObject -Class <ClassName> [-Namespace <Namespace>]
- **Example**:
  Get-WmiObject -Class Win32_BIOS

**9. Get-EventLog**
- **Description**: Retrieves event log entries from local or remote computers.
- **Syntax**:
  Get-EventLog -LogName <LogName> [-Newest <Int32>]
- **Example**:
  Get-EventLog -LogName "Application" -Newest 10
  
**10. Get-Content**
- **Description**: Reads the contents of a file.
- **Syntax**:
  Get-Content -Path <FilePath>
- **Example**:
  Get-Content -Path "Processes.csv"

**11. Get-NetAdapter**
- **Description**: Retrieves information about network adapters.
- **Syntax**:
  Get-NetAdapter [-Name <String[]>]
- **Example**:
  Get-NetAdapter

**12. New-ADUser**
- **Description**: Creates a new Active Directory user account.
- **Syntax**:
  New-ADUser -Name <String> -SamAccountName <String> -UserPrincipalName <String>
- **Example**:
  New-ADUser -Name "John Doe" -SamAccountName "jdoe" -UserPrincipalName "jdoe@contoso.com"

**13. Install-WindowsFeature**
- **Description**: Installs specified roles, role services, or features on a server.
- **Syntax**:
  Install-WindowsFeature -Name <FeatureName>
- **Example**:
  Install-WindowsFeature -Name AD-Domain-Services

**14. Get-CimInstance**
- **Description**: Retrieves information about CIM instances of a class.
- **Syntax**:
  Get-CimInstance -ClassName <ClassName>
- **Example**:
  Get-CimInstance -ClassName Win32_BIOS

**15. ConvertTo-Html**
- **Description**: Converts objects into HTML format.
- **Syntax**:
  ConvertTo-Html [-Property <String[]>] -Path <FilePath>
- **Example**:
  Get-Process | ConvertTo-Html -Path "Processes.html"

  ---
  
## **Labs**

**Lab 1: Server Core and ADDS Setup**

**Summary:** In this lab, the focus is on configuring network settings, installing Active Directory Domain Services (AD DS), and preparing a Server 2022 Core VM. The tasks include setting static IPs, installing roles, and using PowerShell for system configuration.

**Key Cmdlets:**
- New-NetIPAddress: Configures a static IP address for the network adapter.
- Install-WindowsFeature: Installs server roles and features (e.g., AD DS, management tools).
- Add-WindowsFeature: Adds features like AD DS, DNS, etc.
- Get-WindowsFeature: Lists installed features and roles on a system.
- Set-ExecutionPolicy: Changes the script execution policy to allow script running.
- Install-ADDSForest: Installs a new Active Directory Domain Services forest.
- Get-ADDomainController: Retrieves domain controller information.
- New-ADUser: Creates a new Active Directory user.
- Get-ADUser: Retrieves details of an Active Directory user.
- Set-ADUser: Modifies user attributes.

**Lab 2: PowerShell Automation and PSRemoting**

**Summary**: This lab involves creating PowerShell scripts to automate tasks such as network configuration, security settings, domain joining, role installations, and remote execution.
 
**Key Cmdlets**:
- New-ScriptFile: Creates new script files for automation.
- Set-TimeZone: Configures the system time zone.
- Set-ItemProperty: Modifies registry settings (e.g., for IE security settings).
- Add-Computer: Joins the server to the domain.
- New-NetIPAddress: Configures network IP addresses in scripts.
- Disable-IEFeature: Disables security features of Internet Explorer for administrators.
- Set-ExecutionPolicy: Allows or prevents scripts from running.
- Get-Help: Retrieves information about cmdlets and scripts.
- Invoke-Command: Executes scripts on remote computers using PowerShell Remoting.

**Lab 3: File Shares and Permissions**

**Summary**: The lab focuses on user management, file sharing, and permission configuration. You will create users, set up SMB shares, and configure permissions based on the user's roles.

**Key Cmdlets:**
- New-ADUser: Creates new Active Directory users.
- Set-ADUser: Updates user attributes such as group membership.
- New-SmbShare: Creates SMB file shares for sharing files across the network.
- Set-SmbShare: Modifies properties of an SMB share.
- Add-ADGroupMember: Adds users to Active Directory groups.
- Get-SmbShare: Lists the SMB shares on the machine.
- Get-ADGroup: Retrieves details about Active Directory groups.
- Get-ADUser: Retrieves user information from Active Directory.
- Get-SmbShareAccess: Displays permissions on SMB shares.
- Get-ADUser: Fetches user attributes from AD.
- Export-CSV: Exports user data to a CSV file for easy reference.

**Lab 4: AD Management**

**Summary:** This lab focuses on managing Active Directory users, organizational units (OUs), and groups using PowerShell. It involves importing users from a CSV file, creating OUs, and performing user account management tasks such as resetting passwords and disabling accounts.

**Key Cmdlets:**
- Import-Csv: Imports user data from a CSV file for bulk user creation.
- New-ADOrganizationalUnit: Creates a new Organizational Unit (OU) in Active Directory.
- Move-ADObject: Moves objects (like users) to different OUs.
- New-ADGroup: Creates new Active Directory groups.
- Add-ADGroupMember: Adds users to Active Directory groups.
- Set-ADUser: Modifies user properties like password reset or account status.
- Get-ADUser: Retrieves user information for verification.
- Enable-ADAccount: Enables a disabled user account.
- Disable-ADAccount: Disables a user account.
- Unlock-ADAccount: Unlocks a locked user account.
- Remove-ADUser: Deletes a user account from Active Directory.
- Get-ADGroupMember: Lists members of a specified AD group.

---

## **Classwork**

**Classwork 1: PowerShell Console Customization**

**Summary**: This classwork involves customizing the PowerShell console in Windows Server 2022 by adjusting font, colors, layout, and enabling elevated privileges by default. Additionally, students are required to test various basic cmdlets like Write-Host and Get-History and interact with the console.

**Key Steps**:
- Display the PowerShell version using $host.version.
- Pin PowerShell to the taskbar and configure properties for elevated privileges, font size, colors, and layout.
- Enable QuickEdit Mode and Insert Mode for easier text selection and editing.
- Experiment with Write-Host, Get-Service, Get-History, and Invoke-History cmdlets.
- Test QuickEdit mode by copying text from Notepad into PowerShell.
  
**Key Cmdlets**:
- $host.version: Displays the PowerShell version.
- Write-Host: Prints text to the screen.
- Get-Service: Retrieves the status of services.
- Get-History: Lists previous commands entered.
- Invoke-History: Re-runs a command from history.

**Classwork 2: Exploring Get-Help**

**Summary**: This classwork focuses on using the Get-Help cmdlet to explain various PowerShell commands. Students must provide screenshots of the Get-Help output and write brief explanations of the commands' functions.

**Key Cmdlets**:
- Get-Help: Provides information about PowerShell cmdlets and concepts.
- Set-ExecutionPolicy: Configures the script execution policy.
- Export-CSV: Exports data to a CSV file format.
- Select-Object: Selects specific properties from objects.
- Get-Process: Retrieves information about running processes.
- Stop-Process: Terminates running processes.
- Get-Service: Retrieves details of services on a machine.
- Get-WMIObject: Queries WMI objects for system information.
- Get-EventLog: Retrieves event log entries from the system.
- Get-Content: Reads the content of files.
- Get-NetAdapter: Retrieves information about network adapters.

**Classwork 3: Working with Data**

**Summary**: This task focuses on using PowerShell cmdlets to create, manipulate, and query CSV files and system logs. You will also perform actions on processes, services, and event logs.

**Key Steps**:
- Create a CSV File: Use Get-Service to export all running services to a CSV file.
- Read the CSV File: Use Get-Content and Import-CSV to read the CSV file. Understand the differences in how each cmdlet handles data.
- Explore cmdlet differences: Run and analyze the results of different commands, such as comparing Export-Csv with ConvertTo-HTML.
- Event Log: Use Get-EventLog to export recent security events to an HTML file.
- Terminate Processes: Use Stop-Process to terminate processes (like Windows Notepad).
- Export to XML or CSV: Learn how to prevent overwriting files with Export-CliXML and control the delimiter used with Export-CSV.

**Key Cmdlets**:
- Export-CSV: Exports data to a CSV file.
- Get-Content: Reads data from a file.
- Import-CSV: Imports data from a CSV file.
- Get-EventLog: Retrieves event log entries.
- ConvertTo-HTML: Converts objects to HTML format.
- Stop-Process: Stops running processes.
- Export-CliXML: Exports objects to XML format.
- Select-Object: Selects specific properties from objects.

**Classwork 4: Command Analysis**

**Summary**: This classwork involves analyzing PowerShell commands for retrieving information from remote computers. The main task is identifying and correcting issues in commands designed to retrieve data, such as services, event logs, and system information (BIOS) from all computers in the domain. Proper remoting techniques need to be applied for remote access.

**Key Cmdlets**:
- Get-ADComputer: Retrieves Active Directory computer objects.
- Get-Service: Lists services running on a local or remote machine.
- Get-WmiObject: Retrieves WMI data (e.g., BIOS information) from local or remote computers.
- Invoke-Command: Executes commands on remote computers.
- Get-EventLog: Retrieves event logs from local or remote machines.
- Get-Content: Reads the content of a file, like a list of computer names from a text or CSV file.

**Classwork 5: Remoting Exercises**

**Summary**: This classwork focuses on using PowerShell Remoting to execute commands on remote computers. Tasks involve enabling remoting, creating remote sessions, executing commands remotely, and retrieving data (e.g., event logs, processes, or services). The exercises emphasize the use of PowerShell remoting cmdlets to interact with multiple systems efficiently.

**Key Cmdlets**:
- Enable-PSRemoting: Enables PowerShell remoting on the computer to allow remote management.
- Invoke-Command: Executes commands on one or more remote computers.
- New-PSSession: Creates a new remote PowerShell session to a specified computer.
- Get-Process: Lists processes running on local or remote computers.
- Get-EventLog: Retrieves event logs (e.g., security logs) from remote machines.
- Get-Module: Lists available modules on a local or remote computer.
- Set-PSRemoting: Configures PowerShell remoting settings.

**Classwork 6: CIM/WMI Cmdlets**

**Summary**: This task requires using CIM/WMI cmdlets to solve a series of problems related to system configuration. You'll query and display details about classes, methods, network adapter configurations, and hotfixes.

**Key Cmdlets**:
- Get-CimClass: Lists available CIM classes, particularly in the Microsoft namespace.
- Get-CimInstance: Retrieves instances of CIM classes like win32_networkadapterconfiguration.
- Get-WmiObject: Fetches WMI objects, used here for services and hotfix queries.
- Get-CimMethod: Lists methods of a CIM class, e.g., win32_networkadapterconfiguration.
- Get-WmiObject -Class Win32_QuickFixEngineering: Queries installed hotfixes.

**Classwork 7: Background and Syntax Review**

**Summary:** This classwork introduces PowerShell syntax and variable handling. It involves defining variables, performing string manipulation, accessing properties of objects, and understanding cmdlet syntax. The exercises focus on practical usage of variables in scripts, and manipulating strings, processes, and other objects effectively.

**Key Cmdlets:**
- Get-Variable: Retrieves all defined variables in the current PowerShell session.
- Remove-Variable: Removes a specified variable from the session.
- Set-Variable: Sets the value of a variable.
- Get-Process: Retrieves running processes.
- Write-Host: Displays information to the console (e.g., output from variables).
- Select-Object: Selects specific properties of an object to display or manipulate.
- replace: Performs string replacement within a variable or string.


**Classwork 8: Bowling Score Recorder**

**Summary**:In this task, you created a PowerShell script that collects bowling scores for 9 frames in a game. The script validates the user input to ensure it’s a number between 0 and 10, stores the valid scores in an array, and prints the scores with labels indicating the frame number. Finally, the scores are saved to a text file for later reference.

**Key Cmdlets**:
- Read-Host: Prompts the user for input to enter the score for each frame.
- For: Loops through to prompt the user for scores for each of the 9 frames.
- Out-File: Saves the scores to a text file (bowling_scores.txt).
- Write-Host: Displays the scores on the screen with labels for each frame.
- Test-Int: A custom validation (if used) to ensure the score is a valid integer within the range of 0 to 10.


**Classwork 9: Display Running Services and Task Scheduling**

**Summary**: This script displays all the currently running services on a machine. The script is then attached to a scheduled task, which ensures it runs automatically when the user logs in. Screenshots of the PowerShell script, task registration, and Task Manager are required.

**Key Cmdlets:**
- Get-Service: Retrieves the list of all running services.
- New-ScheduledTask: Registers a new scheduled task.
- Register-ScheduledTask: Binds the script to the scheduled task.
- Start-ScheduledTask: Starts the task once it's created.

  **Automated:**
- Displaying running services with `Get-Service`.
- Scheduling the task using `New-ScheduledTask`.

**Classwork 10: Shared Folder and Printer Setup in PowerShell**

**Summary:** In this classwork, you create shared folders between two servers using PowerShell. You also set up a printer on one of the virtual machines (VMs), which can be either a physical or virtual printer.

**Key Cmdlets:**
- New-PSDrive:Creates a new shared folder or network drive.
- Set-SmbShare:Configures and shares a folder over SMB.
- Add-Printer:Adds a printer to the system.
- Set-Printer: Configures the printer settings

