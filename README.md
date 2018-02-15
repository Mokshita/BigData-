Ubuntu Install
Introduction
Hadoop installation was meant to be installed on a production environment with powerful servers that have large supply of memory.  
In order for a Hadoop cluster to function properly in a Oracle VirtualBox environment, the minimum requirements of memory are 4 GB.  
1 GB for the host machine and 1 GB for the three guest machines.  
Not meeting that requirements might freeze jobs during the MapReduce process.  
This tutorial will use minimum server installation of Ubuntu to maximize the physical requirements.  

Ubuntu Installation
1.	I downloaded the minimal CD that can be found at this :-https://help.ubuntu.com/community/Installation/MinimalCD
    The minimal CD downloads the latest packages and we can select to use minimal amount of packages. 
    Download the 64-bit version of the current release of Ubuntu.  
2.	In VirtualBox create a new virtual machine and name it happy.  Select Linux as the type and Ubuntu (64-bit) as the version.  
3.	In the Memory size section I would give the virtual machine 2GB less than your total machine memory because on a single node the virtual machine acts as the resource manager and dataNode, therefore requiring more resources.
4.	In the hard disk section choose the default values so the hard drive is created as a 8GB dynamic vdi disk.
5.	Attach the mini.iso that was downloaded in step 1 to the virtual machine by clicking on settings → storage → the cdrom icon with the plus.  Select to choose disk and then browse to the file location of mini.iso to attach it to the virtual machine.
6.	In the Network section click on Adapter 2 tab and enable it as a Host-only Adapter and press OK.
7.	Press the start button to turn on the virtual machine.
8.	On Ubuntu install select the Install menu item.
9.	Go through prompts to select language and keyboard layout.
10.	On the Configure the network page select enp0s3 as the primary network interface
11.	For the hostname enter happy.
12.	Choose default for mirror location and server.  Also, configure with no proxy.
13.	For the username and password I created a user called vbadmin and assigned him a password of vbadmin
14.	Do not encrypt the home directory.  
15.	On the partitioning screen select Guided - use entire disk.  Then say yes to write changes.
16.	Select no automatic updates
17.	On the software selection screen choose to install standard system utilities, OpenSSH server, and Basic Ubuntu Server.  Then select to continue.        
18.	Select yes to install the GRUB boot loader on a hard disk.
19.	When the Finish installation screen appears select Devices on the VirtualBox menu → optical drive →  IDE primary → remove disk from virtual drive.  This will stop VirtualBox from running the CD on the next boot.
20.	Hit Continue

