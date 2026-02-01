# Netflix Domains & IP Ranges

This repository contains **known Netflix-related domains and IP ranges**
commonly observed in production traffic.  
It is intended for use with **firewalls, DNS filtering, policy routing,
VPN split tunneling, and traffic analysis**.

This is a **practical reference**, not an authoritative or complete list.
Netflix infrastructure is intentionally dynamic.

---

## 📁 Repository Contents

- `domains.txt`  
  Known Netflix domains used for streaming, applications, APIs, assets,
  corporate properties, and performance testing.

- `ipv4-ranges.txt`  
  Netflix Open Connect IPv4 ranges commonly attributed to **AS2906**.

- `ipv6-ranges.txt`  
  Observed Netflix IPv6 prefixes, including Open Connect and
  Netflix-adjacent delivery networks.

- `asn.txt`  
  Netflix autonomous system reference.

---

## 🌐 Domains

Domains are the **most reliable** way to identify Netflix traffic.

Netflix uses DNS-based load balancing, regional CDNs, and ISP-local caches.
Domain-based rules work better than static IP rules in most environments.

Examples include:
- `netflix.com`
- `nflxvideo.net`
- `nflximg.net`
- `fast.com`

See `domains.txt` for the full list.

---

## 📡 IPv4 Ranges

The IPv4 ranges in this repo primarily belong to:

- **AS2906 — Netflix Streaming Services (Open Connect)**

These ranges are commonly used for **video delivery**, but:
- Not all Netflix traffic uses these IPs
- Some delivery may occur via ISP-local Open Connect caches

See `ipv4-ranges.txt` for the full list.

---

## 🌍 IPv6 Considerations (Important)

Netflix uses IPv6 extensively, but IPv6 delivery is **highly dynamic**.

Key points:
- IPv6 prefixes may change by region and ISP
- Some Netflix IPv6 traffic originates from ISP-owned ASNs
- Static IPv6 IP-only rules are fragile

**Strong recommendation:**  
Use **domain-based filtering** and **ASN matching** whenever possible.

See `ipv6-ranges.txt` for observed prefixes.

---

## 🔀 Recommended Best Practices

- ✅ Prefer **domains over IPs**
- ✅ Use **ASN AS2906** when supported
- ✅ Use DNS-based policy routing for VPN split tunneling
- ❌ Avoid relying on IP-only rules for blocking or routing
- ❌ Avoid forcing Netflix traffic through VPNs unless necessary

---

## 🔧 Common Use Cases

- OpenWrt / GL.iNet firewall rules
- nftables / iptables / pfSense aliases
- Pi-hole / AdGuard DNS filtering
- VPN split tunneling exclusions
- Traffic identification and debugging
- Lab environments and documentation

---

## ⚠️ Disclaimer

Netflix infrastructure changes frequently.
This repository reflects **known and observed data** at the time of curation.
No guarantee is made that all Netflix traffic will match these entries.

---

## 📜 License

MIT License  
Free to use, modify, and redistribute. Attribution appreciated.