# IP Addressing and Subnetting Lab

## Objective
Practice IPv4 addressing and subnetting to design and troubleshoot IP networks.

## Skills
- IPv4 address structure
- Subnet masks and CIDR notation
- Network and broadcast addresses
- Usable host ranges
- Network troubleshooting

## Status
In progress.


## Project 2: VLSM Subnetting for an Office Network

### Scenario

A company has been allocated the network `192.168.20.0/24`. The company has three departments that require separate subnets:

- HR: 25 hosts
- IT: 12 hosts
- Finance: 6 hosts

The goal is to allocate IP addresses efficiently using Variable Length Subnet Masking (VLSM), avoid overlapping subnets, and assign a default gateway to each department.

### Subnetting Plan

| Department | Hosts Required | Network Address | CIDR | Subnet Mask | Usable Host Range | Broadcast Address | Default Gateway |
|---|---:|---|---|---|---|---|---|
| HR | 25 | 192.168.20.0 | /27 | 255.255.255.224 | 192.168.20.1 - 192.168.20.30 | 192.168.20.31 | 192.168.20.1 |
| IT | 12 | 192.168.20.32 | /28 | 255.255.255.240 | 192.168.20.33 - 192.168.20.46 | 192.168.20.47 | 192.168.20.33 |
| Finance | 6 | 192.168.20.48 | /29 | 255.255.255.248 | 192.168.20.49 - 192.168.20.54 | 192.168.20.55 | 192.168.20.49 |

### Addressing Calculations

**HR — /27**
- Host bits: 32 - 27 = 5
- Total addresses: 2^5 = 32
- Usable host addresses: 32 - 2 = 30
- Block size: 256 - 224 = 32

**IT — /28**
- Host bits: 32 - 28 = 4
- Total addresses: 2^4 = 16
- Usable host addresses: 16 - 2 = 14
- Block size: 256 - 240 = 16

**Finance — /29**
- Host bits: 32 - 29 = 3
- Total addresses: 2^3 = 8
- Usable host addresses: 8 - 2 = 6
- Block size: 256 - 248 = 8

### Validation

- The subnets do not overlap.
- Each department has enough usable IP addresses for its stated requirement.
- Each subnet has a unique network address and broadcast address.
- The first usable address in each subnet is reserved as the default gateway for this lab.

### Skills Demonstrated
- IPv4 addressing and subnet masks
- CIDR notation
- VLSM subnet planning
- Network and broadcast address calculation
- Usable host range calculation
- Default gateway planning
- IP address allocation and subnet validation

