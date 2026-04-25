# Pragma Diagram Templates

> คลังเก็บ diagram templates สำหรับทีม Pragma — ใช้ร่วมกับ Claude AI เพื่อสร้าง/แก้ไข diagram แบบรวดเร็ว

[![Made with Claude](https://img.shields.io/badge/Made%20with-Claude-D97757)](https://claude.ai)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Templates](https://img.shields.io/badge/Templates-7-blue)](#)
[![Style](https://img.shields.io/badge/Style-Pragma%20Dark-1a1a2e)](#)

---

## 📖 Repo นี้คืออะไร

เป็นคลังกลางที่เก็บ **diagram templates** ที่ทีม Pragma ใช้งานบ่อย โดยแบ่งเป็น 3 หมวดหลัก:

- 🌐 **Network & Infrastructure** — network topology, rack diagrams, firewall zones
- 🏛️ **System Architecture** — application architecture, cloud architecture, microservices
- 🔄 **Process & Workflow** — business process flow, approval flow, deployment pipeline

Template ทุกตัวมี **Pragma Style** (dark theme + Cisco icons + layer bars) พร้อม **Draw.io XML** และ **Mermaid** ที่ Claude เอาไปปรับแก้ได้ทันที

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

## 📂 Templates ทั้งหมด (7 templates)

### 🌐 Network & Infrastructure (5 templates)

| ไฟล์ | ใช้ตอนไหน | Pragma Style |
|---|---|---|
| [3-tier-data-center.md](templates/network-infrastructure/3-tier-data-center.md) | Enterprise DC 100-1000 users, HA pair | ✅ |
| [smb-single-site.md](templates/network-infrastructure/smb-single-site.md) | SMB 20-100 users, single site | ✅ |
| [sd-wan-multi-site.md](templates/network-infrastructure/sd-wan-multi-site.md) | Multi-site SD-WAN, HQ + branches | ✅ |
| [firewall-dmz-zones.md](templates/network-infrastructure/firewall-dmz-zones.md) | Firewall + DMZ zones, security policy | ✅ |
| [enterprise-wifi-deployment.md](templates/network-infrastructure/enterprise-wifi-deployment.md) | WiFi 6 enterprise, multiple SSIDs | ✅ |

### 🏛️ System Architecture (1 template)

| ไฟล์ | ใช้ตอนไหน | Pragma Style |
|---|---|---|
| [3-tier-web-app.md](templates/system-architecture/3-tier-web-app.md) | Traditional web app (Presentation/App/Data) | 🔜 |

### 🔄 Process & Workflow (1 template)

| ไฟล์ | ใช้ตอนไหน | Pragma Style |
|---|---|---|
| [approval-workflow.md](templates/process-flow/approval-workflow.md) | Generic approval workflow (swimlane) | 🔜 |

---

## 🎨 Pragma Style

ทุก Network template ใช้ **Pragma Dark Style** มาตรฐาน:

| Layer | สี | อุปกรณ์ |
|---|---|---|
| Internet / ISP | น้ำเงินเข้ม | Router, ISP, Cloud |
| Security | น้ำตาลแดง | Firewall, UTM, SD-WAN Edge |
| Core | เขียวเข้ม | L3 Switch, Core Switch |
| Access | ม่วงเข้ม | L2 Switch, PoE Switch |
| Wireless | ฟ้าอ่อน | WiFi AP, Controller |
| End Devices | เทาเข้ม | PC, Laptop, Phone |
| Power | เทาเข้ม | UPS |

---

## 📂 โครงสร้าง Repo

```
diagram-templates/
├── README.md                         ← ไฟล์นี้
├── MANUAL.md                         ← คู่มือหลัก — อ่านก่อนใช้
├── CONTRIBUTING.md                   ← วิธีเพิ่ม template ใหม่
├── templates/
│   ├── network-infrastructure/       ← 5 templates ✅ Pragma Style
│   ├── system-architecture/          ← 1 template
│   └── process-flow/                 ← 1 template
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

### Network & Infrastructure
- [ ] `spine-leaf-fabric.md` — Modern DC Spine-Leaf topology
- [ ] `rack-elevation-42u.md` — 42U rack diagram
- [ ] `voip-deployment.md` — VoIP deployment

### System Architecture
- [ ] `microservices-aws.md` — Microservices + API Gateway บน AWS
- [ ] `azure-landing-zone.md` — Azure Landing Zone
- [ ] `serverless-aws.md` — Serverless (Lambda + API GW + DynamoDB)

### Process & Workflow
- [ ] `cicd-pipeline.md` — CI/CD pipeline
- [ ] `incident-response.md` — Incident response process

---

## 🤝 ทีม

Repo นี้ดูแลโดยทีม Pragma — ทุกคนใน team สามารถ contribute template ใหม่ได้

**ติดต่อ**: [Nuttawut](https://github.com/nutbadbot)

---

## 📝 License

MIT License — ใช้ภายในองค์กร/ส่วนตัวได้อิสระ
