# Proxmox

:
Today, I’d like to introduce a new series, where I talk about various topics. This series will be titled, “What the Hack?!”.

In today’s WTH, we discuss installation, configuration, and monitoring with Security Onion . This is a basic installation talk that ends in seeing your traffic. In another discussion, we’ll look at that traffic and break it down.

First, we’ll talk about what Security Onion is, in my own words.

Security Onion is an analyst tool, targeted at providing real-time, or, afterthought analysis of network indicators that could lead to compromise, infection, beaconing of rouge applications, and detection of malicious tools, or activities.

Obtain your copy of Security Onion here:

https://github.com/Security-Onion-Solutions/security-onion/blob/master/Verify_ISO.md

As of this writing 16.0.4.6.6 is the latest release.

See Security Onion HW requirements found here section 3.3, pg 17:

https://readthedocs.org/projects/securityonion/downloads/pdf/latest/

GNU GRUB version 2.02Nbeta2-36ubuntu3.23 *Security0nion 16.04.6.3 GNU/Linux tuon on 16.04.6.3 GNU/Linux A vance pt on o ec Memory test (rnemtest86+) Memory test (rnemtest86+, serial console 115200) Use the T and I kegs to select which entry is highlighted. e' to edit the commands Press enter to boot the selected OS, before booting or for a command-line.

After booting into Security Onion, you’re met with an auto-login, default screen as the “securityonion@securityonion”, default user and computer name. This in a “live-mode” action.  You have full access to the system, same as any other system, but while in this mode, your actions will not persist. Essentially, the operating system has not been installed, and nothing has been written to disk, all items are run out of RAM. A power outage or shutdown will return this machine back to a default state with zero changes, such as it is here. In order to install Security Onion to the system, you must utilize the “Install Security Onion 16.04” installation activation link icon, found on the desktop.
ro uguoŕaunaas rełsuł

After initializing the activation link, your setup will begin, and you’ll be brought to the following setup page.

Here, you can select your preferred language of choice, and click continue.
Welcome EsparYiI YCRI may wish to ttE aack

After selecting your preferred language, you’re are presented with the “Prep” screen for your installation. I recommend, if you have an internet connection, choose both options, this will give you the latest application updates and install any additional software to potential aide you in the hunt.
Preparing to install Securityonion Dcwnload while SecurityOrW1 Trus saves Ome inmnann. Instal third-party soüare m•Fi Flash, MP3 This is su license iB is Fluendo pug MPEG Layer-3 audio deco&ng licensed tom IIS SA

Here, you will select the type of installation you would like. We will be using the basic installation here. Choose, “Erase disk and Install Security Onion”, this is the preferred method for this instruction.
Installation type ThÉ ccmputer curraüy has detected systems. What ym' like to @ Erase (Ek and nstal Sa:wnyOnion Warn"" ; ms will all programs. snoos. music. any omeg Mes in all operaong Encrypt the new securityonion nstaJlaticm tcr security You choose a key in N next use LVM With the new SecurityOnion ms will set up Lo•cal Wurt* Managertwnt allo«s snapshoE and easier parSW' resizing. Something eke You Can or paruons

Select continue to write changes to disk.
Installation type This computer current* has detected operating systems. ym' Eke to do? Write the cmnges to disks? It you continue. listed wi written to &sks. otherwise. ycw will to müe turttv manuaøy. partition tabks tte are charwl: scS13 (0.0.0) (sda) Tt-w following partitions are to tcrmatted: partition (sda) as ext4 partitm SCS13 (sda) as swap Go Back Install Non

Select your time zone and select continue.
Where are you? New York

Choose your keyboard layout type. If you have multiple layouts within your selected language, choose that sub-preference also.
Keyboard layout ymv keyboard (Ghana) EngEsh (Nigeria) E nghsh (South Africa) Enghsh (UK) E SSE' anto Type here to test your keyl»ard Detect Keyt»ard Layout English (US) - Cherokee English (US) - Enghsh (Colemak) English (US) - keys) English (US) EngEsh (Dvorak) English (US) - Enqush (Dvorü. international With keys) English (US) - Enghsh (Macintosh) Engush (US) • EngEsh

In this screen, you’ll create a user account and define your login preference. This account will be the User account of the system. Because Security Onion is built on an Linux Ubuntu system, root is not a readily available user login account. All system actions performed on this system will require the use of “sudo”. We will talk about this in another post. At the bottom, select the login type you’d like, “Require my password to log in” is the best method. You can choose to encrypt your home folder if you’d like.
• 51 n u03 一 0m5 」 L u60toapJomsspdÅ1uamOaH 1S4 , … aUJeUJn0A Is•qeue … acuetuasn ale 014M

Click continue to being your installation.
Installing system Skp

Security Onion will now install to your system, download any updates, apply them, and request for a restart. It is now safe to restart the machine.

After rebooting, enter the credentials you selected when creating a username and password.
BT-SOM € en_US 0 01 Jun, 00:25 C) analyst Cancel Log In

Upon logon, you’re presented with a very nice change of background, presenting you with your next set of instruction. Double-click the Setup icon to continue.
Applications Places Mon 00:27 To configure the system, please double-click the Setup icon.

After entering your credentials, your setup and configuration of the underlying applications that make security onion continues.
Security Onion Setup (bt-som) Welcome to security Onion setup! x Setup will configure the followting services: Elasticsearch Logstash Kibana Squert Sguil Bro Snort/Suricata netsniff-ng Would you like to continue? No, Quit. Yes, Continue!

This sections is one of the more vital pieces to the setup. Ensure you have entered the correct details, if not, your installation will not function properly.

Here we will configure the network interfaces. Because this is only an installation tutorial, we did not add a second network interface card to the machine. Luckily, you’re in luck today.

Select Yes, configure interfaces.
Security Onion Setup (bt-som) would you like to configure letc/neworkfinterfaces nov,'? x This is HIGHLY recommended as it will automatically optimize your neuork interfaces. This includes disabling any NIC offload features which may interfere with traffic analysis. If you choose NO, you should manually configure your interfaces per the instructions at: https://securityonion.netJdocs/NeworkConfiguration NO, not right now. yes, configure letc/nework/interfaces!

Choose your management interface. This interface is assigned an IP address from the network you chose during installation. In our installation, ens18 (this will generally be the architecture naming scheme for the internal NIC) is our management interface that we will setup on the network. Select this interface and move to the net menu.
Security Onion Setup (bt-som) Enter your neoaork's subnet mask (e.g., 255.255.255.0):

Fill in all required fields.
Security Onion Setup (bt-som) Enter your gateway's IP address (e.g., 192.168.1.1):

Fill in all required fields.
security onion Setup (bt-som) Enter one or more DNS server IP addresses, separated by spaces:

Fill in all required fields.
Security Onion Setup (bt-som) Enter your local domain name (e.g., example-com): Cancel OK

Here, you’ll need to configure your sniffing interface. Please understand there are multiple scenarios to allow full functionality. Configure the sniffing interface only, tell the NIC how to interpret the data received on that port. You must have a device that is capable of promiscuous mode.

Here are the type of devices and methods I have in my environment to capture traffic explained here:

    Physical TAP – Pricey, installed between your ISP and router Uplink port with additional port connected to Security Onion.
    Virtual TAP – Generally configured on Hypervisor I’s, think ESXI / Proxmox / etc..
    Virtual TAP type II – This is the Hypervisor II type, Vmware / VirtualBox / HyperTerminal.
    Port Mirroring / SPAN – I have a Netgear GS348T, smart managed switch. This device allows me to assign port(s) to be mirrored /  (SPAN) out to another port. On my switch, I have my VLANs & Uplink port mirrored to a SPAN port which connects to the sniffing port on my Security Onion.

Which ever type of TAP / SPAN you have, you’ll still need to configure the sniffing interface. Although

Select yes, configure interfaces here.
Security Onion Setup (bt-som) would you like to configure sniffing (monitor) interfaces? - Choose YES if this is a Standalone or sensor irlStallation - Choose NO if this is a server-only installation (only management interface will be configured) x NO, only configure a management interface. yes, configure sniffing interfaces.

Take note, you should not see the previously selected interface, that is your management interface. What you should see as an option here, are all the additional network card within your system.
Security Onion Setup (bt-som) x Please select any additional interfaces that will be used for sniffing. ens19 Cancel OK

Once you’ve selected your sniffing interface(s), you’re almost done. *clap*

Select yes, make changes. The system will go down for a reboot. Ensure you remove any media when prompted.
Security Onion Setup (bt-som) We're about to do the following: - Configure the management interface ens18 as follows: Set static IP address of 192.168.4.16 Set the gateway IP address to 192.168.4.1 Set the network mask to 255.255.255.0 Set the DNS server(s) to 192.168.4.1 Set the DNS domain to bt.io - Configure the following interface(s) for sniffing: ens19 We're about to make changes to your system! Would you like to continue? No, do not make changes. Yes, make changes!
Security Onion Setup (bt-som) Network configuration complete' You'" need to arKi then launch setup again to contuuæ secot%i phase ot setup. If 'red to manuaw mt:xiiG' any other retwork can letc/nerworkhnterfaces Would you üe to

Once you’ve completed your reboot, you’re presented with the login screen. Use your previously created credentials to login.

Once logged in, click setup again.

You will now see the services setup summary.

Click yes, continue.
Security Onion Setup (bt•som) Welcome to Secwny SeuW Setup configure the fohvinq services: ElastCsearch K i bana squil uric ata nets niff-ng Would you to continue?

Because we have already setup our primary NIC & chosen our sniffing NIC, we can skip network configuration.
」 n黛n53m驫1筍S9a訬隲蟸e一EA1- Ouos-") dmas uo 、 n s
Security Onion Setup (bt-sotn) Rules down%xki by Punedpork stcred letc/ns m u . rules I_æd rwes can be added to: /ac/ns m,'ru _ rules You can have mtxiib' the by mcKWing the in: Rules wil every morning. You can manuany them ruk--t4Xhte Sensors can be tuned by files n: letc/nsm/NAME-0F-SENSORJ
Security Onion Setup (bt•som) Please note that the kx:aJ utw firewal has Rx:ked It only ancms ccmnectbns to 22. If you need to connect wer any (Mher port. then rtm: sudo scyalkh•a
Security Onion Setup (bt•som) lt ут Ламе шту qtestkms *ase Vist: https :IIsec urty опт Пне ускл “s: Lists НС

After completing all the additional pop-ups after installation, right click on the desktop and open a terminal.

After entering your password, type the following command at the prompt:

<code> sudo so-status
analyst@BT.soM: - File Edit View Search Termna He") analyst F 8 T sudo so•status [sudo] password for analyst:

Once you press enter from the <code> sudo so-status command, you’re presented with:

    List of services running essential to the functionality of Security Onion.
    Status of services with matching color descriptor.
    Sensor status.

analyst@BT.soM: - Véw Search Termiml Help sudo so-status [sudo] password for analyst : Status: securityonion sguil server status: HIDS • ossec_agent (sguil) Status; Bro • 42 : 46 bro Type Host standalone localhost status running 22486 started 03 Jun 06. Status; bt-som•ens19 netsniff-ng (full packet data) pcap_agent (sguil) snort _ agent-I (sguil) snort-I (alert data) barnyard2-I (spooler, unified2 format) Status: Elastic stack so-elasticsearch so- logs tash so- kibana so- freqserver so-domainstats so-curator so •elastalert 0K 0K 0K 0K 0K 0K

The next installation check we want to look at is if we’re are actually getting traffic. This is absolutely essential to the operation of Security Onion in Production or Evaluation mode.

As you can see, there is an IP assigned to ens18. With this, we know we’re connected You will also notice ens19, which is in “PROMISC” mode. This is perfect and exactly what we want. We have a NIC(s) that is full on listen mode; by design, this is intended.
analyst@BT.soM: - Véw Search Termiml Help analyst MBT-SOM:-S ip a show ens18 2: ens18: mtu 1500 qdisc pfifo_fast state up group default glen woe link/ether brd inet 192.168.4.16/24 brd 192.168.4.255 scope global ens18 valid_lft forever preferred_lft forever inet6 fe8e: :a027: scope link valid_lft fore r preferred_lft forever analystdB1 ISDY:-S ip a show ens19 3: ens19: mtu Isøe qdisc pfifo_fast state up group default glen 1909 link/ether 3e:Ic:eb:de:33:af brd ff:ff:ff:ff:ff:ff

<code> sudo tcpdump -I ens19

You should now see your network traffic scrolling on screen.

Common issue – Troubleshooting traffic with tcpdump only gets ARP replies – You aren’t tapping / sniffing anything and tying it into your instance.

Once you’ve verified traffic, you can surf to:

https://YOUR_Security_Onion_IP

This is the landing page. From this page, you can begin to explore Security Onion and what it has to offer. Feel free to start with Kibana to view your Overview dashboard. You also have an instance of Cyber Chef and Squert at your fingertips.

https:hsecurityonion.net https:hsecurityonionsolutions.com 

Feel free to explore Security Onion’s Kibana dashboard. If you encounter any issues, refer to the previously linked docs hyperlink at the top. You can also open a terminal on the system and begin each command with “sudo so-<tab>” in order to discover what’s under the hood and commands available to you. 
