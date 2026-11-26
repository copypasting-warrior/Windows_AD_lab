We will be performing this via PowerShell on the server.



Perform the following steps:

### Step 1: Find Network Adapters Alias:
```PowerShell
Get-NetAdapter

```

My network adapter is called Ethernet0 replace it with the name of your adapter in the next commands.&#x20;

### Step 2: Disable DHCP on the adapter:
```PowerShell
Set-NetIPInterface -InterfaceAlias "Ethernet0" -Dhcp Disabled

```

### Step 3: Assign a static IP address:
```PowerShell
New-NetIPAddress -InterfaceAlias "Ethernet0" -IPAddress 10.99.99.10 -PrefixLength 24 -DefaultGateway 10.99.99.2

```

Here 10.99.99.1 is the static IP we assign the machine. The PrefixLength 24  means the subnet mask is 255.255.255.0 and 10.99.99.2 is Vmnet8's NAt gateway.

### Step 4: Set DNS:
```PowerShell
Set-DnsClientServerAddress -InterfaceAlias "Ethernet0" -ServerAddresses 8.8.8.8

```

### Step 5: Verify changes to adapter:
```PowerShell
Get-NetIPAddress -AddressFamily IPv4

```

This will return an adapter with the IP address 10.99.99.10.

### Step 6: Verify if the NAT gateway and DNS is reachable:
```PowerShell
ping 10.99.99.2
ping 8.8.8.8

```

### Note:

If any of the above fail redo the above steps ensuring you run all commands and if the problems persists you can refer the following to debug it yourself:

- [Microsoft — NetTCPIP PowerShell Module](https://learn.microsoft.com/en-us/powershell/module/nettcpip)\
  &#x20;
- [Microsoft — Set-NetIPInterface](https://learn.microsoft.com/en-us/powershell/module/nettcpip/set-netipinterface)\
  &#x20;
- [Microsoft — New-NetIPAddress](https://learn.microsoft.com/en-us/powershell/module/nettcpip/new-netipaddress)\
  &#x20;
- [Microsoft — Set-DnsClientServerAddress](https://learn.microsoft.com/en-us/powershell/module/dnsclient/set-dnsclientserveraddress)\
  &#x20;
- [Microsoft — Windows network troubleshooting](https://learn.microsoft.com/en-us/troubleshoot/windows-client/networking)

Back to [Deployment and initial configuration](./Deployment%20and%20initial%20configuration.md)
