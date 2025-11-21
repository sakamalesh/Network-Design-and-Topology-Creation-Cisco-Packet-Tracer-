# Network-Design-and-Topology-Creation-Cisco-Packet-Tracer-
Workshop: Design and Simulate Three Enterprise Network Topologies (30 Nodes Each)
-----------------------------------------------------------------------------------------
## NAME: KAMALESH S
## REGISTER_NUMBER: 21222304003
______________________________________________________________________________________
## Introduction

This report documents the complete design, configuration, and verification of an enterprise-scale network created using Cisco Packet Tracer.
The project covers:
>Multi-router hierarchical network
>Six-layer access switches
>DHCP, VLANs, subnetting
>Inter-router communication
>End-to-end connectivity verification
>The entire topology was designed, configured, and tested from scratch.

## NETWORK TOPOLOGY
<img width="1186" height="715" alt="image" src="https://github.com/user-attachments/assets/06a5e5bc-7c6d-4f7c-b2d2-cad0f6076e6e" />

## IP ADDRESSING

| Device | Interface | IP Address    | Subnet Mask     | Description     |
| ------ | --------- | ------------- | --------------- | --------------- |
| **R2** | G0/0      | 10.0.1.2      | 255.255.255.252 | Link to R3      |
|        | G0/1      | 192.168.10.1  | 255.255.255.0   | VLAN 10 Segment |
|        | G0/2      | 192.168.10.65 | 255.255.255.192 | VLAN 20 Segment |
| **R3** | G0/0      | 10.0.2.2      | 255.255.255.252 | Link to R4      |
|        | G0/1      | 192.168.20.1  | 255.255.255.0   | VLAN 10 Segment |
|        | G0/2      | 192.168.20.65 | 255.255.255.192 | VLAN 20 Segment |
| **R4** | G0/0      | 10.0.3.2      | 255.255.255.252 | Link to R7      |
|        | G0/1      | 192.168.30.1  | 255.255.255.0   | VLAN 30 Segment |
|        | G0/2      | 192.168.40.1  | 255.255.255.0   | VLAN 40 Segment |

## Router Configuration Summary
    ## DHCP Configuration
      ip dhcp pool VLAN10
       network 192.168.10.0 255.255.255.0
       default-router 192.168.10.1

      ip dhcp pool VLAN20
       network 192.168.10.64 255.255.255.192
       default-router 192.168.10.65

    ## interface Configuration Example
        interface GigabitEthernet0/1
         ip address 192.168.10.1 255.255.255.0
         no shutdown
    
    ## Helper Address Configuration
        interface GigabitEthernet0/1
         ip helper-address 10.0.1.1

## SWITCH CONFIGURATIONS:
    ## VLAN Creation
        vlan 10
        vlan 20
        vlan 30
        vlan 40

    ## Uplink Port Setup
        interface GigabitEthernet0/1
         switchport mode access
         switchport access vlan X
         no shutdown
        
     ## Access Ports
        interface range FastEthernet0/1 - 15
         switchport mode access
         switchport access vlan X
         spanning-tree portfast

## PC CONFIGURATIONS:
<img width="1600" height="899" alt="image" src="https://github.com/user-attachments/assets/6c5ce0aa-002e-433e-8bf4-7b3b2869abf2" />


## PING TEST:
<img width="1600" height="899" alt="image" src="https://github.com/user-attachments/assets/2dbc3ccf-1400-40d6-a8fb-00622527ca82" />

## RESULT:
This CASE STUDY demonstrates complete mastery of:
VLAN design
DHCP implementation
Inter-router connectivity
Switchport configuration
Network troubleshooting
Packet Tracer simulation






