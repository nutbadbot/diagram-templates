# Pragma Diagram Templates

> คลังเก็บ diagram templates สำหรับทีม Pragma — ใช้ร่วมกับ Claude AI เพื่อสร้าง/แก้ไข diagram แบบรวดเร็ว

[![Made with Claude](https://img.shields.io/badge/Made%20with-Claude-D97757)](https://claude.ai)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Templates](https://img.shields.io/badge/Templates-18-blue)](#)
[![Style](https://img.shields.io/badge/Style-Pragma%20Dark-1a1a2e)](#)

---

## 📖 Repo นี้คืออะไร

เป็นคลังกลางที่เก็บ **diagram templates** ที่ทีม Pragma ใช้งานบ่อย โดยแบ่งเป็น 3 หมวดหลัก:

- 🌐 **Network & Infrastructure** — network topology, rack diagrams, firewall zones, Hyper-V, backup, VLAN
- 🏛️ **System Architecture** — application architecture, cloud architecture, microservices, serverless
- 🔄 **Process & Workflow** — business process flow, CI/CD pipeline, incident response

Template ทุกตัวมี **Pragma Style** (dark theme + layer bars) พร้อม **Draw.io XML** และ **Mermaid** ที่ Claude เอาไปปรับแก้ได้ทันที

> **Vendor-agnostic**: template ทุกตัวออกแบบให้ปรับเปลี่ยนอุปกรณ์/vendor ได้ง่าย ไม่ lock เฉพาะยี่ห้อใด — ดูตาราง Parameters ในแต่ละไฟล์

---

## 🚀 Quick Start

### วิธีใช้งาน (ง่ายที่สุด)

เปิด [Claude](https://claude.ai) แล้วพิมพ์:

```
ช่วยหา template ที่เหมาะสมจาก
github.com/nutbadbot/diagram-templates
แล้วสร้าง diagram สำหรับ:
- [spec อุปกรณ์]
- [จำนวน / ขนาด]
- [connection / topology]
```

Claude จะหา template เอง → ปรับตาม spec → สร้าง diagram ให้เลย ✅

---

## 📂 Templates ทั้งหมด (18 templates)

### 🌐 Network & Infrastructure (11 templates)

| ไฟล์ | ใช้ตอนไหน | Pragma Style |
|---|---|---|
| [3-tier-data-center.md](templates/network-infrastructure/3-tier-data-center.md) | Enterprise DC 100-1,000 users, HA pair | ✅ |
| [smb-single-site.md](templates/network-infrastructure/smb-single-site.md) | SMB 20-100 users, single site | ✅ |
| [sd-wan-multi-site.md](templates/network-infrastructure/sd-wan-multi-site.md) | Multi-site SD-WAN, HQ + branches | ✅ |
| [firewall-dmz-zones.md](templates/network-infrastructure/firewall-dmz-zones.md) | Firewall + DMZ zones, security policy | ✅ |
| [enterprise-wifi-deployment.md](templates/network-infrastructure/enterprise-wifi-deployment.md) | WiFi 6 enterprise, multiple SSIDs | ✅ |
| [hyper-v-failover-cluster.md](templates/network-infrastructure/hyper-v-failover-cluster.md) | Hyper-V Failover Cluster 2+ nodes, CSV, Live Migration | ✅ |
| [backup-architecture.md](templates/network-infrastructure/backup-architecture.md) | Enterprise Backup — 3-2-1 rule, on-prem + cloud | ✅ |
| [vlan-segmentation.md](templates/network-infrastructure/vlan-segmentation.md) | VLAN design, inter-VLAN routing, zone isolation | ✅ |
| [rack-elevation-42u.md](templates/network-infrastructure/rack-elevation-42u.md) | 42U rack layout, front view, U position, BOM | ✅ |
| [spine-leaf-fabric.md](templates/network-infrastructure/spine-leaf-fabric.md) | Modern DC Spine-Leaf (Clos), VXLAN/EVPN, East-West traffic | ✅ |
| [voip-deployment.md](templates/network-infrastructure/voip-deployment.md) | Enterprise VoIP/UC, SIP Trunk, IP PBX, Voice VLAN, QoS | ✅ |

### 🏛️ System Architecture (4 templates)

| ไฟล์ | ใช้ตอนไหน | Pragma Style |
|---|---|---|
| [3-tier-web-app.md](templates/system-architecture/3-tier-web-app.md) | Traditional web app (Presentation/App/Data) | ✅ |
| [microservices-aws.md](templates/system-architecture/microservices-aws.md) | Microservices + Service Mesh, EKS/ECS, event-driven | ✅ |
| [azure-landing-zone.md](templates/system-architecture/azure-landing-zone.md) | Azure Landing Zone (CAF), Hub-Spoke VNet, Governance | ✅ |
| [serverless-aws.md](templates/system-architecture/serverless-aws.md) | Serverless, Functions, Event Bus, Queue, NoSQL | ✅ |

### 🔄 Process & Workflow (3 templates)

| ไฟล์ | ใช้ตอนไหน | Pragma Style |
|---|---|---|
| [approval-workflow.md](templates/process-flow/approval-workflow.md) | Approval swimlane หลาย actor, decision points | ✅ |
| [cicd-pipeline.md](templates/process-flow/cicd-pipeline.md) | CI/CD pipeline — Build, Test, Deploy to production | ✅ |
| [incident-response.md](templates/process-flow/incident-response.md) | Incident response — Detect, Triage, DR, Post-mortem | ✅ |

---

## 🎨 Pragma Style

ทุก template ใช้ **Pragma Dark Style** มาตรฐาน:

| Layer | สี | ใช้สำหรับ |
|---|---|---|
| Internet / WAN | น้ำเงินเข้ม | Cloud, ISP, External endpoint |
| Security | น้ำตาลแดง | Firewall, WAF, Gateway, SBC |
| Core / Compute | เขียวเข้ม | Core switch, Server, K8s, Function |
| Access / Edge | ม่วงเข้ม | Access switch, Voice VLAN, Queue |
| Data | ฟ้าเข้ม | Database, Storage, Cache |
| Reject / Error | แดงเข้ม | Error state, Reject node, Block |
| Endpoint | เทาเข้ม | PC, Phone, End device |

> **Vendor-agnostic**: icon และ label ในแต่ละ template ไม่ lock vendor — ปรับยี่ห้ออุปกรณ์ได้ตาม Parameters ของแต่ละไฟล์

---

## 📂 โครงสร้าง Repo

```
diagram-templates/
├── README.md                         ← ไฟล์นี้
├── MANUAL.md                         ← คู่มือหลัก — อ่านก่อนใช้
├── CONTRIBUTING.md                   ← วิธีเพิ่ม template ใหม่
├── templates/
│   ├── network-infrastructure/       ← 11 templates ✅ Pragma Style
│   ├── system-architecture/          ← 4 templates ✅ Pragma Style
│   └── process-flow/                 ← 3 templates ✅ Pragma Style
├── docs/
│   ├── setup-claude.md               ← setup Claude + connectors
│   ├── prompt-library.md             ← prompt ที่ใช้ได้ผลจริง
│   ├── setup-github-mcp.md           ← (Advanced) เชื่อม GitHub กับ Claude
│   └── team-workflow-ideas.md        ← framework งาน SI + Claude
└── examples/
    └── README.md                     ← ตัวอย่าง diagram
```

---

## 📚 เอกสารสำคัญ

| ไฟล์ | เนื้อหา |
|---|---|
| [MANUAL.md](MANUAL.md) | คู่มือหลัก — อ่านก่อนใช้ครั้งแรก |
| [docs/prompt-library.md](docs/prompt-library.md) | prompt ตัวอย่างสำหรับงาน SI |
| [docs/setup-claude.md](docs/setup-claude.md) | วิธี setup Claude + connectors |
| [docs/team-workflow-ideas.md](docs/team-workflow-ideas.md) | framework งานซ้ำๆ ที่ Claude ช่วยได้ |

---

## 🔜 Roadmap

ไม่มี template ที่ค้างอยู่ตอนนี้ — ถ้าต้องการ template เพิ่ม เปิด [Issue](https://github.com/nutbadbot/diagram-templates/issues) ได้เลยครับ

---

## 🤝 ทีม

Repo นี้ดูแลโดยทีม Pragma — ทุกคนใน team สามารถ contribute template ใหม่ได้ ดูวิธีที่ [CONTRIBUTING.md](CONTRIBUTING.md)

**ติดต่อ**: [Nuttawut](https://github.com/nutbadbot)

---

## 📝 License

MIT License — ใช้ภายในองค์กร/ส่วนตัวได้อิสระ
