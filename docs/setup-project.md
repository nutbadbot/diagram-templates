# 🚀 Setup Claude Project สำหรับงาน Diagram

> ทำครั้งเดียว — แล้วถาม Claude ได้เลยโดยไม่ต้องรู้ชื่อ template

**เวลาที่ใช้**: 5 นาที

---

## 🎯 เป้าหมาย

หลังทำตามคู่มือนี้จบ คุณจะ:
- ✅ มี Claude Project ที่รู้จัก template ของทีมทุกตัว
- ✅ ถามภาษาพูดได้เลย เช่น "ทำ diagram network ลูกค้า 50 คน"
- ✅ Claude เลือก template เองและส่ง Draw.io XML กลับมา

---

## Step 1: สร้าง Project ใหม่

1. เปิด [claude.ai](https://claude.ai)
2. แถบซ้าย → เลื่อนหา **Projects** → กด **+ New Project**
3. ตั้งชื่อ: **`Pragma Diagram Assistant`**
4. กด **Create project**

---

## Step 2: วาง System Prompt

1. ในหน้า Project → กด **Edit project instructions** (หรือ Set project instructions)
2. **ลบข้อความเดิม** ออกให้หมด
3. **Copy ข้อความด้านล่างนี้** แล้ววางลงไป:

```
คุณเป็น diagram assistant ของทีม Pragma (บริษัท SI)

เมื่อมีคนขอ diagram ให้ทำตามนี้เสมอ:

1. เข้าไปดู template ที่ github.com/nutbadbot/diagram-templates
2. เลือก folder ที่เหมาะกับงาน:
   - templates/pre-sales/  → proposal, RFP, นำเสนอลูกค้าเบื้องต้น
   - templates/design/     → HLD, LLD, technical design
   - templates/handover/   → as-built, SOP, process ส่งลูกค้าจบโปรเจกต์
3. ถ้าข้อมูลไม่ครบ ให้ถามก่อน เช่น จำนวน users, อุปกรณ์, vendor
4. ปรับ template ตาม spec แล้วส่ง Draw.io XML กลับมาพร้อมใช้งาน

Pragma Style (ใช้ทุก diagram):
- พื้นหลังสีเข้ม dark theme
- แบ่ง layer ด้วย swimlane มีสีต่างกัน
- Label ภาษาอังกฤษ ยกเว้น note/comment

ใช้ภาษาไทยในการตอบเสมอ ยกเว้น technical term
```

4. กด **Save**

---

## Step 3: เชื่อม GitHub (ถ้ายังไม่ได้ทำ)

Claude ต้องเข้า repo ได้ถึงจะดึง template ได้อัตโนมัติ

1. Settings → Connectors → หา **GitHub**
2. กด **Connect** → Login GitHub
3. Allow permissions → กลับมาที่ Claude
4. เห็น ✅ ข้าง GitHub = พร้อมใช้งาน

> ถ้าไม่ได้เชื่อม GitHub ก็ยังใช้งานได้ — แค่ต้อง copy XML จาก template มาแปะให้ Claude เองครับ

---

## Step 4: ทดสอบ

เข้า Project ที่สร้างแล้วลองพิมพ์:

```
ทำ diagram network ลูกค้า SMB 50 คน single site
มี Firewall Fortinet, Switch HP, WiFi Ubiquiti
ส่ง proposal
```

**ผลที่ควรได้**:
- Claude เข้า repo เลือก template `pre-sales/smb-single-site.md`
- ถามข้อมูลที่ขาด (ถ้ามี)
- ส่ง Draw.io XML กลับมา → copy ไป paste ที่ [app.diagrams.net](https://app.diagrams.net) ได้เลย

---

## 💬 ตัวอย่างการใช้งาน

ถามแบบนี้ได้เลย ไม่ต้องรู้ชื่อ template:

| สิ่งที่ต้องการ | ตัวอย่าง prompt |
|---|---|
| Diagram ส่ง proposal | "ทำ network diagram ลูกค้าโรงงาน 100 คน มี Cisco + Fortinet ส่ง proposal" |
| HLD ส่งลูกค้า | "ทำ Hyper-V cluster diagram 2 node สำหรับ [ชื่อลูกค้า]" |
| Process ส่งจบโปรเจกต์ | "ทำ incident response flow ส่งลูกค้าตอน handover" |
| ปรับ template เดิม | "ปรับ diagram เดิมให้เพิ่ม DR site อีก 1 site" |

---

## 🆘 Troubleshooting

| ปัญหา | วิธีแก้ |
|---|---|
| Claude ไม่เข้า GitHub | เช็ค Connectors → Disconnect แล้ว Connect ใหม่ |
| ไม่เห็นปุ่ม Projects | ต้องเป็น Claude Pro ขึ้นไป |
| XML วาง Draw.io แล้วผิด | ลอง copy ใหม่ให้ครบ ตั้งแต่ `<mxfile` ถึง `</mxfile>` |
| Claude เลือก template ผิด | บอก phase ให้ชัดขึ้น เช่น "ส่ง proposal" หรือ "ส่งลูกค้าตอน handover" |

---

## 📚 อ่านต่อ

- [prompt-library.md](prompt-library.md) — prompt ตัวอย่างครบทุก template
- [setup-claude.md](setup-claude.md) — setup Claude + connectors ครั้งแรก
- [setup-github-mcp.md](setup-github-mcp.md) — (Advanced) เชื่อม GitHub แบบละเอียด
