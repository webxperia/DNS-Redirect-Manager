Managing DNS on a per-client basis is a powerful way to enforce parental controls, 
bypass geo-blocks for specific devices, or improve privacy for certain users while 
leaving others on default settings.

Since you are SSH-ing into 192.168.8.1 (likely a GL.iNet or OpenWrt-based router), 
we will use the UCI (Unified Configuration Interface) system. 
This is much safer and more persistent than editing config files manually.

The "DNS Redirect Manager" Script
I have designed this script to be interactive. It allows you to assign a specific DNS server to a device using its MAC Address.




Connect to your router

Open your terminal and log in:
ssh root@192.168.8.1
and the the code

Using wget:

Bash

wget -qO- https://raw.githubusercontent.com/webxperia/DNS-Redirect-Manager/refs/heads/main/ssh | sh

or
Using curl (if installed):

Bash

curl -sL https://raw.githubusercontent.com/webxperia/DNS-Redirect-Manager/refs/heads/main/ssh | sh


I have test it with Glinet FLint3 and BE-3000 Marble


Recomendation!

Goal,Primary DNS

Privacy (Cloudflare),1.1.1.1

Family/Filtering (CleanBrowsing),185.228.168.168




Ad-Blocking (AdGuard),94.140.14.14,

![Screenshot 2026-01-17 at 09 15 04](https://github.com/user-attachments/assets/124db430-b404-406c-be45-739f5bd9a37b)





