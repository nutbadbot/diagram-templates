# Case Study: Retail Chain — SD-WAN Multi-Branch

> ข้อมูลลูกค้า mask แล้ว — ใช้เป็น reference สำหรับโปรเจกต์ SD-WAN ลักษณะเดียวกัน

---

## 📋 Background

| | รายละเอียด |
|---|---|
| **ประเภทธุรกิจ** | ร้านค้าปลีก (Retail) |
| **ขนาด** | 1 HQ + 12 สาขา |
| **Users รวม** | ~280 คน |
| **ระยะเวลาโปรเจกต์** | 3 เดือน |
| **Phase** | Pre-Sales → Design → Deployment |

---

## 🎯 โจทย์ของลูกค้า

- สาขาเก่าใช้ MPLS ราคาแพง ต้องการลด cost
- Internet แต่ละสาขาไม่เสถียร ไม่มี failover
- ระบบ POS ต้องการ latency ต่ำ (back to HQ datacenter)
- IT ดูแลคนเดียวไม่ไหว ต้องการ centralized management
- แต่ละสาขามี CCTV + Guest WiFi ที่ต้องแยกจาก POS network

---

## 🏗️ Solution ที่ Propose

ใช้ template `sd-wan-multi-site.md` เป็นฐาน แล้วปรับ:

- **HQ**: Firewall HA pair + SD-WAN Hub + Core/Distribution/Access
- **สาขาใหญ่** (3 สาขา, 30+ users): SD-WAN CPE + PoE switch + WiFi
- **สาขาเล็ก** (9 สาขา, 10-20 users): SD-WAN CPE + PoE switch รวม
- **Underlay**: Fiber primary + 4G LTE backup ทุกสาขา
- **Overlay**: IPSec tunnel back to HQ, QoS policy แยก POS / VoIP / Data

---

## 🗺️ Architecture Diagram

### HQ Network

```mermaid
flowchart TB
    subgraph ISP_HQ["ISP LAYER — HQ"]
        FIBER_HQ["CAT Telecom Fiber\n1 Gbps"]
        LTE_HQ["4G LTE Backup\n100 Mbps"]
    end

    subgraph SEC_HQ["SECURITY LAYER — HQ"]
        FW_ACT["Firewall Active\nFortiGate 200F"]
        FW_STB["Firewall Standby\nFortiGate 200F"]
        SDWAN_HUB["SD-WAN Hub\n(FortiGate HA)"]
    end

    subgraph CORE_HQ["CORE / DISTRIBUTION — HQ DC"]
        CORE_HQ_SW["Core Switch\n48x SFP+ 10G\nL3"]
        DIST_HQ["Distribution Switch\n48x 1G PoE+\n2x 10G Uplink"]
        SRV["Application Servers\nERP / POS Backend"]
        SAN["SAN Storage\nCentralized"]
    end

    subgraph ACC_HQ["ACCESS — HQ Office"]
        ACC_HQ_SW["Access Switch\n24x PoE+"]
        AP_HQ["WiFi 6 AP ×6\nHQ Office"]
    end

    FIBER_HQ --> FW_ACT
    LTE_HQ -. "Backup" .-> FW_ACT
    FW_ACT <--> FW_STB
    FW_ACT --> SDWAN_HUB
    SDWAN_HUB --> CORE_HQ_SW
    CORE_HQ_SW --> DIST_HQ
    CORE_HQ_SW --> SRV
    CORE_HQ_SW --> SAN
    DIST_HQ --> ACC_HQ_SW
    ACC_HQ_SW --> AP_HQ
```

### Branch Network (สาขาใหญ่)

```mermaid
flowchart TB
    subgraph ISP_BR["ISP LAYER — สาขา"]
        FIBER_BR["3BB / AIS Fiber\n300 Mbps"]
        LTE_BR["4G LTE Backup\n50 Mbps"]
    end

    subgraph CPE["SD-WAN CPE"]
        SDWAN_CPE["SD-WAN CPE\nFortiGate 60F\nIPSec → HQ Hub"]
    end

    subgraph ACCESS_BR["ACCESS LAYER — สาขา"]
        POE_SW["PoE+ Switch\n24-port"]
        AP_BR["WiFi 6 AP ×2\nStaff + Guest SSID"]
        POS["POS Terminal ×4\nPoE — VLAN 100"]
        CAM["CCTV Camera ×8\nPoE — VLAN 200"]
        NVR["NVR\nLocal Recording"]
    end

    FIBER_BR --> SDWAN_CPE
    LTE_BR -. "Backup" .-> SDWAN_CPE
    SDWAN_CPE -- "Trunk" --> POE_SW
    POE_SW -- "PoE — VLAN 100" --> POS
    POE_SW -- "PoE — VLAN 200" --> CAM
    POE_SW --> NVR
    POE_SW -- "PoE+" --> AP_BR
```

### Overlay SD-WAN (All Sites)

```mermaid
flowchart LR
    HQ["HQ\nSD-WAN Hub\nFortiGate 200F HA"]

    subgraph LARGE["สาขาใหญ่ ×3"]
        BR_L1["สาขา 1\nFG-60F"]
        BR_L2["สาขา 2\nFG-60F"]
        BR_L3["สาขา 3\nFG-60F"]
    end

    subgraph SMALL["สาขาเล็ก ×9"]
        BR_S1["สาขา 4-12\nFG-40F"]
    end

    HQ <-- "IPSec\nPrimary: Fiber" --> BR_L1
    HQ <-- "IPSec\nPrimary: Fiber" --> BR_L2
    HQ <-- "IPSec\nPrimary: Fiber" --> BR_L3
    HQ <-- "IPSec\nPrimary: Fiber" --> BR_S1
    BR_L1 -. "Failover: LTE" .-> HQ
```

---

## 📐 VLAN Design

| VLAN | ชื่อ | Subnet | Traffic |
|---|---|---|---|
| 10 | Staff | 10.x.10.0/24 | User laptops, workstations |
| 20 | VoIP | 10.x.20.0/24 | IP Phone (QoS DSCP EF) |
| 100 | POS | 10.x.100.0/24 | POS terminal (ลัด HQ เท่านั้น) |
| 200 | CCTV | 10.x.200.0/24 | Camera → NVR (local only) |
| 999 | Guest | 172.16.x.0/24 | Guest WiFi (Internet only) |

> `x` = Branch ID (01-12), HQ = 00

---

## 🔧 QoS Policy

| Traffic | DSCP | Bandwidth Guarantee | Priority |
|---|---|---|---|
| POS (VLAN 100) | EF (46) | 20% reserved | Highest |
| VoIP (VLAN 20) | EF (46) | 15% reserved | High |
| Staff (VLAN 10) | AF21 | Best effort | Normal |
| CCTV (VLAN 200) | CS1 | Max 10 Mbps | Low |
| Guest (VLAN 999) | BE | Max 20 Mbps | Lowest |

---

## 📊 ผลลัพธ์โปรเจกต์

| Metric | Before | After |
|---|---|---|
| Monthly MPLS cost | ~120,000 บาท/เดือน | ~45,000 บาท/เดือน |
| Network downtime (branch) | 3-5 ครั้ง/เดือน | < 1 ครั้ง/เดือน (failover ≤ 30 วินาที) |
| POS transaction timeout | 5-8% | < 0.5% |
| IT management | manual per-site | Centralized FortiManager |

---

## ⏱️ เวลาที่ Claude ช่วยประหยัด

| งาน | เวลาเดิม | เวลาที่ใช้จริง |
|---|---|---|
| วาด HQ diagram | 3-4 ชม. | 20 นาที |
| วาด Branch diagram × 12 | 6-8 ชม. | 30 นาที (batch) |
| VLAN table | 1 ชม. | 10 นาที |
| QoS policy doc | 2 ชม. | 15 นาที |
| **รวม** | **~12-15 ชม.** | **~1.25 ชม.** |

---

## 💡 Lessons Learned

- **PoE budget คือจุดที่มักพลาด** — CCTV 8 กล้อง + 4 POS + 2 AP กิน budget เกือบเต็ม switch 24-port PoE+ (370W) → ต้องตรวจก่อนเสมอ
- **LTE backup latency** — บาง POS vendor ไม่ยอม latency > 80ms → ต้องเลือก carrier ที่ดีในพื้นที่
- **CCTV VLAN แยกออกมา** ทำให้ IT ไม่ต้องกังวลเรื่อง bandwidth กิน staff network อีกต่อไป
- **FortiManager ช่วยลด onboarding branch ใหม่** จาก 2 วัน เหลือ 2 ชั่วโมง

---

## 📌 Related Templates

- SD-WAN topology → [`sd-wan-multi-site.md`](../../templates/pre-sales/sd-wan-multi-site.md)
- VLAN design → [`vlan-segmentation.md`](../../templates/design/vlan-segmentation.md)
- CCTV/IoT zone → ดู Notes ใน `smb-single-site.md`
