# Netflix Domains & IP Ranges

This repository contains known Netflix domains and IP ranges
for use in firewalls, DNS filtering, routing policies, and traffic analysis.

## ⚠️ Important Notes

- Netflix intentionally rotates infrastructure.
- IPs outside AS2906 are often AWS or ISP-local caches.
- This list should be treated as a **baseline**, not a guarantee.
- Domain-based filtering is more reliable than IP-only filtering.

## Contents

- domains.txt        → Known Netflix domains
- ipv4-ranges.txt    → Netflix-owned Open Connect IP ranges
- asn.txt            → Netflix ASN

## Common Use Cases

- OpenWrt / GL.iNet firewall rules
- Split tunneling exclusions
- Pi-hole / AdGuard filtering
- Traffic classification
- VPN debugging

## ASN Reference

- AS2906 — Netflix Streaming Services

## IPv6 Considerations

Netflix uses IPv6 extensively, but IPv6 routing is highly dynamic.
Many Netflix IPv6 endpoints are delivered via ISP-local Open Connect
caches and may not always originate directly from AS2906.

For best results:
- Prefer domain-based filtering for IPv6
- Use ASN-based rules where supported
- Avoid hard-blocking IPv6 Netflix ranges unless necessary

## License

MIT (use freely, attribution appreciated)