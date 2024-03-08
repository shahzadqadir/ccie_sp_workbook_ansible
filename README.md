# Ansible Playbook Solutions to INE Service Provider Workbook v3

#### Tasks Completed so far

- IPv4, IPv6 interface configurations
- Task 2.1 - OSPF base configuration
- Task 2.2 - OSPF Network Types
- Task 2.3 - OSPF Path Selection
- Task 2.5 - OSPF Authentication
- Task 2.6 - OSPFv3 Base Configurations
- Task 2.7 - OSPFv3 Path Selection

- Task 2.11 - Base ISIS Configurations
- Task 2.12 - ISIS Network Types
- Task 2.13 - Missing
- Task 2.14 - Missed, BFD - issues with GNS3
- Task 2.15 - Skipped for now - ISIS Authentication
- Task 2.16 - Multi Level ISIS
- Task 2.17 - Route Leaking
- Task 2.18 - Single Topology ISIS


Directory Structure

tree
.
├── directory_structure.txt
├── group_vars
│   ├── all.yml
│   ├── ios_routers.yml
│   └── xr_routers.yml
├── hosts
├── host_vars
│   ├── 10.10.100.1
│   │   ├── interfaces.yml
│   │   ├── isis218.yml
│   │   ├── isis.yml
│   │   ├── ospfv3.yml
│   │   └── ospf.yml
│   ├── 10.10.100.19
│   │   ├── interfaces.yml
│   │   ├── isis.yml
│   │   ├── mpls.yml
│   │   ├── ospfv3.yml
│   │   └── ospf.yml
│   ├── 10.10.100.2
│   │   ├── interfaces.yml
│   │   ├── isis218.yml
│   │   ├── isis.yml
│   │   ├── mpls.yml
│   │   ├── ospfv3.yml
│   │   └── ospf.yml
│   ├── 10.10.100.20
│   │   ├── interfaces.yml
│   │   ├── isis.yml
│   │   ├── ospfv3.yml
│   │   └── ospf.yml
│   ├── 10.10.100.3
│   │   ├── interfaces.yml
│   │   ├── isis218.yml
│   │   ├── isis.yml
│   │   ├── mpls.yml
│   │   ├── ospfv3.yml
│   │   └── ospf.yml
│   ├── 10.10.100.4
│   │   ├── interfaces.yml
│   │   ├── isis218.yml
│   │   ├── isis.yml
│   │   ├── mpls.yml
│   │   ├── ospfv3.yml
│   │   └── ospf.yml
│   ├── 10.10.100.5
│   │   ├── interfaces.yml
│   │   ├── isis218.yml
│   │   ├── isis.yml
│   │   ├── mpls.yml
│   │   ├── ospfv3.yml
│   │   └── ospf.yml
│   └── 10.10.100.6
│       ├── interfaces.yml
│       ├── isis218.yml
│       ├── isis.yml
│       ├── mpls.yml
│       ├── ospfv3.yml
│       └── ospf.yml
├── ine_sp_v3_ipv4_topology_gns3_mgmt.png
├── ine_sp_v3_isis_diagram.png
├── known_issues.md
├── lab_tasks.txt
├── LICENSE
├── playbooks
│   ├── ansible.cfg
│   ├── base_ospf_test_r1.yml
│   ├── configure_interfaces.yml
│   ├── configure_ospf2.yml
│   ├── get_show_version.yml
│   ├── task_2.11_isis_baseconfig.yml
│   ├── task_2.12_isis_networktypes.yml
│   ├── task_2.16_multi_level_isis.yml
│   ├── task_2.17_isis_route_leaking.yml
│   ├── task_2.18_singletopologyisis_ios.yml
│   ├── task_2.19_multitopology_isis.yml
│   ├── task_2.2_network_type.yml
│   ├── task_2.3_path_selection.yml
│   ├── task_2.5_ospf_authentication.yml
│   ├── task_2.6_ospf3_base_config.yml
│   ├── task_2.8_ospf3_pathselection.yml
│   ├── task_3.1_basic_ldp.yml
│   └── templates
│       ├── base
│       │   ├── interface_config_ios.j2
│       │   └── interface_config_xr.j2
│       ├── isis
│       │   ├── task_2.11_isis_baseconfig_ios.j2
│       │   ├── task_2.11_isis_baseconfig_xr.j2
│       │   ├── task_2.12_isis_network_types_ios.j2
│       │   ├── task_2.12_isis_network_types_xr.j2
│       │   ├── task_2.16_multi_level_isis_xr.j2
│       │   ├── task_2.16_mutli_level_isis_ios.j2
│       │   ├── task_2.17_isis_route_leaking_ios.j2
│       │   ├── task_2.17_isis_route_leaking_xr.j2
│       │   ├── task_2.18_isis_singletopology_ios.j2
│       │   ├── task_2.18_isis_singletopology_xr.j2
│       │   ├── task_2.19_isis_multitopology_ios.j2
│       │   └── task_2.19_isis_multitopology_xr.j2
│       ├── mpls
│       │   └── task_3.1_basic_ldp_ios.j2
│       └── ospf
│           ├── ipv4_base_ospf_ios.j2
│           ├── ipv4_base_ospf_xr.j2
│           ├── task_2.2_network_types_ios.j2
│           ├── task_2.2_network_types_xr.j2
│           ├── task_2.3_path_selection_ios.j2
│           ├── task_2.3_path_selection_xr.j2
│           ├── task_2.5_ospf_authentication_ios.j2
│           ├── task_2.5_ospf_authentication_xr.j2
│           ├── task_2.6_ospf3_baseconfig_ios.j2
│           ├── task_2.6_ospf3_baseconfig_xr.j2
│           ├── task_2.8_ospf3_pathselection_ios.j2
│           └── task_2.8_ospf3_pathselection_xr.j2
├── prep_for_ansible.txt
└── README.md
