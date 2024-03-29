# Ansible Playbook Solutions to INE Service Provider Workbook v3

## Introduction

This repository provides solutions to tasks in INE Service Provider Workbook v3 in Ansible Playbooks form. Instead of using CLI, ansible is used to complete the tasks. Jinja2 templates, templates build as we go through the configuration tasks, host files change as required by tasks. See directory structure for details of how files are laid out.

### Network Diagram

![1711700268781](image/README/1711700268781.png)

## Installation

```
git clone https://github.com/shahzadqadir/ccie_sp_workbook_ansible.git
```

#### Navigating to a particular Task

```
1. Get the list of commits by using git log (mostly a commit is done per task)

Example:
shahzad@devpc:ansible$ git log --oneline
d00eadc (HEAD -> main, origin/main) Completed task 4.10 - VPNv4 Route reflectors w/IOS XR - yet to test
0b5a0fa Completed task 4.9 - MPLS L3VPNs with Route Reflectors
f3d291f Update README.md
7e5cfd9 Completed task 4.8 - MPLS L3 VPN Central Services, Instead of using RIPv2 I am using Static Routing between PE to CE. Done using existing templates.
a4d5b13 Updated task 4.7 - MPLS L3VPN Policy Based Routing (PBR) had missed some hosts in earlier commit.
9469beb Complete task 4.7 - MPLS L3VPN with PBR
aafbede working on python script to 'beautify' README file
12150f6 TEST Commit - updated README.md
a12f1cc Added new routers R7, R8 to host file Configured interfaces using playbooks/configure_interfaces.yml
3b55091 - added host files for R7, and R8 - updated host files (interfaces.yml) for R4, and R7 to inlcude links to R7 and R8 respectively. - updated network diagram to include mangament links - added configuration on R7 and R8 to enable SSH - added file add_new_device_process.md
a6e3b6d Update network diagram for tasks 4.7 onwards. Add R7 and R8 CPE Routers.
5f6bff2 Completed task 4.6 - MPLS L3 VPN with BGP
090c8ce removed un-necessary files. for all tasks in section 4 from 4.2 onwards only need one playbook that is task_4.2_onwards_all_customer_routing.yml Completed task 4.5 - MPLS L3VPN with OSPF
a8e6763 Standardized configuration of routing between PE and CE. Removed task based templates and configured a single template for all section 4 tasks.
24f3832 Completed task 4.4 - MPLS L3VPN EIGRP IOS & XR
46fc58a Completed task 4.4 MPLS L3VPNs with EIGRP for IOS Routers
ccfcb30 Fixed Task 4.2 - MPLS L3 VPN with Static Routing
819f12c Completed task 4.2 - MPLS L3VPNs with Static Routing
d0558dd updated host files for r2, xr1 to remove ipv4 and add vpnv4 family
....

2. If you want to go to task 4.2
git checkout 819f12c

3. Once done use following to go back to latest
git checkout main

```

## Sections done so far

* Section 2 - IGP

  * 2.1 - 2.5 OSPFv2 (IPv4)
  * 2.6 - 2.10 OSPFv3 (IPv6)
  * 2.11 - 2.15 ISIS - Single Level
  * 2.16 - 2.17 Multi Level ISIS, Route Leaking
  * 2.18 - 2.19 Single/Multi Topology ISIS
* Section 3 - MPLS

  * 3.1 - 3.8 LDP {Basics, Authentication, Autconfig, IGP Sync}
* Section 4 - VPN

  * 4.1 - 4.6 {Basic MPLS Tunnels, MPLS L3VPN Routing - static, eigrp, ospf, bgp}
  * 4.7 MPLS L3VPN Policy Based Routing
  * 4.8	MPLS Central Services L3VPN
  * 4.9 - 4.10	MPLS L3VPN Route Reflectors (IOS, IOSXR)

  > To get the full list use ``git log --oneline``
  >

## Directory Structure

```
ansible
  ansible.cfg
  hosts  (inventory file)
  ├── group_vars
    ├── all.yml
    ├── ios_routers.yml
    └── xr_routers.yml
  ├── hosts
  |   host_vars
       ├── 10.10.100.x (one host directory per device)
       ├── acls.yml
       ├── bgp.yml
       ├── interfaces.yml
       ├── isis218.yml
       ├── isis.yml
       ├── mpls.yml
       ├── ospfv3.yml
       ├── ospf.yml
       ├── routemaps.yml
       └── vpns.yml

```

Interested in learning Ansible basics, I also host a course at Udemy, you can get it for only 9.99 - [https://www.udemy.com/course/complete-ansible-for-network-engineers-ios-junos-arista/?couponCode=67CCE60A60C068C156A3](https://www.udemy.com/course/complete-ansible-for-network-engineers-ios-junos-arista/?couponCode=67CCE60A60C068C156A3) Msg me on linkedin if you need a free coupon.
