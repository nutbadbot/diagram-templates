# 📁 Network & Infrastructure Templates

Template สำหรับ network topology, infrastructure diagram, rack diagram
ทุก template มี **Pragma Dark Style** + **Cisco icons** พร้อมใช้งาน

---

## Templates ปัจจุบัน (5 templates)

| ไฟล์ | ใช้ตอนไหน | Pragma Style |
|---|---|---|
| [3-tier-data-center.md](3-tier-data-center.md) | Enterprise DC 100-1000 users, HA pair Firewall | ✅ |
| [smb-single-site.md](smb-single-site.md) | SMB 20-100 users, single office | ✅ |
| [sd-wan-multi-site.md](sd-wan-multi-site.md) | Multi-site SD-WAN, HQ + branches + 4G backup | ✅ |
| [firewall-dmz-zones.md](firewall-dmz-zones.md) | Firewall + DMZ + Internal + Management zones | ✅ |
| [enterprise-wifi-deployment.md](enterprise-wifi-deployment.md) | WiFi 6 enterprise, multiple SSIDs, PoE+ | ✅ |

---

## วิธีใช้ template

```
ช่วยหา template ที่เหมาะสมจาก repo
แล้วสร้าง diagram สำหรับ:
- Firewall: [รุ่น]
- Core Switch: [รุ่น + จำนวน]
- Access Switch: [รุ่น + จำนวน]
- AP: [รุ่น + จำนวน]
- Users: [จำนวน]
```

---

## 🎨 Pragma Style Color Reference

| Layer | Background | Border |
|---|---|---|
| Security / Firewall | `#2d1a0e` | `#8b3a0f` |
| Core Layer | `#0d2b1a` | `#2e7d32` |
| Access Layer | `#1a0d2b` | `#6a1b9a` |
| Wireless Zone | `#0d1f2b` | `#0288d1` |
| End Devices | `#1a1a1a` | `#424242` |
| LACP Link | — | `#2e7d32` (หนา 3px) |
| Backup Link | — | `#ff9800` (เส้นประ) |
| Stack Link | — | `#00bcd4` (เส้นประ) |

---

## จะเพิ่ม (Roadmap)

- [ ] `spine-leaf-fabric.md` — Modern DC Spine-Leaf
- [ ] `rack-elevation-42u.md` — 42U rack layout
- [ ] `voip-deployment.md` — VoIP deployment (Cisco/Avaya)
- [ ] `multi-site-mpls.md` — Traditional MPLS multi-site

## อยากเพิ่ม template ใหม่?

ดู [../../CONTRIBUTING.md](../../CONTRIBUTING.md)
