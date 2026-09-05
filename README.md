# Firewall & ACL Configuration Lab

## Project Overview

A hands-on Network & Endpoint Security project focused on configuring, testing, and troubleshooting host-based firewalls and network-based Access Control Lists (ACLs).

The project was completed using Ubuntu Linux in VirtualBox and Cisco Packet Tracer.

## Environment

- Ubuntu Linux VM
- Oracle VirtualBox
- Cisco Packet Tracer
- Cisco 1941 Router
- Cisco 2960 Switch
- Windows/Linux endpoints for testing

## Tools & Technologies

- UFW (Uncomplicated Firewall)
- Cisco ACLs
- Nmap
- tcpdump
- net-tools
- Python HTTP Server
- Cisco Packet Tracer

## Skills Demonstrated

- Linux firewall configuration
- Network access control
- Firewall rule management
- Cisco standard ACL configuration
- Cisco extended ACL configuration
- IP-based traffic filtering
- Protocol and port-based filtering
- Nmap network testing
- Positive and negative security testing
- Network troubleshooting
- Security policy verification

## Part 1: Linux Host Firewall – UFW

Configured Ubuntu UFW using a default-deny incoming policy while allowing outgoing traffic.

### Firewall Policy

- Deny incoming traffic by default
- Allow outgoing traffic by default
- Allow SSH (TCP 22)
- Allow HTTP (TCP 80)
- Allow HTTPS (TCP 443)

The firewall was enabled and verified as active.

## Firewall Testing

Nmap was used to verify firewall behavior.

A Python HTTP server was started on TCP port 80, and Nmap confirmed that the port changed from closed to open when the service was listening.

This demonstrated that the configured UFW rule successfully permitted the required service traffic.

## Part 2: Cisco Network ACLs

A Cisco Packet Tracer topology was created using:

- Cisco 1941 Router
- Cisco 2960 Switch
- Two PCs
- One Server
- Separate LAN and Server networks

### Standard ACL

A standard ACL was configured to block PC1 from reaching the server while allowing PC0 to communicate with it.

Example policy:

- PC1 → Server: Denied
- PC0 → Server: Allowed

This demonstrated source-IP-based traffic filtering.

## Extended ACL

An extended ACL was configured to allow only HTTP traffic to the server while denying other traffic, including ICMP.

### Policy

- HTTP (TCP/80) → Allowed
- ICMP/Ping → Denied
- Other traffic to the server → Denied
- Normal traffic elsewhere → Permitted

### Verification

Testing confirmed that:

- Ping from both PCs to the server failed.
- HTTP access to the server succeeded from both PCs.

This demonstrated the ability of extended ACLs to control traffic based on source, destination, protocol, and port.

## Key Security Concepts

### Host-Based Firewall

A host firewall protects an individual endpoint by controlling incoming and outgoing network connections.

### Standard ACL

A standard ACL primarily filters traffic based on the source IP address.

### Extended ACL

An extended ACL provides more granular control by filtering based on factors such as source IP, destination IP, protocol, and port.

### Default-Deny Security

A default-deny approach blocks traffic unless it has been explicitly permitted, reducing unnecessary network exposure.

## Testing & Troubleshooting

The project included both positive and negative testing to verify that security controls behaved as expected.

Testing included:

- Nmap port scanning
- ICMP/ping testing
- HTTP connectivity testing
- Firewall status verification
- ACL behavior verification
- Network reachability testing

An important observation during the Linux firewall testing was that localhost traffic (127.0.0.1) can behave differently from traffic arriving through the network interface.

## Security & Ethical Scope

All activities were performed in an isolated laboratory environment for educational and portfolio purposes.

Network scanning, firewall testing, and ACL testing were performed only against systems and networks under controlled laboratory conditions.

Security tools and techniques should only be used on systems for which explicit authorization has been granted.

## Project Documentation

The complete project documentation, including configuration steps, topology, testing results, screenshots, and key observations, is available in the PDF included in this repository.

## Future Improvements

Potential future improvements include:

- Implementing more granular firewall rules
- Adding additional ACL scenarios
- Testing traffic between multiple VLANs
- Implementing ACL logging and monitoring
- Integrating firewall and ACL events with security monitoring tools
- Exploring centralized network security policies

## Project Status

**Completed ✅**
