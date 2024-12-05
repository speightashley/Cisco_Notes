---
tags:
  - CCNA/Subnetting/CIDR
---
# **CIDR Notation**

## **What is CIDR?**
- **CIDR (Classless Inter-Domain Routing)** is a method for allocating IP addresses and routing.
- Replaces the old classful addressing system (Class A, B, C).
- Allows more efficient use of IP address space and supports route aggregation.

---

## **CIDR Format**
- Written as: `IP Address/Prefix Length`
  - Example: `192.168.1.0/24`
- **Prefix Length:** Specifies how many bits are used for the network portion.
  - `/24` means the first 24 bits are for the network, leaving the remaining bits for hosts.

---

## **CIDR Range Breakdown**
| **CIDR Notation** | **Subnet Mask**     | **# of Addresses** | **# of Usable Hosts** | **Network Bits** | **Host Bits** |
|-------------------|---------------------|---------------------|-----------------------|------------------|---------------|
| `/8`              | 255.0.0.0          | 16,777,216          | 16,777,214            | 8                | 24            |
| `/16`             | 255.255.0.0        | 65,536              | 65,534                | 16               | 16            |
| `/24`             | 255.255.255.0      | 256                 | 254                   | 24               | 8             |
| `/30`             | 255.255.255.252    | 4                   | 2                     | 30               | 2             |

- **Usable Hosts:** Total addresses minus 2 (one for network ID and one for broadcast address).

---

## **Subnet Mask to CIDR**
| **Subnet Mask**     | **CIDR Notation** |
|---------------------|-------------------|
| 255.0.0.0           | /8               |
| 255.255.0.0         | /16              |
| 255.255.255.0       | /24              |
| 255.255.255.128     | /25              |
| 255.255.255.192     | /26              |
| 255.255.255.224     | /27              |
| 255.255.255.240     | /28              |
| 255.255.255.248     | /29              |
| 255.255.255.252     | /30              |

---

## **Calculating CIDR Subnets**
1. **Determine Prefix Length (CIDR):**
   - Convert subnet mask to binary.
   - Count the number of `1` bits.
     - Example: `255.255.255.0` → `11111111.11111111.11111111.00000000` → `/24`.

2. **Calculate Hosts Per Subnet:**
   - Formula: \( $2^{\text{Host Bits}} - 2$ \).
     - Example: `/24` → \( $2^{8} - 2 = 254$ \) usable hosts.

---

## **CIDR Examples**
1. **192.168.1.0/24**
   - Subnet Mask: 255.255.255.0
   - Total Addresses: 256
   - Usable Hosts: 254
   - Network Range: 192.168.1.0 to 192.168.1.255

2. **10.0.0.0/16**
   - Subnet Mask: 255.255.0.0
   - Total Addresses: 65,536
   - Usable Hosts: 65,534
   - Network Range: 10.0.0.0 to 10.0.255.255

3. **172.16.0.0/20**
   - Subnet Mask: 255.255.240.0
   - Total Addresses: 4,096
   - Usable Hosts: 4,094
   - Network Range: 172.16.0.0 to 172.16.15.255

---

## **CIDR in Supernetting**
- Aggregates multiple smaller networks into a single larger network.
- Example: Combine `192.168.0.0/24` and `192.168.1.0/24` into `192.168.0.0/23`.

---

## **CIDR Benefits**
1. **Efficient Address Usage:**
   - Avoids wasting IP addresses (e.g., classful system would reserve too many addresses).
2. **Simplifies Routing:**
   - Enables route aggregation to reduce routing table size.
3. **Supports Scalability:**
   - Flexible in creating subnets of varying sizes.

---

## **Key Formulas**
1. **Number of Subnets:**
$$   2^{\text{New Network Bits}}$$
   - Example: `/24` split into `/26` → \( $2^{2} = 4$ \) subnets.

2. **Number of Hosts per Subnet:**
$$2^{\text{Host Bits}} - 2$$
---

## **Useful Commands**
- **Convert CIDR to Subnet Mask:**
  ```bash
ipcalc <ip_address>/<prefix_length>
```

- **Display Network Range and Hosts:**

```bash

nmap -sL <ip_address>/<prefix_length>
```

