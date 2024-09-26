# Azure-Network-Protocol
<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create the folders
- Read-Access
- Log into Client
- Use active directory 

<h2>Actions and Observations</h2>

<p>
6 Steps to Set Up File Shares and Test Access
Log into DC-1:

//Step 1.Use your domain admin account: mydomain.com\jane_admin.
Create Folders on C: Drive:

//Step 2.Create the folders: read-access, write-access, no-access, and accounting on C:\.
Set Permissions and Share Folders:

//Step.3 Read-Access: Share with Domain Users set to Read.
Write-Access: Share with Domain Users set to Read/Write.
No-Access: Share with Domain Admins set to Read/Write.
Test Access as Normal User:

//Step 4. Log into Client-1 as mydomain\<someuser>.
Navigate to \\dc-1 and check access:
Read-Access: Should open.
Write-Access: Should open and allow file creation.
No-Access: Should be denied.
Create ACCOUNTANTS Security Group:

//Step.5 In Active Directory, create a group called ACCOUNTANTS.
Set permissions on the accounting folder to Read/Write for the ACCOUNTANTS group.
Test Access to Accounting Folder:

//Step.6 As <someuser>, try to access the accounting folder (should fail).
Add <someuser> to the ACCOUNTANTS group, log back in, and check access again (should succeed).

<p>

![image](https://github.com/user-attachments/assets/3453faf4-9acd-4a40-bad6-0f030efa94f7)

