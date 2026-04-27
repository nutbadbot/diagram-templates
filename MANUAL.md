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
4. [GitHub Connector — สำคัญมาก อ่านก่อน](#4-github-connector)
5. [Workflow พื้นฐาน](#5-workflow-พื้นฐาน)
6. [ตัวอย่างการใช้งานจริง](#6-ตัวอย่างการใช้งานจริง)
7. [Tips & Tricks](#7-tips--tricks)
8. [คำถามที่พบบ่อย](#8-faq)

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
2. Sign up ด้วย email
3. ยืนยัน email

### ขั้นที่ 2: เลือก Plan

- **Free**: ใช้ได้ แต่จำกัดจำนวนข้อความ
- **Pro** ($20/เดือน): **แนะนำสำหรับใช้งานจริง**

> 💡 แต่ละคนในทีม **สมัครด้วย account ของตัวเอง** ไม่ต้องใช้ account ร่วมกัน

---

## 3. เชื่อมต่อ Tools

### วิธีเปิด Connectors

1. เปิด [claude.ai](https://claude.ai)
2. คลิก **ชื่อตัวเอง** หรือ **icon** มุมซ้ายล่าง
3. เลือก **Settings**
4. คลิก **Connectors**

---

### 🔗 Google Drive

1. Settings → Connectors → ค้นหา **Google Drive**
2. กด **Connect** → Login Google → Allow
3. ✅ เสร็จ

**ใช้ทำอะไร**: Claude บันทึกและอ่านไฟล์จาก Drive ได้โดยตรง

---

### 🔗 Microsoft 365 (OneDrive / SharePoint)

1. Settings → Connectors → ค้นหา **Microsoft 365**
2. กด **Connect** → Login Microsoft → Allow
3. ✅ เสร็จ

**ใช้ทำอะไร**: Claude ค้นหาและอ่านไฟล์จาก SharePoint ได้

> ⚠️ ปัจจุบัน Microsoft 365 connector **อ่านได้อย่างเดียว** — ยังไม่รองรับการ upload ไฟล์เข้า OneDrive

---

### 🔗 Draw.io (Custom Connector)

1. Settings → Connectors → **Add custom connector**
2. ใส่ URL: `https://mcp.draw.io/mcp`
3. ตั้งชื่อ: `Draw_io`
4. กด Save
5. ✅ เสร็จ

**ใช้ทำอะไร**: Claude สร้าง diagram แบบ interactive ได้เลย ไม่ต้อง copy XML

---

## 4. GitHub Connector — สำคัญมาก อ่านก่อน

> ⚠️ **ถ้าข้ามขั้นตอนนี้** Claude จะเข้า template repo ไม่ได้ และจะแสดง error แบบนี้:
>
> *"GitHub blob page ติด robots.txt... ช่วย copy เนื้อหามาให้ได้ไหม"*
>
> วิธีแก้คือต่อ GitHub connector ตามขั้นตอนด้านล่างเลยครับ

---

### GitHub Account ของใครที่ต้องใช้?

**ใช้ GitHub account ของตัวเองครับ** — ไม่ต้องใช้ account คนอื่น

```
แต่ละคนในทีม:
✅ มี Claude account ของตัวเอง
✅ ต่อ GitHub account ของตัวเอง
✅ เข้า repo ของทีมได้ เพราะ repo เป็น Public
```

ถ้ายังไม่มี GitHub account → สมัครฟรีที่ [github.com](https://github.com)

---

### ขั้นตอนต่อ GitHub Connector

**ขั้นที่ 1**: เปิด Claude → Settings → Connectors

**ขั้นที่ 2**: ค้นหา **GitHub Integration** → กด **Connect**

**ขั้นที่ 3**: GitHub จะถามให้ Authorize → กด **Authorize**

**ขั้นที่ 4**: เลือก repo ที่ให้ Claude เข้าถึง
- เลือก **All repositories** (ง่ายสุด)
- หรือเลือกเฉพาะ `diagram-templates` ก็ได้

**ขั้นที่ 5**: กด **Save** ✅ เสร็จ

---

### ทดสอบว่าต่อสำเร็จไหม

พิมพ์ใน Claude:

```
ช่วยดู repo github.com/nutbadbot/diagram-templates
มีไฟล์อะไรบ้างใน templates/network-infrastructure/
```

ถ้า Claude ตอบและแสดงรายการไฟล์ได้ = ✅ สำเร็จ

ถ้า Claude บอกว่าเข้าไม่ได้ = กลับไปเช็ค connector settings

---

### หลังต่อ GitHub แล้ว ใช้ template ยังไง?

พิมพ์แค่นี้พอครับ:

```
ช่วยหา template ที่เหมาะสมจาก
github.com/nutbadbot/diagram-templates
แล้วสร้าง diagram สำหรับ:
- [spec อุปกรณ์]
- [connection/topology]
```

Claude จะหา template เอง → ปรับให้ → สร้าง diagram ให้เลย ✅

---

## 5. Workflow พื้นฐาน

### Workflow A: สร้าง diagram จากศูนย์

```
1. เปิด Claude
2. พิมพ์ prompt บอก spec อุปกรณ์
3. Claude สร้าง diagram
4. เปิดใน Draw.io แก้ไขต่อ
5. Export PNG/PDF
```

**ตัวอย่าง prompt**:
```
ช่วยสร้าง network diagram แบบ Pragma Style สำหรับ:
- Firewall: FortiGate 60F
- Core Switch: Cisco 9300 x2 (stacked, LACP uplink)
- Access Switch: 24-port PoE x4
- AP: 12 ตัว
- Users: 80 คน
```

---

### Workflow B: ใช้ template จาก repo (แนะนำ)

```
1. เปิด Claude (ต้องต่อ GitHub ก่อน)
2. บอกให้หา template ที่ใกล้เคียง
3. Claude อ่าน template → ปรับตาม spec
4. ได้ diagram แบบ Pragma Style ทันที
```

**ตัวอย่าง prompt**:
```
ช่วยหา template ที่เหมาะสมจาก
github.com/nutbadbot/diagram-templates
ปรับเป็น network ของลูกค้า:
- Firewall: FortiGate 70G
- Core: Dell N1524 x2 stacked LACP
- Access Switch: 1 ตัว LACP จาก Core
- AP: 6 ตัว PoE+
- UPS: 3000VA
```

---

### Workflow C: แก้ diagram เดิม

```
1. Upload ไฟล์เดิม (Visio/PNG/PDF)
2. บอก Claude ว่าจะแก้อะไร
3. Claude สร้าง version ใหม่
```

**ตัวอย่าง prompt**:
```
[แนบไฟล์ old-network.png]

นี่คือ diagram เดิม ช่วยปรับให้:
- เปลี่ยน Firewall เป็น FortiGate 100F
- เพิ่ม branch office ที่เชียงใหม่
- เชื่อมด้วย SD-WAN
```

---

## 6. ตัวอย่างการใช้งานจริง

### ✅ ตัวอย่างที่ 1: สร้าง diagram จาก spec

```
ช่วยหา template ที่เหมาะสมจาก
github.com/nutbadbot/diagram-templates
แล้วสร้าง diagram สำหรับ:
- FortiGate 70G x1 (Firewall)
- Dell N1524 x2 (Core, stacked, LACP uplink)
- Cisco SG350 x1 (Access, LACP จาก Core)
- Ruckus R350 x6 (AP, PoE+)
- APC UPS 3000VA x1

แล้วบันทึกเข้า Google Drive ด้วย
ชื่อ: Network-Diagram_[Client]_2026-04-27.drawio
```

### ✅ ตัวอย่างที่ 2: SD-WAN Multi-site

```
ช่วยหา template SD-WAN จาก repo
github.com/nutbadbot/diagram-templates
ปรับสำหรับลูกค้า:
- HQ: Bangkok 200 users, FortiGate 200F
- Branch1: Chiang Mai 50 users, FortiGate 60F
- Branch2: Phuket 40 users, FortiGate 60F
- Internet: AIS Fiber ทุก site
- Backup: 4G LTE ทุก site
```

### ✅ ตัวอย่างที่ 3: เปลี่ยน vendor ใน diagram

```
ใช้ template smb-single-site.md จาก repo
เปลี่ยน Firewall เป็น Sophos XG 135
และเปลี่ยน AP เป็น Ubiquiti U6-Pro
spec อื่นๆ เหมือนเดิม
```

---

## 7. Tips & Tricks

### ✅ เขียน prompt ที่ได้ผลดี

❌ **ไม่ดี**: "วาด network ให้หน่อย"

✅ **ดี**:
```
สร้าง network diagram แบบ Pragma Style:
- Firewall: FortiGate 60F (LACP uplink → Core)
- Core: Cisco 9300 x2 (stacked)
- Access: 48-port PoE+ x4 (LACP จาก Core)
- AP: 12 ตัว (PoE+)
- Users: 100 คน
```

**หลักการ**: บอก **model + จำนวน + การต่อ**

---

### ✅ บันทึกทันทีหลังสร้าง

```
สร้าง diagram นี้แล้วบันทึกเข้า Google Drive ด้วยนะ
ชื่อ: Network-[Client]-[วันที่].drawio
```

ถ้าไม่บันทึก → ปิด chat หายหมด

---

### ✅ ถ้า diagram ผิด บอกตรงๆ

```
Firewall ควรอยู่บน Core ไม่ใช่ใต้ — ช่วยแก้ให้
```

Claude จะแก้ให้ใหม่ทันที ไม่ต้องเริ่มใหม่ทั้งหมด

---

### ❌ สิ่งที่ไม่ควรทำ

- ❌ ใส่ IP จริงของลูกค้าใน prompt
- ❌ ใส่ password หรือ credentials
- ❌ ส่ง config file จริงที่มีข้อมูลลับ

ใช้ placeholder แทน เช่น "Client ABC", "10.x.x.x"

---

## 8. FAQ

### Q: Claude เข้าใจภาษาไทยมั้ย?
A: เข้าใจดีมากครับ — พิมพ์ไทยได้เลย

### Q: ต้องมี GitHub account ไหม?
A: ต้องมีครับ สมัครฟรีที่ [github.com](https://github.com) — ใช้เวลา 2 นาที

### Q: ต้องใช้ GitHub account เดียวกับพี่นัทไหม?
A: **ไม่ครับ** — ใช้ account ของตัวเองได้เลย แค่ต่อ GitHub connector ใน Claude ของตัวเอง แล้วก็เข้า repo ของทีมได้เลยเพราะ repo เป็น Public

### Q: ถ้าไม่ต่อ GitHub แล้ว Claude บอกว่า "copy มาให้หน่อย" ทำยังไง?
A: นั่นแปลว่า **ยังไม่ได้ต่อ GitHub connector** ครับ — กลับไปทำ Section 4 ก่อน ใช้เวลา 2 นาที แล้วจะหายเองเลย

### Q: ข้อมูลลูกค้าปลอดภัยไหม?
A: Claude (Pro plan) ไม่เอา conversation ไป train — แต่ถ้าเป็นข้อมูลลับมากให้ใช้ placeholder แทนชื่อจริง

### Q: ถ้า diagram ไม่แสดงใน Draw.io ทำยังไง?
A: บอก Claude ว่า "diagram เปิดใน Draw.io ไม่ได้ ช่วย fix XML ให้" — Claude จะแก้ให้ทันที

### Q: Google Drive บันทึกไม่ได้ทำยังไง?
A: Settings → Connectors → Google Drive → **Reconnect** — token อาจหมดอายุ

---

## 📞 ต้องการความช่วยเหลือ

- **เจอปัญหา / อยากเพิ่ม template**: เปิด Issue ใน [GitHub repo](https://github.com/nutbadbot/diagram-templates/issues)
- **ถามทีม**: ติดต่อ Nuttawut

---

**อัพเดตล่าสุด**: 2026-04-27
**Version**: 2.0 — เพิ่ม GitHub Connector guide + FAQ ทีม
