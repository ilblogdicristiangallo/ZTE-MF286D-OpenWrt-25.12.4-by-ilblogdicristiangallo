# ZTE-MF286D-OpenWrt-25.12.4-by-ilblogdicristiangallo
Custom OpenWrt 25.12.4 firmware and APK repository for ZTE MF286D, built on Linux 6.12.74 (ipq40xx). Includes LuCI, QMI/MBIM modem support, ModemManager, WireGuard, modem tools, HTTPS-enabled package management, plus custom packages apn-web and telegramWrt, ready to use after sysupgrade.

# 📦 OpenWrt 25.12.4 — Custom Firmware & APK Repository
### by [ilblogdicristiangallo](https://www.ilblogdicristiangallo.com)

---

<div align="center">
  <img src="https://github.com/ilblogdicristiangallo/ilblogdicristiangallo_repo_openwrt_APK/blob/main/repository-openwrt-by-ilblogdicristiangallo.png?raw=true" 
       alt="Repository OpenWrt by ilblogdicristiangallo"
       width="600">
</div>

---

## 🖥️ What is inside the sysupgrade firmware?

The `sysupgrade-zte_mf286d-YYYYMMDD-HHMM.bin` file is a **custom OpenWrt 25.12.4 firmware image** built specifically for the **ZTE MF286D** router (Target: `ipq40xx/generic`).

It contains a **compressed Linux-based operating system** built on top of OpenWrt 25.12.4, with the following components pre-installed and ready to use out of the box.

---

### 🐧 Operating System

| Component | Details |
|---|---|
| **Base OS** | OpenWrt 25.12.4 |
| **Kernel** | Linux 6.12.74 |
| **Architecture** | ARM Cortex-A7 + NEON VFPv4 (ipq40xx) |
| **C Library** | musl libc 1.2.5 |
| **Package Manager** | apk-tools 3.0.5 (APK v3 format) |
| **Init System** | procd |
| **Shell** | busybox ash |

---

### 🌐 Web Interface

| Package | Version | Description |
|---|---|---|
| `luci` | 26.x | Full OpenWrt web administration interface |
| `luci-base` | 26.x | LuCI core framework |
| `luci-mod-admin-full` | 26.x | Full admin panel |
| `luci-theme-bootstrap` | 26.x | Default Bootstrap theme |
| `luci-app-firewall` | 26.x | Firewall management via LuCI |
| `luci-mod-network` | 26.x | Network configuration via LuCI |
| `luci-mod-status` | 26.x | System status page |
| `luci-mod-system` | 26.x | System settings via LuCI |
| `uhttpd` | 2025.x | Lightweight HTTP server for LuCI |

---

### 📡 Mobile Broadband & Modem Support

| Package | Version | Description |
|---|---|---|
| `luci-proto-qmi` | 26.x | QMI protocol support for LuCI |
| `luci-proto-mbim` | 26.x | MBIM protocol support for LuCI |
| `luci-proto-modemmanager` | 26.x | ModemManager integration for LuCI |
| `modemmanager` | 1.24.0 | Advanced modem management daemon |
| `uqmi` | 2025.x | Lightweight QMI modem utility |
| `umbim` | 2025.x | Lightweight MBIM modem utility |
| `usb-modeswitch` | 2025.x | USB modem mode switching tool |
| `kmod-usb-net-qmi-wwan` | 6.12.74 | Kernel module for QMI WAN |
| `kmod-usb-net-cdc-mbim` | 6.12.74 | Kernel module for MBIM |
| `kmod-usb-serial-option` | 6.12.74 | Kernel module for USB serial modems |
| `kmod-usb-wdm` | 6.12.74 | Kernel module for USB WDM devices |

---

### 📊 Modem Extra Tools (by [4IceG](https://github.com/4IceG))

| Package | Version | Description |
|---|---|---|
| `luci-app-modemband` | 1.0.31 | LTE band selection and locking via LuCI |
| `luci-app-sms-tool-js` | 2.0.38 | SMS management tool via LuCI |
| `luci-app-3ginfo-lite` | 1.0.77 | Real-time modem signal info via LuCI |

---

### 🔒 VPN — WireGuard

| Package | Version | Description |
|---|---|---|
| `luci-proto-wireguard` | 26.x | WireGuard protocol support for LuCI |
| `wireguard-tools` | 1.0.x | WireGuard VPN userspace tools |
| `kmod-wireguard` | 6.12.74 | WireGuard kernel module |

---

### 🌍 Network & Connectivity

| Package | Version | Description |
|---|---|---|
| `netifd` | 2026.x | OpenWrt network interface daemon |
| `dnsmasq` | 2.91 | DNS and DHCP server |
| `odhcp6c` | 2026.x | DHCPv6 client |
| `odhcpd-ipv6only` | 2026.x | DHCPv6 server |
| `firewall4` | 2025.x | nftables-based firewall |
| `nftables` | 1.1.6 | Packet filtering framework |
| `ppp` + `ppp-mod-pppoe` | 2.5.2 | PPP and PPPoE support |
| `wget-ssl` | 1.25.0 | wget with full HTTPS support |
| `curl` | 8.19.0 | HTTP/HTTPS transfer tool |
| `ca-bundle` | 2025.x | SSL/TLS CA certificates |

---

### 🔧 System Tools

| Package | Description |
|---|---|
| `busybox` | Core Unix utilities |
| `uci` | OpenWrt Unified Configuration Interface |
| `ubus` | OpenWrt inter-process communication bus |
| `procd` | OpenWrt process manager and init system |
| `logd` | System log daemon |
| `mtd` | MTD flash write utility |
| `uboot-envtools` | U-Boot environment tools |
| `dropbear` | Lightweight SSH server and client |
| `jq` | JSON processor for shell scripts |
| `tcpdump` | Network traffic analyzer |

---

### 📱 Custom Packages (by ilblogdicristiangallo)

| Package | Version | Description |
|---|---|---|
| `apn-web` | 1.0.3 | Simple web interface for APN configuration. Installed in `/www/` |
| `telegramWrt` | 1.0.7 | Modular Telegram bot for OpenWrt. Provides diagnostics, automation and security plugins. Installed in `/usr/lib/TelegramWrt/` |

---

### ⚙️ Pre-configured Settings

The firmware comes with a ready-to-use configuration:

#### Network (`/etc/config/network`)
- **LAN**: Bridge on ports `lan2`, `lan3`, `lan4` — Static IP `192.168.1.1`
- **WAN**: QMI modem on `/dev/cdc-wdm0` — APN `internet` — IPv4
- **WAN6**: DHCPv6

#### Firewall (`/etc/config/firewall`)
- LAN → WAN forwarding enabled
- WAN input rejected
- NAT/masquerade enabled
- SYN flood protection enabled

#### WiFi (`/etc/config/wireless`)
- **radio0**: 2.4 GHz — Channel 8 — HT20 — SSID `OpenWRT`
- **radio1**: 5 GHz — Channel auto — VHT80 — SSID `OpenWRT`
- Country: `IT`
