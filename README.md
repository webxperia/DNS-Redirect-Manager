Managing DNS on a per-client basis is a powerful way to enforce parental controls, 
bypass geo-blocks for specific devices, or improve privacy for certain users while 
leaving others on default settings.

Since you are SSH-ing into 192.168.8.1 (likely a GL.iNet or OpenWrt-based router), 
we will use the UCI (Unified Configuration Interface) system. 
This is much safer and more persistent than editing config files manually.

The "DNS Redirect Manager" Script
I have designed this script to be interactive. It allows you to assign a specific DNS server to a device using its MAC Address.

1. Connect to your router

Open your terminal and log in:

Bash
ssh root@192.168.8.1
and the the code

I have test it with Glinet FLint3 and BE-3000 Marble


Recomendation
Goal,Primary DNS
Privacy (Cloudflare),1.1.1.1
Family/Filtering (CleanBrowsing),185.228.168.168
Google,8.8.8.8
Ad-Blocking (AdGuard),94.140.14.14,
