# Pragma Diagram Templates

> คลังเก็บ diagram templates สำหรับทีม Pragma — ใช้ร่วมกับ Claude AI เพื่อสร้าง/แก้ไข diagram แบบรวดเร็ว

[![Made with Claude](https://img.shields.io/badge/Made%20with-Claude-D97757)](https://claude.ai)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## 📖 Repo นี้คืออะไร

เป็นคลังกลางที่เก็บ **diagram templates** ที่ทีม Pragma ใช้งานบ่อย โดยแบ่งเป็น 3 หมวดหลัก:

- 🌐 **Network & Infrastructure** — network topology, rack diagrams, firewall zones
- 🏛️ **System Architecture** — application architecture, cloud architecture, microservices
- 🔄 **Process & Workflow** — business process flow, approval flow, deployment pipeline

Template ทุกตัวอยู่ในรูป **Draw.io XML** หรือ **Mermaid** ที่พร้อมให้ Claude เอาไปปรับแก้ได้ทันที

---

## 🚀 Quick Start

### สำหรับคนที่จะหยิบ template ไปใช้

1. เลือก template จากโฟลเดอร์ `templates/`
2. Copy เนื้อหาไฟล์
3. เปิด [Claude](https://claude.ai) แล้วส่ง prompt พร้อม template:

```
นี่คือ diagram template ของทีม:
[paste template ที่นี่]

ช่วยปรับให้เป็น [ระบุสิ่งที่ต้องการ เช่น "network ของลูกค้า A ที่มี 3 sites"]
```

### สำหรับคนที่จะเพิ่ม template ใหม่

ดูที่ [CONTRIBUTING.md](CONTRIBUTING.md)

---

## 📂 โครงสร้าง Repo

```
diagram-templates/
├── README.md                    ← ไฟล์นี้
├── MANUAL.md                    ← วิธี setup Claude + ตัวอย่าง prompts
├── CONTRIBUTING.md              ← วิธีเพิ่ม template ใหม่
├── templates/
│   ├── network-infrastructure/  ← network, rack, firewall
│   ├── system-architecture/     ← app, cloud, microservices
│   └── process-flow/            ← workflow, approval, pipeline
├── docs/
│   ├── setup-claude.md          ← setup Claude + connectors
│   ├── prompt-library.md        ← prompt ที่ใช้ได้ผลจริง
│   └── setup-github-mcp.md      ← (Advanced) เชื่อม GitHub กับ Claude
└── examples/
    └── before-after/            ← ตัวอย่าง diagram ก่อน/หลังให้ Claude แก้
```

---

## 📚 เอกสารสำคัญ

| ไฟล์ | เนื้อหา |
|---|---|
| [MANUAL.md](MANUAL.md) | คู่มือหลัก — อ่านก่อนใช้ครั้งแรก |
| [docs/setup-claude.md](docs/setup-claude.md) | วิธี setup Claude + เชื่อม Google Drive, OneDrive |
| [docs/prompt-library.md](docs/prompt-library.md) | prompt ตัวอย่างสำหรับงาน SI |
| [docs/setup-github-mcp.md](docs/setup-github-mcp.md) | (Advanced) ต่อ GitHub เข้า Claude โดยตรง |

---

## 🤝 ทีม

Repo นี้ดูแลโดยทีม Pragma — ทุกคนใน team สามารถ contribute template ใหม่ได้

**ติดต่อ**: [Nuttawut](https://github.com/nutbadbot)

---

## 📝 License

MIT License — ใช้ภายในองค์กร/ส่วนตัวได้อิสระ
