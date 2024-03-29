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
  ├── playbooks
    ├── ansible.cfg
    ├── base_ospf_test_r1.yml
    ├── configure_interfaces.yml
    ├── configure_ospf2.yml
    ├── get_show_version.yml
    ├── host_files_archive
    ├── task_2.11_isis_baseconfig.yml
    ├── task_2.12_isis_networktypes.yml
    ├── task_2.16_multi_level_isis.yml
    ├── task_2.17_isis_route_leaking.yml
    ├── task_2.18_singletopologyisis_ios.yml
    ├── task_2.19_multitopology_isis.yml
    ├── task_2.2_network_type.yml
    ├── task_2.3_path_selection.yml
    ├── task_2.5_ospf_authentication.yml
    ├── task_2.6_ospf3_base_config.yml
    ├── task_2.8_ospf3_pathselection.yml
    ├── task_3.1_basic_ldp.yml
    ├── task_3.2_3.3_mpls_autconfig.yml
    ├── task_3.4_ldp_authenticate.yml
    ├── task_4.1_basic_mpls_tunnels.yml
    ├── task_4.2_onwards_all_customer_routing.yml
    ├── task_4.7_mpls_l3vpn_pbr.yml
    ├── task_4.8_mpls_l3vpn_central_services.yml
    ├── task_4.9_mpls_l3vpn_route_reflectors.yml
    └── templates
        ├── acls
        │   └── configure_acls.j2
        ├── base
        │   ├── interface_config_ios.j2
        │   └── interface_config_xr.j2
        ├── isis
        │   ├── task_2.11_isis_baseconfig_ios.j2
        │   ├── task_2.11_isis_baseconfig_xr.j2
        │   ├── task_2.12_isis_network_types_ios.j2
        │   ├── task_2.12_isis_network_types_xr.j2
        │   ├── task_2.16_multi_level_isis_xr.j2
        │   ├── task_2.16_mutli_level_isis_ios.j2
        │   ├── task_2.17_isis_route_leaking_ios.j2
        │   ├── task_2.17_isis_route_leaking_xr.j2
        │   ├── task_2.18_isis_singletopology_ios.j2
        │   ├── task_2.18_isis_singletopology_xr.j2
        │   ├── task_2.19_isis_multitopology_ios.j2
        │   └── task_2.19_isis_multitopology_xr.j2
        ├── mpls
        │   ├── task_3.1_basic_ldp_ios.j2
        │   ├── task_3.2_3.3_autoconfig_ios.j2
        │   ├── task_3.2_3.3_autoconfig_xr.j2
        │   ├── task_3.4_ldp_authentication_ios.j2
        │   └── task_3.4_ldp_authentication_xr.j2
        ├── ospf
        │   ├── ipv4_base_ospf_ios.j2
        │   ├── ipv4_base_ospf_xr.j2
        │   ├── task_2.2_network_types_ios.j2
        │   ├── task_2.2_network_types_xr.j2
        │   ├── task_2.3_path_selection_ios.j2
        │   ├── task_2.3_path_selection_xr.j2
        │   ├── task_2.5_ospf_authentication_ios.j2
        │   ├── task_2.5_ospf_authentication_xr.j2
        │   ├── task_2.6_ospf3_baseconfig_ios.j2
        │   ├── task_2.6_ospf3_baseconfig_xr.j2
        │   ├── task_2.8_ospf3_pathselection_ios.j2
        │   └── task_2.8_ospf3_pathselection_xr.j2
        ├── pbr
        ├── routemaps
        │   └── configure_routemap.j2
        └── vpn
            ├── all_tasks_bgp_ios.j2
            ├── all_tasks_bgp_xr.j2
            ├── l3vpn_customer_routing_ios.j2
           └── l3vpn_customer_routing_xr.j2

```

Interested in learning Ansible basics, I also host a course at Udemy, you can get it for only 9.99 - [https://www.udemy.com/course/complete-ansible-for-network-engineers-ios-junos-arista/?couponCode=67CCE60A60C068C156A3](https://www.udemy.com/course/complete-ansible-for-network-engineers-ios-junos-arista/?couponCode=67CCE60A60C068C156A3) Msg me on linkedin if you need a free coupon.
