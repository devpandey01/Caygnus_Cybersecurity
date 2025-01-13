Virtual Machine Setup and Vulnerable Application Installation Report

## **Introduction**
This document outlines the process of setting up a virtual machine (VM) with a Linux-based operating system and installing a vulnerable application Metasploitable2 for penetration testing and security training. 

### **VMware Installation**
1. **Visit the Official Website**: Go to the [VMWare Download](https://www.vmware.com/products/workstation-pro.html).
2. **Download**: Select the version suitable for your OS.
3. **Install**: Follow the installation steps.

![image](https://github.com/user-attachments/assets/0179f25a-9ead-40da-9fd8-b82c09107866)


## **Step 2: Download a Linux ISO File**
### **Ubuntu Download**
1. **Visit Ubuntu's Download Page**: Go to [Ubuntu Download](https://ubuntu.com/download/desktop).
2. **Choose the Version**: Select the latest stable LTS release.
3. **Download the ISO**: Download the ISO file for installation.

   ![image](https://github.com/user-attachments/assets/25c480df-4813-49f9-94f1-70d4fb903452)

## **Step 3: Verify the Integrity of the ISO File**
1. **Obtain the Checksum**: Visit the download page for either Ubuntu or Kali Linux and note the SHA256 checksum.
2. **Verify the ISO File**:
   - On **Linux/macOS**: Use the command `sha256sum /path/to/your.iso`.
   - On **Windows**: Open PowerShell and use `Get-FileHash C:\path\to\your.iso -Algorithm SHA256`.

## **Step 4: Create a New Virtual Machine**
### **VMware Setup**
1. **Open VMware Workstation** and click **Create a New Virtual Machine**.
2. **Select Operating System**: Choose the appropriate version (e.g., Ubuntu 64-bit or Kali Linux).
3. **Allocate Resources**: 
   - **Memory**: Allocate at least **2GB RAM**.
   - **Disk**: Create a virtual disk with **20GB** storage or more.
4. **Attach ISO**: In **VM Settings**, under **CD/DVD** select the ISO file.

   ![image](https://github.com/user-attachments/assets/ef91838f-2366-4364-8674-c501a8ceaef5)

## **Step 5: Install the Operating System**
1. **Boot the VM**: Start the virtual machine to begin the OS installation process.
2. **Follow Installation Prompts**:
   - Choose language, time zone, keyboard layout.
   - Set up **user accounts** and **root password** (use a strong password for security).
   - Select default disk partitioning for installation.
3. **Complete Installation**: Wait for the installation to finish and reboot.

![image](https://github.com/user-attachments/assets/4b508183-cbd4-46e6-b740-0482db71eb46)

![image](https://github.com/user-attachments/assets/ef4edd4a-bc62-46e6-839a-748cc2e1b20a)


## **Step 6: Configure Network Settings**
1. **Configure Network Mode**: Set the network adapter to either **NAT** or **Bridged**:
   - **NAT**: Allows internet access via the host machine.
   - **Bridged**: Connects the VM directly to the local network.

   - **VirtualBox**: Go to **Settings** > **Network** > Adapter 1 > set **Attached to**: NAT or Bridged.
   - **VMware**: Go to **VM Settings** > **Network Adapter** > select **NAT** or **Bridged**.

   ![nat](https://github.com/user-attachments/assets/4f052413-9e23-4dda-9007-e6cbe574b6c7)


## **Step 7: Install a Vulnerable Application (Metasploitable2 or DVWA)**
### **Metasploitable2**
1. **Download**: Obtain the Metasploitable2 ISO from the [official SourceForge page](https://sourceforge.net/projects/metasploitable/).
2. **Create VM**: Create a new VM and mount the Metasploitable2 ISO.
3. **Start the VM**: Boot the VM and log in with the default credentials (`msfadmin`/`msfadmin`).
