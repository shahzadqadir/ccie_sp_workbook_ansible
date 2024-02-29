#### SSH to vIOS and XR devices

fatal: [10.10.100.19]: FAILED! => {"changed": false, "msg": "ssh connection failed: ssh connect failed: kex error : no match for method kex algos: server [diffie-hellman-group1-sha1], client [diffie-hellman-group-exchange-sha1,diffie-hellman-group14-sha1]"}

##### Solution:

Add to ~/.ssh/config

<strong>For vIOS</strong>

Host host_ip
  KexAlgorithms +diffie-hellman-group1-sha1,diffie-hellman-group-exchange-sha1,diffie-hellman-group14-sha1
  Ciphers aes128-cbc,3des-cbc,aes192-cbc,aes256-cbc
  HostkeyAlgorithms +ssh-rsa

<strong>For XR</strong>

Host 10.10.100.19
  KexAlgorithms +diffie-hellman-group1-sha1
  Ciphers aes128-cbc,aes192-cbc,aes256-cbc,3des-cbc
  HostkeyAlgorithms +ssh-rsa

Also make sure to add host_key_checking=False to ansible.cfg file

more playbooks/ansible.cfg 
[defaults]
gather_facts=False
inventory=../hosts
host_key_checking = False
