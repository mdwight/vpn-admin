VPN-Admin
=========

VPN-Admin is a collection of CLI scripts to manage a small OpenVPN system running on the Raspberry Pi.   The OpenVPN system requires a number of configuration, certificate and keys files for both the client and server side.  VPN-Admins can be used to manage these files and deploy them to the local OpenVPN server running on the RPi.  VPN-Admin will also also embed the configuration, certificate and keys files needed into a single configuration file for use by various OpenVPN clients.

Limitations
-----------

The OpenVPN system the scripts are design to manage have some limitation and don't take into account all the best practices for managing an OpenVPN system.  The first is that all keys and certificates are generated by one person.  Therefore these scripts should only be used on a small OpenVPN system where there is a high level of trust between users, such as a family or small technical group.  Secondly the keys and certificates are generated on the same system that runs the OpenVPN server.  Finally it is assumed that there will only be one instance of a OpenVPN server running on the RPi which is normal for most Home or small technical group VPNs.

Install Script
--------------

The following command will install or update the VPN-Admin scripts into the current working directory and also pull in the required scripts from OpenVPN/easy-rsa.  

    bash <(curl -L https://raw.githubusercontent.com/mdwight/VPN-Admin/v1.0/VPN-Admin-install.sh)


Documentation
-------------
    
Full documentation on how to setup and manage an OpenVPN system using VPN-Admin on the Raspberry can be found at [https://www.mdwight.com/OpenVPN](https://www.mdwight.com/OpenVPN).

Prerequisites
-------------

The scripts have been tested on Raspberry Pi (1,2 and 3) model B boards running Raspbian Stretch Lite.   The scripts were tested against OpenVPN v2.4 and easy-RSA v3.0.6.

Overview of VPN-Admin scripts
-----------------------------

There are 3 main scripts for VPN-Admin. The sub-command `help` will provide further details of their use. 

    ./config {sub-commands}
    
The above script is used to manage the OpenVPN configuration files for both the clients and server.  It will only make changes within the VPN-Admin system but will NOT affect the locally running OpenVPN system.

    ./system {sub-commands}

The above script is used to manage the OpenVPN service running locally on the Pi.  It is responsible for copying over configuration files and a starting and stopping the OpenVPN system.  This command will NOT make any modification within the VPN-Admin system.

    ./show {sub-commands} 
    
The above command is used to view the various log files and configuration files so you don't have to hunt around to find them.
   
License
-------

This project is licensed under the GNU GPL v3 License - see the [LICENSE.md](LICENSE.md) file for details.
