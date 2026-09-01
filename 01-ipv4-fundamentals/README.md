
# IPv4 Fundamentals

## Overview

This lab documents my study and hands-on practice with IPv4 addressing and basic Windows network configuration.

The goal was to understand how IPv4 addresses are structured, recognize private IPv4 addresses, understand basic automatic addressing, and use Windows networking tools to inspect a computer's network configuration.

---

## IPv4 Addressing

IPv4 (Internet Protocol version 4) provides logical addressing that allows devices to communicate across IP networks.

An IPv4 address contains **32 bits**, divided into **four 8-bit octets**.

Example:

`192.168.1.25`

Each octet can contain a decimal value from **0 to 255**.

---

## Private IPv4 Addressing

Private IPv4 addresses are commonly used within internal networks such as home and business networks.

The three private IPv4 ranges are:

- `10.0.0.0 - 10.255.255.255`
- `172.16.0.0 - 172.31.255.255`
- `192.168.0.0 - 192.168.255.255`

### Private Address Recognition

I practiced identifying private addresses using these patterns:

- `10.x.x.x` — private
- `172.16.x.x` through `172.31.x.x` — private
- `192.168.x.x` — private

For example:

`172.28.10.7` is private because the second octet falls between 16 and 31.

`172.32.10.7` is not within the private `172.16.0.0/12` range.

---

## DHCP

DHCP stands for **Dynamic Host Configuration Protocol**.

DHCP can automatically provide devices with network configuration including:

- IPv4 address
- Subnet mask
- Default gateway
- DNS server information

This reduces the need to manually configure network settings on every device.

---

## APIPA

APIPA stands for **Automatic Private IP Addressing**.

If a Windows device cannot obtain IPv4 configuration from DHCP, it may automatically assign itself an address from the link-local range:

`169.254.0.0 - 169.254.255.255`

For example:

`169.254.50.10`

Seeing a `169.254.x.x` address during troubleshooting can indicate that the device was unable to obtain normal IPv4 configuration from DHCP.

An APIPA address can provide limited communication with other devices on the local link, but it normally does not provide routed Internet connectivity.

---

## Default Gateway

A default gateway is the router or network device a host sends traffic to when the destination is outside its local network.

Simplified traffic flow:

`Computer → Default Gateway → Other Networks`

The default gateway provides a path toward destinations that the computer cannot reach directly on its local network.

---

## Network Address Translation (NAT)

NAT stands for **Network Address Translation**.

On a typical home IPv4 network, a router can use NAT to translate between private addressing on the internal network and public addressing used for Internet communication.

It is important to distinguish NAT from a default gateway:

- **Default Gateway:** Where a host sends traffic when the destination is outside its local network.
- **NAT:** A process that translates IP addressing.

A router may perform both functions, but they are not the same thing.

---

# Hands-On Windows Lab

## Objective

Inspect the IPv4 configuration of a Windows computer and identify important network settings.

## Tool Used

Windows Command Prompt

## Command

```cmd
ipconfig
```

## Procedure

1. Opened Windows Command Prompt.
2. Ran the `ipconfig` command.
3. Located the active Wi-Fi network adapter.
4. Identified the IPv4 address.
5. Identified the subnet mask.
6. Identified the default gateway.
7. Determined whether the IPv4 address belonged to a private address range.

---

## Results

The computer was using an IPv4 address within the `10.0.0.0/8` private address range.

The `ipconfig` output also displayed the subnet mask and default gateway associated with the active network connection.

Exact network addresses have been omitted from this public documentation.

---

## Troubleshooting Scenario

If I run `ipconfig` on a Windows computer and find an address such as:

`169.254.50.10`

I would recognize it as an APIPA/link-local address.

One of my first troubleshooting considerations would be whether the computer failed to obtain its expected IPv4 configuration from DHCP.

---

## Skills Demonstrated

Through this lab, I practiced:

- IPv4 address identification
- Private IPv4 address recognition
- Basic DHCP concepts
- APIPA identification
- Default gateway concepts
- Basic NAT concepts
- Windows Command Prompt
- Using `ipconfig`
- Basic network troubleshooting

---

## Next Steps

The next topic in this networking lab series is **subnet masks and basic IPv4 subnetting**.
