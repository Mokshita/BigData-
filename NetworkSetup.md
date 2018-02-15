Setting up network and SSH via host machine
Introduction
I prefer to have the IP addresses setup statically so they do not change via DHCP.  We will configure these changes on the host 
and in the virtual machine.

Change Host Adapter IP Address
On Windows 7, click on Control Panel → Network and Internet → Network connections.
Right click on Virtual Host-Only Network → select properties → double click on Internet Protocol Version 4 (TCP/IPv4)
Select use the following IP address and enter 192.168.56.104 for IP address and 255.255.255.0 for Subnet mask. (See Figure 1)  Then hit OK.

Change Guest Adapter IP address
1. Run the below command
$ sudo nano /etc/network/interfaces

2. Add the below lines to the end of  the /etc/network/interfaces file
auto enp0s8
iface enp0s8 inet static
address 192.168.56.101
netmask 255.255.255.0

3. Run the below commands to restart the network and verify ip address.
$ sudo /etc/init.d/networking restart
$ ifconfig -a

Please note that now enp0s8 is up and has a IP address of 192.168.56.101.From the host machine you should be able to ping 192.168.56.101


SSH from host to Guest:-
1. SSH will allow you to copy and paste from your host machine to your guest machine and it is also great program to 
administer linux servers remotely.
2. Download putty or Apple compatible ssh tool
3. In hostname type in the IP address of happy which is 192.168.56.101.
4. Now you will have SSH access to happy and will be able to copy and paste text in the terminal
