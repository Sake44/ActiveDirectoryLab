# Active Directory Lab

Configuration vmware workstation:

For domain controller virtual machine set:

1. at leat 50gb of memory
2. 4-8gb RAM

From vmware workstation toolbar click Edit/Virtual Network Editor

Usually vmnet1 is set as host-only type. (Disable DHCP if you set static IP)

Use subnet class c for local network (**192.168.x.x**)

For Domain Controller set ip address to: **192.168.100.10**

![Windows Ip settings](/images/ipsettingsDC.png)

Now, create another virtual machine using as network adapter settings:  **Custom (vmnet1)**

![Vmware client network settings](/images/clientVmwareSettings.png)

Log in in our client and set a static ip address: 192.168.100.11

Subnet mask 255.255.255.0 and as preferred DNS 192.168.100.10 **(DC IP)**

Probably, there's a disabled inbound rule in Windows Defender Firewall that does not allow communication in local network. 

Go to: 

1. Windows Defender Firewall
2. Advanced settings
3. Inbound Rule
4. Look for File and Printer Sharing (Echo Request - ICMPv4-In)

![Firewall Inbound rule](/images/FirewallInboundRule.png)