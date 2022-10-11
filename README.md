# mnemonic Simple Port Scanner

Live off the land with this simple PowerShell TCP port scanner.

## Quick start

This will run a default port scan (around 60 common ports)

```
PS > .\simple_port_scanner.ps1 -Address 192.168.1.1
```

## What is this?

This is a simple "TCP connect" port scanner, made for stealthy, small-scale scans against one host, and does not ping the target before scanning (similar to `nmap -Pn`). It comes in two variants:

- A regular PowerShell script where you can specify target address and ports
- A short one-liner that can fit in a Tweet

Both is a simpler version of the PowerShell port scanner found in the [Nishang](https://github.com/samratashok/nishang) toolset.

## How to use

**simple_port_scanner.ps1**

```
.SYNOPSIS
A simple TCP port scanner that does not ping the target

.DESCRIPTION
Scan one network address for open ports and its hostname. It tries ~60 popular ports by 
default and skips pinging the target before a scan (similar to -Pn in Nmap)
    
.PARAMETER Address
Target host address (IP or DNS name)

.PARAMETER Ports
Ports that should be scanned, default values are 21,22,23,53,69,71,80,81,88,98,110,111,
113,135,139,143,179,199,389,443,445,465,514,548,587,636,993,995,1025,1026,1080,1433,1521,
1720,1723,2000,2001,2049,3001,3128,3306,3389,5060,5222,5355,5357,5555,5801,5900,5901,5985,
5986,6001,6667,6868,7777,7878,8080,8888,10000,27000,27001

.PARAMETER Timeout
Time (in milliseconds) before timeout, default is 250

.PARAMETER NoResolve
Skip DNS resolution, similar to -n in Nmap

.EXAMPLE
PS > .\simple_port_scanner.ps1 -Address 192.168.1.1

.EXAMPLE
PS > .\simple_port_scanner.ps1 -Address 192.168.1.1 -Ports 80,443 -Timeout 100

.NOTES
by Kim Troennes, mnemonic
```

**simple_port_scanner_oneliner.ps1**

Modify the IP address and the comma-separated list of ports to scan in the beginning:`$ip="10.0.0.1";$Ports=@(22,80);`