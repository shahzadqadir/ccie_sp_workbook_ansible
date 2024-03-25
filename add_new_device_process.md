#### Steps to add new device to lab

- Connect new device to Mgmt Switch
- Make connections to other devices as required
- On new device configure IP address in management range (10.10.100.x)
- configure ip domain name (shahzadqadir.net or anything)
- configure username/password (username xx priv 15 secret xx)
- generate rsa key (crypto key generate rsa (on prompt enter 2048))
- configure vty lines to use ssh (line vty 0 4 -> transport input ssh telnet -> login local)

These steps will enable connection to ansible host. Rest can be done through Playbooks.
Playbook to configure interfaces - configure_interfaces.yml
Read known_issues.md file if you come across any issues.