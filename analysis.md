# Network Scan Analysis

## Overview

A TCP SYN scan was performed on the local network using Nmap to identify active hosts and discover open TCP ports. The scan identified four active devices exposing different network services.

---

## Scan Summary

| Host   | Open Port(s) | Service(s)            |
| ------ | ------------ | --------------------- |
| Host 1 | 80           | HTTP                  |
| Host 2 | 80, 8899     | HTTP, OSPF-Lite       |
| Host 3 | 2869         | ICSLAP                |
| Host 4 | 135          | Microsoft RPC (MSRPC) |

---

## Port Analysis

### Host 1

**Open Port:** 80/TCP

**Service:** HTTP

**Description:**
Port 80 is the standard port used for HTTP web services. It is commonly found on routers, web servers, and devices providing web-based management interfaces.

**Potential Risks:**

* Unencrypted communication.
* Unauthorized access if management interfaces are exposed.
* Vulnerabilities in outdated web applications.

**Recommendation:**
Use HTTPS where possible, keep device firmware updated, and restrict access to trusted users.

---

### Host 2

**Open Ports:** 80/TCP, 8899/TCP

**Services:** HTTP, OSPF-Lite

**Description:**
Port 80 provides web-based access, while port 8899 is associated with OSPF-Lite and is commonly used by certain embedded or IoT devices for management or communication.

**Potential Risks:**

* Web interfaces may be vulnerable if left unsecured.
* Custom management services may expose device information or be susceptible to unauthorized access.

**Recommendation:**
Change default credentials, disable unused services, and ensure the device firmware is regularly updated.

---

### Host 3

**Open Port:** 2869/TCP

**Service:** ICSLAP

**Description:**
Port 2869 is commonly associated with Universal Plug and Play (UPnP) and Internet Connection Sharing services. It is often used by multimedia devices, smart TVs, and other network-enabled appliances.

**Potential Risks:**

* UPnP services can unintentionally expose devices to the network.
* Misconfigured services may increase the attack surface.

**Recommendation:**
Disable UPnP if it is not required and restrict unnecessary network services.

---

### Host 4

**Open Port:** 135/TCP

**Service:** Microsoft Remote Procedure Call (MSRPC)

**Description:**
Port 135 is used by Microsoft Windows for Remote Procedure Call (RPC), enabling communication between Windows applications and system services.

**Potential Risks:**

* Can be targeted if exposed outside trusted networks.
* May allow exploitation of RPC-related vulnerabilities if systems are not updated.

**Recommendation:**
Keep Windows systems updated, restrict access through firewalls, and allow RPC communication only within trusted networks.

---

## Wireshark Observation

Wireshark was used to monitor network traffic during the Nmap scan. The packet capture showed TCP SYN packets transmitted by Nmap and corresponding responses from active hosts. This demonstrated how Nmap identifies open ports without completing the full TCP three-way handshake.

---

## Conclusion

The scan successfully identified multiple active devices and their exposed network services. Most services appeared to be associated with normal network operations such as web management interfaces, Windows RPC, and device communication services. Regular monitoring, timely software updates, proper firewall configuration, and disabling unnecessary services can help reduce the attack surface and improve network security.
