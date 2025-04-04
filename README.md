# Cisco-Packet-Tracer
#Simple Enterprise Network
![Network Diagram](images/network-diagram.png)

# OneNote Converted Notes

## OneNote Link
[View OneNote Document](https://onedrive.live.com/view.aspx?resid=C09A73B9C3376B0E%21s35adc950e55d48649b0889c2e9bd50d4&id=documents)

## Scenario
Design a network in CISCO packet tracer to connect ACCOUNTS and DELIVERY departments through the following:
- Each department should contain at least 2 PCs.
- Appropriate number of switches and routers should be used in the network.
- Using the given network address 192.168.40.0, all interfaces should be configured with appropriate IP addresses, subnet mask, and gateways.
- All devices in the network should be connected using appropriate cables.
- Test the connectivity between ACCOUNT and DELIVERY department - PCs in DELIVERY department should be able to ping PCs in ACCOUNTS department.

## Subnetting
- **Network:** 192.168.40.0
- Number of departments: 2 (so we need 2 subnets)
- **Subnet Mask:** 255.255.255.128 or /25
- **Block size:** 128

## Router Configuration Code
```sh
Router>
Router>en
Router#config t
Router(config)#int range gig0/0-1
Router(config-if-range)#no shut
Router(config-if-range)#exit
Router(config)#int gig0/0
Router(config-if)#ip address 192.168.40.1 255.255.255.128
Router(config-if)#int gig0/1
Router(config-if)#ip address 192.168.40.129 255.255.255.128
Router(config-if)#exit
Router(config)#do wr
Building configuration... [OK]
```

## Account Department Devices Configuration
- **PC0:** IP 192.168.40.2, Subnet 255.255.255.128, Gateway 192.168.40.1
- **PC1:** IP 192.168.40.3, Subnet 255.255.255.128, Gateway 192.168.40.1
- **Printer0:** IP 192.168.40.4, Subnet 255.255.255.128, Gateway 192.168.40.1

## Delivery Department Devices Configuration
- **PC2:** IP 192.168.40.130, Subnet 255.255.255.128, Gateway 192.168.40.129
- **PC3:** IP 192.168.40.131, Subnet 255.255.255.128, Gateway 192.168.40.129
- **Printer0:** IP 192.168.40.132, Subnet 255.255.255.128, Gateway 192.168.40.129

## Ping Command Details
```sh
C:\>ping 192.168.40.2
Pinging 192.168.40.2 with 32 bytes of data:
Request timed out.
Reply from 192.168.40.2: bytes=32 time<1ms TTL=127
Reply from 192.168.40.2: bytes=32 time<1ms TTL=127
Reply from 192.168.40.2: bytes=32 time<1ms TTL=127
```
