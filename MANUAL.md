# 📘 MANUAL: การใช้ Claude + Diagram Templates

> คู่มือสำหรับทีม Pragma — เริ่มต้นจากศูนย์จนใช้ Claude สร้าง/แก้ diagram ได้

---

## 🎯 คู่มือนี้เหมาะกับใคร

- 👤 คนในทีม Pragma ที่อยากใช้ Claude ช่วยงาน diagram
- 🆕 ไม่เคยใช้ Claude มาก่อน ก็อ่านได้
- 🔧 ไม่ต้องเป็น developer

**เวลาที่ใช้**: ประมาณ 15-20 นาทีสำหรับ setup ครั้งแรก

---

## 📋 สารบัญ

1. [Claude คืออะไร ทำไมต้องใช้](#1-claude-คืออะไร)
2. [Setup บัญชี Claude](#2-setup-บัญชี-claude)
3. [เชื่อมต่อ Tools ที่จำเป็น](#3-เชื่อมต่อ-tools)
4. [Workflow พื้นฐาน](#4-workflow-พื้นฐาน)
5. [ตัวอย่างการใช้งานจริง](#5-ตัวอย่างการใช้งานจริง)
6. [Tips & Tricks](#6-tips--tricks)
7. [คำถามที่พบบ่อย](#7-faq)

---

## 1. Claude คืออะไร

Claude คือ AI ผู้ช่วย (เหมือน ChatGPT) ของบริษัท Anthropic ที่เราใช้ช่วยงาน diagram ได้ 3 อย่างหลัก:

✅ **สร้าง diagram ใหม่** จากคำอธิบาย
✅ **แก้ไข diagram เดิม** ที่ให้ไป (Visio, PDF, รูป)
✅ **อธิบาย diagram** ที่เข้าใจยาก

### ทำไมต้องใช้ Claude แทน Draw.io ล้วนๆ

| งาน | ทำเอง | ใช้ Claude |
|---|---|---|
| วาด network 3-tier | 30 นาที | 2 นาที |
| แก้ diagram ลูกค้าเดิม | 1 ชั่วโมง | 5 นาที |
| เปลี่ยน format (Visio → Draw.io) | 45 นาที | 1 นาที |

---

## 2. Setup บัญชี Claude

### ขั้นที่ 1: สมัครสมาชิก

1. ไปที่ [claude.ai](https://claude.ai)
2. Sign up ด้วย email บริษัท (ถ้ามี)
3. ยืนยัน email

### ขั้นที่ 2: เลือก Plan

- **Free**: ใช้ได้ แต่จำกัดจำนวนข้อความ
- **Pro** ($20/เดือน): **แนะนำสำหรับใช้งานจริง** — ใช้ Claude 4 รุ่นล่าสุดได้ + Projects + Connectors
- **Team** ($25/user/เดือน): ถ้าทั้งทีมใช้ — แชร์ Projects ได้

💡 **แนะนำ**: เริ่มด้วย Pro ก่อน ถ้าทีมใช้ 3+ คนเป็นประจำ ค่อยอัพเป็น Team

---

## 3. เชื่อมต่อ Tools

Claude มี "Connectors" ให้เชื่อมกับ tool อื่นๆ ได้ — ทีม Pragma ควรเชื่อม 3 อันนี้:

### 🔗 3.1 Google Drive (ถ้าใช้)

**ทำไม**: เพื่อให้ Claude อ่านไฟล์จาก Drive ได้โดยตรง ไม่ต้อง download มา upload ใหม่

**วิธี**:
1. เปิด Claude → Settings (มุมซ้ายล่าง) → **Connectors**
2. หา **Google Drive** → กด **Connect**
3. Login ด้วย Google account ที่มีไฟล์
4. Authorize

### 🔗 3.2 OneDrive / SharePoint ⭐ (หลักของทีม)

**ทำไม**: ทีม Pragma เก็บ diagram เดิมไว้ที่นี่

**วิธี**:
1. Settings → Connectors
2. หา **OneDrive** หรือ **SharePoint**
3. Connect → Login ด้วย Microsoft 365 account
4. Authorize

**หลัง Connect แล้วทำอะไรได้**:
- "ช่วยดึง diagram ชื่อ xxx จาก SharePoint มาแก้ให้หน่อย"
- "ไปดูใน folder Projects/ClientA แล้วสรุป architecture ให้ที"

### 🔗 3.3 Draw.io (สำคัญมาก)

**ทำไม**: Claude จะสร้าง diagram ออกมาให้เป็น Draw.io โดยตรง เปิดแก้ไขต่อได้เลย

**วิธี**:
1. Settings → Connectors
2. หา **Draw.io**
3. Connect (ไม่ต้อง login — ใช้ได้เลย)

### 🔗 3.4 GitHub (Advanced)

ดู [docs/setup-github-mcp.md](docs/setup-github-mcp.md) — ต้องมี developer tools

---

## 4. Workflow พื้นฐาน

### Workflow A: สร้าง diagram จากศูนย์

```
1. เปิด Claude
2. พิมพ์ prompt อธิบายสิ่งที่ต้องการ
3. Claude สร้าง diagram ออกมา
4. กด "Open in draw.io" เพื่อแก้ไขต่อ
5. Export เป็น PNG/PDF/Visio
```

**ตัวอย่าง prompt**:
```
ช่วยวาด network diagram แบบ 3-tier สำหรับ data center ที่มี:
- Core layer: 2 switches (redundant)
- Distribution layer: 4 switches
- Access layer: 12 switches (3 ต่อ floor, 4 floors)
- Firewall คั่น Core กับ Internet
- ใช้ Cisco icons
```

### Workflow B: แก้ไข diagram เดิม

```
1. Upload ไฟล์ diagram เดิม (Visio/PDF/PNG)
2. บอก Claude ว่าจะแก้อะไร
3. Claude สร้าง version ใหม่
4. เปรียบเทียบก่อน-หลัง
```

**ตัวอย่าง prompt**:
```
[แนบไฟล์ old-network.vsdx]

ช่วยทำ diagram เดียวกันแต่:
- เปลี่ยน firewall เป็น Fortinet
- เพิ่ม DMZ zone
- เปลี่ยน label เป็นภาษาอังกฤษ
```

### Workflow C: ใช้ template จาก repo

```
1. เปิด template จาก repo (เช่น templates/network-infrastructure/3-tier-basic.md)
2. Copy XML/Mermaid content
3. Paste ให้ Claude พร้อมบอกว่าจะปรับอะไร
4. Claude ปรับให้แล้วเปิดใน Draw.io
```

**ตัวอย่าง prompt**:
```
นี่คือ template มาตรฐานของทีม:
[paste XML]

ช่วยปรับให้เป็น network สำหรับลูกค้า Bank ABC ที่มี:
- 3 สาขา (HQ, Branch 1, Branch 2)
- MPLS เชื่อม HQ กับ branches
- Internet breakout ที่ HQ
```

---

## 5. ตัวอย่างการใช้งานจริง

### ✅ ตัวอย่างที่ 1: ดึง Visio จาก SharePoint มาแก้

```
ช่วยไปที่ SharePoint folder "Projects/ClientABC/Architecture"
เปิดไฟล์ชื่อ "network-v2.vsdx"
แล้วสร้างเวอร์ชันใหม่ที่:
- เพิ่ม branch office ใหม่ที่เชียงใหม่
- เชื่อมด้วย SD-WAN แทน MPLS
- Export เป็น Draw.io format
```

### ✅ ตัวอย่างที่ 2: แปลง PDF เป็น editable diagram

```
[แนบ PDF ที่มี diagram ข้างใน]

PDF หน้า 5 มี network diagram
ช่วยสร้าง diagram เดียวกันแต่ editable เป็น Draw.io
ให้ icon ตรงกับของเดิม
```

### ✅ ตัวอย่างที่ 3: สร้าง doc ประกอบ diagram

```
นี่คือ architecture diagram ของระบบลูกค้า:
[paste diagram หรือ upload รูป]

ช่วยเขียน architecture document ประกอบ:
- Overview
- Component descriptions
- Data flow
- Security considerations
ภาษาไทย, format markdown
```

---

## 6. Tips & Tricks

### 🎯 เขียน prompt ให้ได้ผลดี

❌ **ไม่ดี**: "วาด network ให้หน่อย"

✅ **ดี**: "วาด network 3-tier สำหรับ data center — Core 2 switches redundant, Distribution 4, Access 12 (3/floor x 4 floors), firewall คั่น Internet, ใช้ Cisco icons"

**หลักการ**: บอก **ปริมาณ**, **ยี่ห้อ/icon set**, **ความสัมพันธ์**, **style ที่ต้องการ**

### 🎯 ใช้ Projects สำหรับงานประจำ

Projects คือ workspace ที่จดจำ context ได้ — สร้าง project สำหรับลูกค้าแต่ละราย:
- Upload context docs ของลูกค้าไว้
- Claude จะอ้างอิงได้ทุก chat ในโปรเจกต์นั้น

### 🎯 บอก Claude ให้ใช้ template

```
ก่อนตอบคำถาม ให้อ้างอิง template จาก:
https://github.com/nutbadbot/diagram-templates
ในหมวด network-infrastructure
```

### 🎯 Export หลายรูปแบบ

หลัง Claude สร้าง diagram ใน Draw.io แล้ว Export ได้:
- **PNG** — ใส่ในเอกสาร Word
- **PDF** — ส่งให้ลูกค้า
- **XML (.drawio)** — แก้ต่อทีหลัง
- **Visio (.vsdx)** — ถ้าลูกค้าขอ

---

## 7. FAQ

### Q: Claude เข้าใจภาษาไทยมั้ย

A: เข้าใจดีมาก — พิมพ์ prompt ภาษาไทย, สั่งให้ label เป็นไทยหรืออังกฤษก็ได้

### Q: ข้อมูลลูกค้าปลอดภัยมั้ย

A: Claude (Pro/Team plan) ไม่เอา conversation ไป train model — แต่ถ้าเป็นข้อมูลลับมาก แนะนำให้ mask ข้อมูล เช่น ใช้ "Client A" แทนชื่อจริง

### Q: ถ้า Claude สร้าง diagram ผิดต้องทำยังไง

A: บอกตรงๆ ว่าผิดตรงไหน เช่น "Firewall ควรอยู่หน้า Core ไม่ใช่หลัง" — Claude จะแก้ให้ใหม่

### Q: ใช้ Claude แล้วยังต้องมี Draw.io desktop มั้ย

A: ไม่จำเป็น — ใช้ Draw.io web (app.diagrams.net) ก็พอ ฟรีด้วย

### Q: ทีมอื่นจะ pull template ไปใช้ยังไง

A:
```bash
# Clone repo มาทั้งก้อน
git clone https://github.com/nutbadbot/diagram-templates.git

# หรือ download เฉพาะไฟล์ที่ต้องการ (ไม่ต้องใช้ git)
# ไปที่ GitHub web → คลิกไฟล์ → กด "Raw" → Save
```

---

## 📞 ต้องการความช่วยเหลือ

- เจอบัค/อยากเพิ่ม template: [เปิด Issue](https://github.com/nutbadbot/diagram-templates/issues)
- ถามทีม: [ติดต่อ Nuttawut]

---

**อัพเดตล่าสุด**: 2026-04-24
**Version**: 1.0
