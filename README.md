# Pragma Diagram Templates

> คลังเก็บ diagram templates สำหรับทีม Pragma — ใช้ร่วมกับ Claude AI เพื่อสร้าง/แก้ไข diagram แบบรวดเร็ว

[![Made with Claude](https://img.shields.io/badge/Made%20with-Claude-D97757)](https://claude.ai)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Templates](https://img.shields.io/badge/Templates-23-blue)](#)
[![Style](https://img.shields.io/badge/Style-Pragma%20Dark-1a1a2e)](#)

---

## 📖 Repo นี้คืออะไร

เป็นคลังกลางที่เก็บ **diagram templates** ที่ทีม Pragma ใช้งานบ่อย แบ่งตาม **phase ของโปรเจกต์ SI** เพื่อให้หา template ได้ตรงกับงานที่ทำอยู่:

- 🎯 **Pre-Sales** — diagram สำหรับ proposal / ตอบ RFP / นำเสนอลูกค้าเบื้องต้น
- 📐 **Design** — diagram สำหรับ HLD / LLD / technical design ส่งลูกค้า
- 📦 **Handover** — diagram สำหรับ as-built / SOP / process ส่งลูกค้าตอนจบโปรเจกต์

Template ทุกตัวมี **Pragma Style** (dark theme + layer bars) พร้อม **Draw.io XML** และ **Mermaid** ที่ Claude เอาไปปรับแก้ได้ทันที

> **Vendor-agnostic**: template ทุกตัวออกแบบให้ปรับเปลี่ยนอุปกรณ์/vendor ได้ง่าย ไม่ lock เฉพาะยี่ห้อใด — ดูตาราง Parameters ในแต่ละไฟล์

---

## 🚀 Quick Start

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

## 📂 Templates ทั้งหมด (23 templates)

### 🎯 Pre-Sales (7 templates)
> ใช้ตอน proposal / RFP / นำเสนอลูกค้าเบื้องต้น

| ไฟล์ | ใช้ตอนไหน | Pragma Style |
|---|---|---|
| [smb-single-site.md](templates/pre-sales/smb-single-site.md) | SMB 20-100 users, single site | ✅ |
| [3-tier-data-center.md](templates/pre-sales/3-tier-data-center.md) | Enterprise DC 100-1,000 users, HA pair | ✅ |
| [sd-wan-multi-site.md](templates/pre-sales/sd-wan-multi-site.md) | Multi-site SD-WAN, HQ + branches | ✅ |
| [3-tier-web-app.md](templates/pre-sales/3-tier-web-app.md) | Traditional web app (Presentation/App/Data) | ✅ |
| [microservices-aws.md](templates/pre-sales/microservices-aws.md) | Microservices + Service Mesh, EKS/ECS, event-driven | ✅ |
| [azure-landing-zone.md](templates/pre-sales/azure-landing-zone.md) | Azure Landing Zone (CAF), Hub-Spoke VNet, Governance | ✅ |
| [serverless-aws.md](templates/pre-sales/serverless-aws.md) | Serverless, Functions, Event Bus, Queue, NoSQL | ✅ |

### 📐 Design (13 templates)
> ใช้ตอน HLD / LLD / technical design ส่งลูกค้า

| ไฟล์ | ใช้ตอนไหน | Pragma Style |
|---|---|---|
| [hyper-v-failover-cluster.md](templates/design/hyper-v-failover-cluster.md) | Hyper-V Failover Cluster 2+ nodes, CSV, Live Migration | ✅ |
| [vlan-segmentation.md](templates/design/vlan-segmentation.md) | VLAN design, inter-VLAN routing, zone isolation | ✅ |
| [firewall-dmz-zones.md](templates/design/firewall-dmz-zones.md) | Firewall + DMZ zones, security policy | ✅ |
| [enterprise-wifi-deployment.md](templates/design/enterprise-wifi-deployment.md) | WiFi 6 enterprise, multiple SSIDs | ✅ |
| [spine-leaf-fabric.md](templates/design/spine-leaf-fabric.md) | Modern DC Spine-Leaf (Clos), VXLAN/EVPN, East-West traffic | ✅ |
| [voip-deployment.md](templates/design/voip-deployment.md) | Enterprise VoIP/UC, SIP Trunk, IP PBX, Voice VLAN, QoS | ✅ |
| [backup-architecture.md](templates/design/backup-architecture.md) | Enterprise Backup — 3-2-1 rule, on-prem + cloud | ✅ |
| [rack-elevation-42u.md](templates/design/rack-elevation-42u.md) | 42U rack layout, front view, U position, BOM | ✅ |
| [vsan-cluster.md](templates/design/vsan-cluster.md) | VMware vSAN 3-node, 10GbE switch-independent teaming, witness | ✅ |
| [ad-ds-topology.md](templates/design/ad-ds-topology.md) | Active Directory DS, DC multi-site, FSMO, replication, DNS | ✅ |
| [iscsi-san-multipath.md](templates/design/iscsi-san-multipath.md) | iSCSI SAN dual-controller, MPIO multipath, redundant fabric | ✅ |
| [fortigate-ha.md](templates/design/fortigate-ha.md) | FortiGate HA Active-Passive, heartbeat, FortiLink, failover | ✅ |
| [ot-purdue-model.md](templates/design/ot-purdue-model.md) | OT/ICS network ตาม Purdue Model — L0–L4 + Industrial DMZ, IEC 62443 | ✅ |

### 📦 Handover (3 templates)
> ใช้ตอน as-built / SOP / process ส่งลูกค้าจบโปรเจกต์

| ไฟล์ | ใช้ตอนไหน | Pragma Style |
|---|---|---|
| [approval-workflow.md](templates/handover/approval-workflow.md) | Approval swimlane หลาย actor, decision points | ✅ |
| [cicd-pipeline.md](templates/handover/cicd-pipeline.md) | CI/CD pipeline — Build, Test, Deploy to production | ✅ |
| [incident-response.md](templates/handover/incident-response.md) | Incident response — Detect, Triage, DR, Post-mortem | ✅ |

### 📖 Case Studies & Before-After Examples
> ตัวอย่างการนำ template ไปใช้จริง

| ไฟล์ | เนื้อหา |
|---|---|
| [examples/before-after/smb-rough-to-pragma.md](examples/before-after/smb-rough-to-pragma.md) | แปลง rough sketch → Pragma Style diagram |
| [examples/case-studies/hospital-network-upgrade.md](examples/case-studies/hospital-network-upgrade.md) | Case study: upgrade network โรงพยาบาล |
| [examples/case-studies/retail-multi-branch.md](examples/case-studies/retail-multi-branch.md) | Case study: retail chain หลายสาขา |

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
│   ├── pre-sales/                    ← 7 templates ✅ Pragma Style
│   ├── design/                       ← 13 templates ✅ Pragma Style
│   └── handover/                     ← 3 templates ✅ Pragma Style
├── docs/
│   ├── setup-claude.md               ← setup Claude + connectors
│   ├── prompt-library.md             ← prompt ที่ใช้ได้ผลจริง
│   ├── setup-github-mcp.md           ← (Advanced) เชื่อม GitHub กับ Claude
│   ├── setup-project.md              ← setup repo + project settings
│   ├── team-test-prompts.md          ← prompt ชุดทดสอบสำหรับทีม
│   ├── team-workflow-ideas.md        ← framework งาน SI + Claude
│   └── audit-report.md              ← ผลตรวจสอบ template 22 ไฟล์
└── examples/
    ├── README.md                     ← index ตัวอย่าง
    ├── before-after/
    │   └── smb-rough-to-pragma.md    ← แปลง rough sketch → Pragma Style
    └── case-studies/
        ├── hospital-network-upgrade.md   ← case study โรงพยาบาล
        └── retail-multi-branch.md        ← case study retail หลายสาขา
```

---

## 📚 เอกสารสำคัญ

| ไฟล์ | เนื้อหา |
|---|---|
| [MANUAL.md](MANUAL.md) | คู่มือหลัก — อ่านก่อนใช้ครั้งแรก |
| [docs/prompt-library.md](docs/prompt-library.md) | prompt ตัวอย่างสำหรับงาน SI |
| [docs/setup-claude.md](docs/setup-claude.md) | วิธี setup Claude + connectors |
| [docs/setup-github-mcp.md](docs/setup-github-mcp.md) | (Advanced) เชื่อม GitHub กับ Claude |
| [docs/team-workflow-ideas.md](docs/team-workflow-ideas.md) | framework งานซ้ำๆ ที่ Claude ช่วยได้ |
| [docs/team-test-prompts.md](docs/team-test-prompts.md) | prompt ชุดทดสอบสำหรับทีม |

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
