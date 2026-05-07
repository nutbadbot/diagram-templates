# 📁 Network & Infrastructure Templates

Template สำหรับ network topology, infrastructure diagram, rack diagram, virtualization, backup
ทุก template มี **Pragma Dark Style** + **Cisco icons** พร้อมใช้งาน

---

## Templates ปัจจุบัน (8 templates)

| ไฟล์ | ใช้ตอนไหน | Pragma Style |
|---|---|---|
| [3-tier-data-center.md](3-tier-data-center.md) | Enterprise DC 100-1000 users, HA pair Firewall | ✅ |
| [smb-single-site.md](smb-single-site.md) | SMB 20-100 users, single office | ✅ |
| [sd-wan-multi-site.md](sd-wan-multi-site.md) | Multi-site SD-WAN, HQ + branches + 4G backup | ✅ |
| [firewall-dmz-zones.md](firewall-dmz-zones.md) | Firewall + DMZ + Internal + Management zones | ✅ |
| [enterprise-wifi-deployment.md](enterprise-wifi-deployment.md) | WiFi 6 enterprise, multiple SSIDs, PoE+ | ✅ |
| [hyper-v-failover-cluster.md](hyper-v-failover-cluster.md) | Hyper-V Failover Cluster 2+ nodes, CSV, Live Migration | ✅ |
| [backup-architecture.md](backup-architecture.md) | Enterprise Backup — Veeam/Commvault, 3-2-1 rule | ✅ |
| [vlan-segmentation.md](vlan-segmentation.md) | VLAN design, inter-VLAN routing, zone isolation | ✅ |

---

## วิธีใช้ template

```
ช่วยหา template ที่เหมาะสมจาก
github.com/nutbadbot/diagram-templates
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
| Internet / ISP | `#1a2a4a` | `#4a90d9` |
| Security / Firewall | `#2d1a0e` | `#8b3a0f` |
| Core Layer | `#0d2b1a` | `#2e7d32` |
| Distribution / App | `#1a0d2b` | `#6a1b9a` |
| Access / Wireless | `#0d1f2b` | `#0288d1` |
| Storage / Data | `#1a1a0d` | `#f9a825` |
| End Devices | `#1a1a1a` | `#424242` |
| Cluster Node (Active) | `#2d1a4a` | `#9c27b0` |
| Cluster Node (Standby) | `#1a2a1a` | `#388e3c` |
| LACP Link | — | `#2e7d32` (หนา 3px) |
| Live Migration / HA | — | `#00bcd4` (เส้นประ) |
| Backup / Archive | — | `#ff9800` (เส้นประ) |

---

## เลือก template อย่างไร

| ถ้าต้องการ... | ใช้ template... |
|---|---|
| วาด network ทั้ง site (physical) | `3-tier-data-center.md` หรือ `smb-single-site.md` |
| เชื่อมหลาย site ด้วย SD-WAN | `sd-wan-multi-site.md` |
| แสดง firewall zones + DMZ | `firewall-dmz-zones.md` |
| วาง AP + WiFi | `enterprise-wifi-deployment.md` |
| แสดง Hyper-V HA cluster | `hyper-v-failover-cluster.md` |
| ออกแบบ backup topology | `backup-architecture.md` |
| ออกแบบ VLAN + security zone | `vlan-segmentation.md` |

---

## จะเพิ่ม (Roadmap)

- [ ] `spine-leaf-fabric.md` — Modern DC Spine-Leaf
- [ ] `rack-elevation-42u.md` — 42U rack layout
- [ ] `voip-deployment.md` — VoIP deployment (Cisco/Avaya)

## อยากเพิ่ม template ใหม่?

ดู [../../CONTRIBUTING.md](../../CONTRIBUTING.md)
