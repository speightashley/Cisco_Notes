# Private IP Addresses

Private IP addresses are IP addresses reserved for internal use within private networks. These addresses cannot be routed on the public internet, making them ideal for local communication within a network, such as a home, office, or organisation.

---

## **Purpose of Private IP Addresses**
1. **Internal Communication:**
   - Used for devices within the same local network to communicate.
2. **Conservation of IPv4 Addresses:**
   - Prevents exhaustion of IPv4 addresses by reusing private address ranges within isolated networks.
3. **Security:**
   - Devices with private IP addresses are not directly accessible from the internet, providing a layer of protection.

---

## **Private IP Address Ranges**
Private IP address ranges are defined by **RFC 1918**. These ranges are:

| Class | Range                         | Number of IPs               |
| ----- | ----------------------------- | --------------------------- |
| A     | 10.0.0.0 - 10.255.255.255     | \( $2^{24}$ = 16,777,216 \) |
| B     | 172.16.0.0 - 172.31.255.255   | \( $2^{20}$= 1,048,576 \)   |
| C     | 192.168.0.0 - 192.168.255.255 | \( $2^{16}$= 65,536 \)      |

### **CIDR Notation**
- Class A: `10.0.0.0/8`
- Class B: `172.16.0.0/12`
- Class C: `192.168.0.0/16`

---

## **Difference Between Private and Public IPs**
| Feature               | Private IP                   | Public IP                  |
|-----------------------|-----------------------------|---------------------------|
| **Scope**             | Local (LAN)                 | Global (Internet)          |
| **Assigned by**       | Local network (Router, DHCP)| ISP                        |
| **Accessibility**     | Not routable on the internet| Routable on the internet   |
| **Cost**              | Free                        | May incur charges          |

---

## **How Private IPs Work**
1. **Network Address Translation (NAT):**
   - Devices with private IPs access the internet using NAT, where a router replaces the private IP with a public IP for outgoing traffic.
2. **Device Identification:**
   - Within a local network, each device is uniquely identified by its private IP.

---

## **Advantages of Private IPs**
- **Security:** Cannot be accessed directly from the internet.
- **Cost Savings:** No need to purchase public IPs for all devices.
- **Flexibility:** Networks can use the same private IP ranges without conflict.

---

## **Disadvantages of Private IPs**
- **No Direct Internet Access:** Requires NAT to communicate with the internet.
- **Limited Communication:** Cannot communicate directly with devices in another private network without additional configurations (e.g., VPN).

---

## **Example Usage**
1. Home Networks:
   - Routers assign private IPs like `192.168.1.2` to local devices.
2. Corporate Networks:
   - Use private IP ranges like `10.0.0.0/8` for large internal networks.

---

## **Key Notes**
- Private IP addresses are free to use.
- They help conserve IPv4 space by enabling address reuse.
- They require NAT or other technologies for internet access.

---

## **Related Concepts**
- **Public IP Addresses**
- **NAT (Network Address Translation)**
- **CIDR (Classless Inter-Domain Routing)**
- **IPv6 and Private Addressing**

---

### **References**
- RFC 1918: Address Allocation for Private Internets
- Understanding NAT and Private IP Addressing
