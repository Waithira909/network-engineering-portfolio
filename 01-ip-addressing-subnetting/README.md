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

## Project 1: IPv4 Subnetting

### Problem
Determine the subnet details for the host address `192.168.10.75/27`.

### Given
- IP address: `192.168.10.75`
- CIDR prefix: `/27`

### Solution
| Property | Result |
|---|---|
| Subnet mask | `255.255.255.224` |
| Network address | `192.168.10.64` |
| Broadcast address | `192.168.10.95` |
| First usable address | `192.168.10.65` |
| Last usable address | `192.168.10.94` |
| Host bits | `32 - 27 = 5` |
| Total addresses | `2^5 = 32` |
| Usable host addresses | `32 - 2 = 30` |

### Method
1. A `/27` prefix leaves 5 bits for hosts.
2. The subnet mask is `255.255.255.224`.
3. The block size is `256 - 224 = 32`.
4. The address `192.168.10.75` falls in the block from `192.168.10.64` to `192.168.10.95`.
5. The first and last addresses are reserved for the network and broadcast, leaving 30 usable host addresses.

### Verification
The host address `192.168.10.75` is within the usable range `192.168.10.65–192.168.10.94`.

### Skills demonstrated
- IPv4 subnetting and CIDR notation
- Subnet mask and block-size calculations
- Identifying network, broadcast, and usable host addresses

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

