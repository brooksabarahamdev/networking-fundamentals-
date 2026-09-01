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
