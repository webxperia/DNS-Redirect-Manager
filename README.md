### DNS Redirect Manager

Managing DNS on a per-client basis is a powerful way to enforce parental controls, 
bypass geo-blocks for specific devices, or improve privacy for certain users while 
leaving others on default settings.

Since you are **SSH-ing into 192.168.8.1** (likely a GL.iNet or OpenWrt-based router), 
we will use the UCI (Unified Configuration Interface) system. 
This is much safer and more persistent than editing config files manually.

The "DNS Redirect Manager" Script
I have designed this script to be interactive. It allows you to assign a specific DNS server to a device using its MAC Address.


### After install you can find it on LUCI -> Services -> DNS Redirect


### Connect to your router

Open your **terminal** and log in:
```ssh root@192.168.8.1```
and then the code

### Using wget:

Bash
```
wget -qO- https://raw.githubusercontent.com/webxperia/DNS-Redirect-Manager/refs/heads/main/ssh | sh
```
or
### Using curl (if installed):

Bash
```
curl -sL https://raw.githubusercontent.com/webxperia/DNS-Redirect-Manager/refs/heads/main/ssh | sh
```

I have **test** it with Gl.inet **FLint3** and **GL-B3000** (Marble)


**Recomendation!**

Goal,Primary DNS

**Cloudflare**,1.1.1.1

**Family/Filtering** (CleanBrowsing),185.228.168.168

**Ad-Blocking** (AdGuard),94.140.14.14,

![Screenshot 2026-01-17 at 09 15 04](https://github.com/user-attachments/assets/124db430-b404-406c-be45-739f5bd9a37b)


**HOW TO UNINSTALL**

### Delete main files
```
rm -f /usr/lib/lua/luci/controller/admin/dnsredirect.lua
rm -f /usr/lib/lua/luci/view/admin_dnsredirect/dashboard.htm
rm -f /usr/share/dns-redirect/apply-rules.sh
rm -f /etc/config/dnsredirect
rm -f /www/luci-static/dnsredirect/theme-switcher.js
```
### Clean up configuration
```
uci delete dnsredirect 2>/dev/null
uci commit 2>/dev/null
```

### Remove empty directories
```
find /usr/lib/lua /usr/share /www/luci-static -type d -empty -delete 2>/dev/null
```
### Restart and clean Luci catch interface
```
rm -rf /tmp/luci-*
/etc/init.d/uhttpd restart
/etc/init.d/rpcd restart```

