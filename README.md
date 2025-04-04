# Cisco-Packet-Tracer
Cisco Packet Tracer Real life Projects
<!DOCTYPE html>
<html>
<head>
    <title>OneNote Converted Notes</title>
    <style>
        body { font-family: Arial, sans-serif; line-height: 1.8; margin: 20px; background-color: #f9f9f9; color: #333; }
        h1, h2, h3 { color: #0056b3; }
        .section { margin-bottom: 25px; padding: 15px; background: white; border-radius: 8px; box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); }
        .code-block { background-color: #272822; color: #f8f8f2; padding: 15px; border-radius: 5px; font-family: monospace; white-space: pre-wrap; }
        ul { margin-left: 20px; }
        a { color: #d35400; text-decoration: none; }
        a:hover { text-decoration: underline; }
    </style>
</head>
<body>
    <div class="section">
        <h1>OneNote Link</h1>
        <p><a href="https://onedrive.live.com/view.aspx?resid=C09A73B9C3376B0E%21s35adc950e55d48649b0889c2e9bd50d4&id=documents" target="_blank">View OneNote Document</a></p>
    </div>
    
<div class="section">
        <h2>Scenario</h2>
        <p>Design a network in CISCO packet tracer to connect ACCOUNTS and DELIVERY departments through the following:</p>
        <ul>
            <li>Each department should contain at least 2 PCs.</li>
            <li>Appropriate number of switches and routers should be used in the network.</li>
            <li>Using the given network address 192.168.40.0, all interfaces should be configured with appropriate IP addresses, subnet mask, and gateways.</li>
            <li>All devices in the network should be connected using appropriate cables.</li>
            <li>Test the connectivity between ACCOUNT and DELIVERY department - PCs in DELIVERY department should be able to ping PCs in ACCOUNTS department.</li>
        </ul>
    </div>
    
<div class="section">
        <h2>Subnetting</h2>
        <p><strong>Network:</strong> 192.168.40.0</p>
        <p>Number of departments: 2, so we need 2 Subnets</p>
        <p><strong>Subnet Mask:</strong> 255.255.255.128 or /25</p>
        <p><strong>Block size:</strong> 128</p>
    </div>
    
<div class="section">
        <h2>Router Configuration Code</h2>
        <div class="code-block">
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
        </div>
    </div>
    
<div class="section">
        <h2>Account Department Devices Configuration</h2>
        <ul>
            <li><strong>PC0</strong>: IP 192.168.40.2, Subnet 255.255.255.128, Gateway 192.168.40.1</li>
            <li><strong>PC1</strong>: IP 192.168.40.3, Subnet 255.255.255.128, Gateway 192.168.40.1</li>
            <li><strong>Printer0</strong>: IP 192.168.40.4, Subnet 255.255.255.128, Gateway 192.168.40.1</li>
        </ul>
    </div>
    
<div class="section">
        <h2>Delivery Department Devices Configuration</h2>
        <ul>
            <li><strong>PC2</strong>: IP 192.168.40.130, Subnet 255.255.255.128, Gateway 192.168.40.129</li>
            <li><strong>PC3</strong>: IP 192.168.40.131, Subnet 255.255.255.128, Gateway 192.168.40.129</li>
            <li><strong>Printer0</strong>: IP 192.168.40.132, Subnet 255.255.255.128, Gateway 192.168.40.129</li>
        </ul>
    </div>
    
<div class="section">
        <h2>Ping Command Details</h2>
        <div class="code-block">
C:\>ping 192.168.40.2
Pinging 192.168.40.2 with 32 bytes of data:
Request timed out.
Reply from 192.168.40.2: bytes=32 time<1ms TTL=127
Reply from 192.168.40.2: bytes=32 time<1ms TTL=127
Reply from 192.168.40.2: bytes=32 time<1ms TTL=127
        </div>
    </div>
</body>
</html>
