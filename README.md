# EtherChannel and LACP Link Aggregation Lab

## Project Overview

This project demonstrates the implementation of EtherChannel using Link Aggregation Control Protocol (LACP) in Cisco Packet Tracer.

The network consists of three interconnected switches forming a triangle topology. Multiple physical Ethernet links between each pair of switches are combined into logical Port-Channel connections to improve bandwidth utilization and link redundancy.

Spanning Tree Protocol (STP) is also investigated to understand how it prevents Layer 2 switching loops in a redundant network.

## Learning Objectives

- Understand link aggregation and EtherChannel.
- Configure LACP using Active and Passive modes.
- Combine multiple physical links into logical Port-Channels.
- Verify EtherChannel operation and member interfaces.
- Test link redundancy by disconnecting physical cables.
- Investigate STP behavior in an EtherChannel topology.
- Troubleshoot EtherChannel configuration issues.

## Network Topology

The network contains:

- 3 Cisco switches (Switch0, Switch1 and Switch2)
- 6 PCs
- 3 EtherChannels connecting each pair of switches
- Multiple physical links forming each EtherChannel
- A redundant triangle topology

## IP Addressing Plan

| PC | Connected Switch | IP Address | Subnet Mask |
|---|---|---|---|
| PC0 | Switch1 | 192.168.10.10 | 255.255.255.0 |
| PC1 | Switch1 | 192.168.10.11 | 255.255.255.0 |
| PC2 | Switch2 | 192.168.10.12 | 255.255.255.0 |
| PC3 | Switch2 | 192.168.10.13 | 255.255.255.0 |
| PC4 | Switch0 | 192.168.10.14 | 255.255.255.0 |
| PC5 | Switch0 | 192.168.10.15 | 255.255.255.0 |

## EtherChannel Configuration

Three separate EtherChannels are configured:

| Connection | Protocol | Purpose |
|---|---|---|
| Switch1 - Switch0 | LACP | Link aggregation |
| Switch0 - Switch2 | LACP | Link aggregation |
| Switch1 - Switch2 | LACP | Link aggregation |

Each EtherChannel combines multiple physical Ethernet links into one logical connection.

## Implementation Tasks

1. Build the three-switch triangle topology.
2. Configure IP addresses on all six PCs.
3. Configure LACP EtherChannel between Switch1 and Switch0.
4. Configure LACP EtherChannel between Switch0 and Switch2.
5. Configure LACP EtherChannel between Switch1 and Switch2.
6. Verify EtherChannel status and member interfaces.
7. Test end-to-end PC connectivity.
8. Disconnect individual physical links to test redundancy.
9. Investigate STP behavior and port roles.
10. Compare LACP Active and Passive modes.

## Verification Commands

```bash
show etherchannel summary
show interfaces trunk
show spanning-tree
show running-config
```

## Connectivity Testing

Use ICMP ping commands to verify communication between PCs connected to different switches.

Example:

```bash
ping 192.168.10.14
```

## Link Redundancy Testing

The following tests are performed:

- Verify that all EtherChannels are operational.
- Start continuous ping tests between PCs.
- Disconnect one physical member link.
- Observe packet loss and connectivity.
- Verify the remaining member links.
- Reconnect the cable and observe recovery.
- Repeat the test for all three EtherChannels.

## Technologies and Concepts

- Cisco Packet Tracer
- EtherChannel
- Link Aggregation Control Protocol (LACP)
- LACP Active and Passive Modes
- Port-Channel Interfaces
- Layer 2 Switching
- Spanning Tree Protocol (STP)
- Network Redundancy
- ICMP Connectivity Testing
- Network Troubleshooting

## Key Learning Outcomes

- Understand how multiple physical links operate as one logical connection.
- Configure and verify LACP EtherChannels.
- Understand the difference between physical interfaces and Port-Channel interfaces.
- Investigate link failure and redundancy.
- Understand how STP interacts with EtherChannel.
- Develop practical switching and troubleshooting skills.
