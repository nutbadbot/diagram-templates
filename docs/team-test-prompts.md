# 🧪 Pragma Claude Test Prompts
### สำหรับทีม Pragma — ทดสอบก่อนใช้งานจริง

> **วิธีใช้**: ทำตามลำดับ Level 1 → 2 → 3
> แต่ละ Level ใช้เวลาประมาณ 5-10 นาที
> ถ้าผ่านครบ 3 Level = พร้อมใช้งานจริงแล้ว ✅

---

## ✅ Checklist ก่อนเริ่ม

- [ ] สมัคร Claude account แล้ว (claude.ai)
- [ ] ต่อ **GitHub connector** แล้ว (สำคัญมาก!)
- [ ] ต่อ **Google Drive connector** แล้ว (ถ้ามี)
- [ ] ต่อ **Draw.io connector** แล้ว

> ถ้ายังไม่ได้ต่อ → อ่าน MANUAL.md Section 3-4 ก่อนนะครับ

---

## 🟢 Level 1 — ทดสอบพื้นฐาน (ไม่ต้องใช้ connector)

ทดสอบว่า Claude ทำงานได้ปกติ

---

### Test 1.1 — ถามตรงๆ

**คัดลอก prompt นี้ไปวางใน Claude:**

```
สวัสดีครับ ผมเป็นทีม Pragma บริษัท SI
ช่วยอธิบายให้ฟังหน่อยว่า SD-WAN ต่างจาก MPLS ยังไง
อธิบายสั้นๆ ภาษาไทย ใน 5 ข้อ
```

**ผลที่ควรได้**: Claude ตอบเป็นภาษาไทย อธิบาย 5 ข้อ ชัดเจน

---

### Test 1.2 — สร้าง Diagram เบื้องต้น

```
ช่วยสร้าง network diagram อย่างง่ายสำหรับออฟฟิศเล็กๆ
มีแค่:
- Internet 1 เส้น
- Firewall 1 ตัว
- Switch 1 ตัว
- PC 5 เครื่อง

ทำเป็น Draw.io diagram ให้หน่อย
```

**ผลที่ควรได้**: Claude สร้าง diagram ออกมา มีทั้ง Mermaid หรือ Draw.io XML

---

### Test 1.3 — แก้ไข Diagram

```
จาก diagram ที่เพิ่งสร้าง ช่วยเพิ่ม:
- WiFi AP 2 ตัว ต่อจาก Switch
- UPS 1 ตัว ปกป้อง Firewall กับ Switch

อัพเดต diagram ให้ด้วย
```

**ผลที่ควรได้**: Claude แก้ diagram เพิ่ม AP และ UPS เข้าไปได้

---

## 🟡 Level 2 — ทดสอบ GitHub Connector

ทดสอบว่าต่อ GitHub ได้และดึง template ได้

---

### Test 2.1 — เช็ค GitHub Connection

```
ช่วยดู repo นี้ให้หน่อยครับ
github.com/nutbadbot/diagram-templates

มีไฟล์อะไรอยู่ใน templates/network-infrastructure/ บ้าง?
```

**ผลที่ควรได้**: Claude แสดงรายการไฟล์ใน folder ได้

❌ ถ้า Claude บอกว่า "เข้าไม่ได้" หรือ "ช่วย copy มาให้" → **ยังไม่ได้ต่อ GitHub connector** กลับไปทำ MANUAL.md Section 4 ก่อน

---

### Test 2.2 — ดึง Template มาใช้

```
ช่วยไปอ่าน template smb-single-site.md
จาก repo github.com/nutbadbot/diagram-templates

แล้วสรุปให้ฟังว่า template นี้ใช้กับงานแบบไหน
และมี prompt ตัวอย่างอะไรบ้าง
```

**ผลที่ควรได้**: Claude อ่าน template แล้วสรุปเนื้อหาได้ถูกต้อง

---

### Test 2.3 — ให้ Claude หา Template เอง

```
ผมมีลูกค้าที่ต้องการ network สำหรับ:
- บริษัทเล็กๆ 30 คน
- Office เดียว ไม่มีสาขา
- มี internet + wifi + NAS

ช่วยหา template ที่เหมาะสมที่สุด
จาก github.com/nutbadbot/diagram-templates
แล้วบอกว่าทำไมถึงเลือกตัวนั้น
```

**ผลที่ควรได้**: Claude เลือก `smb-single-site.md` และอธิบายเหตุผล

---

## 🔴 Level 3 — ทดสอบงานจริง

ทดสอบ use case ที่ใกล้เคียงงานของ Pragma

---

### Test 3.1 — สร้าง Diagram จาก Spec จริง

```
ช่วยหา template ที่เหมาะสมจาก
github.com/nutbadbot/diagram-templates

แล้วสร้าง network diagram สำหรับลูกค้า:

อุปกรณ์:
- Firewall: FortiGate 60F x1
- Core Switch: Cisco SG350-28P x1 (24 port PoE+)
- AP: Ruckus R350 x4 (PoE+ จาก Core)
- UPS: APC 1500VA x1

Topology:
- Internet 300 Mbps → FortiGate → Core Switch → AP
- UPS ปกป้อง FortiGate + Core Switch
- Users: 40 คน

ใช้ Pragma Style (dark theme, layered)
```

**ผลที่ควรได้**: Claude สร้าง diagram ออกมาแบบ Pragma Style ครบถ้วน

---

### Test 3.2 — Multi-site SD-WAN

```
ช่วยหา template SD-WAN จาก
github.com/nutbadbot/diagram-templates

ปรับสำหรับลูกค้า:
- HQ: กรุงเทพ 100 users, FortiGate 100F, Internet AIS 1Gbps
- Branch: เชียงใหม่ 30 users, FortiGate 60F, Internet True 300Mbps
- Backup: 4G LTE ทั้ง 2 site
- Tunnel: SD-WAN IPsec

แสดง Pragma Style
```

**ผลที่ควรได้**: Claude สร้าง SD-WAN diagram แบบ 2 sites ได้ถูกต้อง

---

### Test 3.3 — บันทึกเข้า Google Drive

```
[ทำหลังจาก Test 3.1 หรือ 3.2]

บันทึก diagram ที่เพิ่งสร้างเข้า Google Drive
ตั้งชื่อว่า: Test-Diagram_Pragma_[ชื่อคุณ]_[วันที่วันนี้].drawio
```

**ผลที่ควรได้**: Claude บันทึกไฟล์เข้า Google Drive สำเร็จ และบอก file ID

❌ ถ้า Claude บันทึกไม่ได้ → เช็ค Google Drive connector ใน Settings

---

### Test 3.4 — Bonus: ถามคำแนะนำ

```
ช่วยดู diagram ที่เพิ่งสร้างแล้ว review ให้หน่อย:
- มีอะไรที่ขาดไปไหม?
- Best practice ของ Fortinet แนะนำอะไรเพิ่ม?
- ถ้าลูกค้าต้องการ HA ในอนาคต ควรเพิ่มอะไร?
```

**ผลที่ควรได้**: Claude ให้คำแนะนำที่เป็นประโยชน์เกี่ยวกับ network design

---

## 📊 สรุปผลการทดสอบ

| Test | ผ่าน | ไม่ผ่าน | หมายเหตุ |
|---|---|---|---|
| 1.1 ถามตรงๆ | ☐ | ☐ | |
| 1.2 สร้าง diagram เบื้องต้น | ☐ | ☐ | |
| 1.3 แก้ไข diagram | ☐ | ☐ | |
| 2.1 เช็ค GitHub connection | ☐ | ☐ | |
| 2.2 ดึง template | ☐ | ☐ | |
| 2.3 ให้ Claude หา template เอง | ☐ | ☐ | |
| 3.1 สร้าง diagram จาก spec จริง | ☐ | ☐ | |
| 3.2 SD-WAN multi-site | ☐ | ☐ | |
| 3.3 บันทึกเข้า Google Drive | ☐ | ☐ | |
| 3.4 Bonus review | ☐ | ☐ | |

### เกณฑ์การผ่าน
- **Level 1 ผ่านหมด** = ใช้ Claude พื้นฐานได้ ✅
- **Level 1-2 ผ่านหมด** = ใช้กับ template repo ได้ ✅
- **Level 1-3 ผ่านหมด** = พร้อมใช้งานจริงกับลูกค้า ✅

---

## 🆘 ปัญหาที่พบบ่อย

| อาการ | สาเหตุ | วิธีแก้ |
|---|---|---|
| Claude บอก "copy มาให้หน่อย" | ยังไม่ต่อ GitHub connector | ทำ MANUAL.md Section 4 |
| บันทึก Google Drive ไม่ได้ | Token หมดอายุ | Settings → Connectors → Google Drive → Reconnect |
| Diagram เปิดใน Draw.io ไม่ได้ | XML มีปัญหา | บอก Claude ว่า "ช่วย fix XML ให้" |
| Claude ตอบเป็นภาษาอังกฤษ | ไม่ได้บอกภาษา | เพิ่ม "ตอบภาษาไทย" ใน prompt |

---

## 💬 Feedback

หลังทดสอบเสร็จแล้ว ช่วยแจ้ง Nuttawut ด้วยนะครับว่า:
- ผ่าน Level ไหน
- ติดปัญหาตรงไหน
- อยากเพิ่ม test case อะไร

จะได้ปรับปรุง workflow ให้ดีขึ้นครับ 🙏
