DHCP
* Open OPNSense https://10.15.16.151/ui/kea/dhcp/v4
* Add an entry for mac address of eno1 of the XOS server
* Apply
* Syncronize to backup (https://10.15.16.151/status_habackup.php)

PXE
* login to iDrac of the server.
* open remote KVM.
* Click "Boot", then select PXE.
* Click "Power", then select "Reset System (Warm Boot).
* On reboot, the server will try to boot from network after picking the IP address from DHCP.
* Select Linux 9 Installation with script, three selection steps.

HIM
* add the server to HIM (add host using IP)
* add the host to the inventory you want to run the playbooks on.
* run below playbooks in sequence:
* * XOS_1.0_init_Install_Packages
* * XOS_2.0_configure_management
* * XOS_2.2_configure_multicast_interface
* * XOS 3.0 - Install RPM | 1.24.0.0.77