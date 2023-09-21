# PFsense Installation

This is a short guide how to install and configure PFsense firewall for lab environment purpose
The firewall will be able to be connected with a client and be able to route to internet

Prerequisite: familiar with VMM

Quickreference:
  - Default username and password: Admin, Pfsense
  - Download: https://www.pfsense.org/download/
  - OS: FreeBSD
  - Recommended RAM: 1 gig
  - Minimum storage: 8 gig

<h2>Installation</h2>

Download iso file from https://www.pfsense.org/download/
Transfer the iso file to server and set up with 1 gig ram, minimum 8 gig storage, bridged adapter (for example Virtualbox) or default VM Network on VMWare ESXI
<br><br><br>

![alt text](https://github.com/tg222eu/PFsenseInstallation/blob/main/UFS.JPG)<br>
Follow the guideline during installation. When asked for a partision choose Auto(UFS) and then GPT. Reboot when finished installing
<br><br><br>

![alt text](https://github.com/tg222eu/PFsenseInstallation/blob/main/vlan.JPG)<br>
When PFsense is started some configurations are required
  - VLAN: No
  - vmx0 or a?: The interface is vmx0 in our case but might be different depending on the network interface. Choose the interface thats given
  - LAN: [BLANK]
  - Proceed: Yes
  <br><br><br>

![alt text](https://github.com/tg222eu/PFsenseInstallation/blob/main/menui.JPG)<br>
When the configuration is set up a menu appears with a IPv4 adress. Login to the web UI using the IP adress in a browser <br>
Username: Admin<br>
Password: PFsense
<br><br><br>

![alt text](https://github.com/tg222eu/PFsenseInstallation/blob/main/firstwebgui.JPG)<br>
When logged into the web UI a wizard button will appear on the front page. Click on it, and follow the instructions
  - Hostname: Any
  - domain: Localdomain
  - DNS: 8.8.8.8

Leave time server hostname to default
<br><br><br>

![alt text](https://github.com/tg222eu/PFsenseInstallation/blob/main/secondwebgui.JPG)<br>
Change WAN interface to "Static". Give the IP address that was given to the firewall and set gateway stream to the router thats connected to the internet

<br><br><br>

![alt text](https://github.com/tg222eu/PFsenseInstallation/blob/main/client.JPG)<br>

Once finished you can set up a client with static IP and default gateway pointed toward the firewall
