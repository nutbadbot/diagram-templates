# 🎬 Setup Claude สำหรับทีม Pragma

> คู่มือการ setup Claude + connectors แบบละเอียด

---

## 🎯 เป้าหมาย

หลังทำตามคู่มือนี้จบ คุณจะมี:
- ✅ บัญชี Claude พร้อมใช้
- ✅ เชื่อม Google Drive แล้ว (ถ้าต้องใช้)
- ✅ เชื่อม OneDrive/SharePoint แล้ว
- ✅ เชื่อม Draw.io แล้ว
- ✅ ทดสอบใช้งานได้

**เวลาที่ใช้**: 10-15 นาที

---

## Step 1: สร้างบัญชี Claude

### 1.1 ไปที่ [claude.ai](https://claude.ai)

### 1.2 Sign up

ใช้ email ที่ทำงานจะดีที่สุด เพราะ:
- เอา claim ค่า subscription จากบริษัทได้ง่าย
- ถ้าออกจากบริษัทจะลบได้ชัดเจน

### 1.3 Upgrade เป็น Pro

1. คลิก profile มุมซ้ายล่าง
2. Settings → Plans & Billing
3. เลือก **Pro** ($20/เดือน)
4. ใส่ข้อมูลการชำระเงิน

💡 **Tips**: ใช้บัตร credit บริษัท หรือเก็บ invoice ไว้ claim

---

## Step 2: เปิดใช้งาน Connectors

### 2.1 หา Connectors

1. ในหน้าแชท คลิกไอคอนเฟือง ⚙️ (Settings)
2. ไปที่ **Connectors** (บางครั้งชื่อ "Integrations")

### 2.2 Google Drive (ถ้าใช้)

**ต้องมี**: Google account ที่มีไฟล์ diagram

**ขั้นตอน**:
1. คลิก **Connect** ข้าง Google Drive
2. Browser จะเปิด Google login popup
3. เลือก account
4. Review permissions → Allow
5. กลับมาที่ Claude → จะเห็น ✅ ติดแล้ว

**ทดสอบ**: ถามว่า
```
ช่วยลิสต์ 5 ไฟล์ล่าสุดใน Google Drive ของฉันหน่อย
```

### 2.3 OneDrive / SharePoint ⭐

**ต้องมี**: Microsoft 365 account บริษัท

**ขั้นตอน**:
1. คลิก **Connect** ข้าง OneDrive (หรือ SharePoint)
2. Microsoft login popup
3. ใส่ email + password บริษัท
4. ถ้ามี MFA ให้ยืนยัน
5. Review permissions → Accept

**ทดสอบ**: ถามว่า
```
ช่วยไปหาไฟล์ .vsdx ล่าสุดใน OneDrive ของฉันหน่อย
```

⚠️ **ถ้าองค์กรบล็อก**: บาง org ตั้งค่าไม่ให้ third-party apps เข้าถึง SharePoint — ต้องคุยกับ IT Admin

### 2.4 Draw.io

**ขั้นตอน**:
1. คลิก **Connect** ข้าง Draw.io
2. ไม่ต้อง login (authless) — เชื่อมได้เลย

**ทดสอบ**: ถามว่า
```
ช่วยวาด flowchart ง่ายๆ: Start → Process → End
```

Claude ควรแสดง diagram inline พร้อมปุ่ม "Open in draw.io"

---

## Step 3: สร้าง Project สำหรับงาน Diagram

Projects ช่วยเก็บ context ที่ใช้ซ้ำๆ

### 3.1 สร้าง Project

1. หน้าแรก Claude → **Projects** (sidebar ซ้าย)
2. **+ New Project**
3. ตั้งชื่อ: เช่น "Pragma Diagrams"

### 3.2 ใส่ Context

ใส่ข้อมูลที่อยากให้ Claude รู้ทุกครั้ง:

**ตัวอย่าง Custom Instructions**:
```
ฉันทำงานที่ Pragma (บริษัท SI)
งาน diagram หลัก: Network/Infrastructure, System Architecture, Process Flow
Template อ้างอิง: https://github.com/nutbadbot/diagram-templates

เวลาสร้าง diagram:
- ใช้ Cisco icons สำหรับ network
- ใช้ AWS/Azure icons สำหรับ cloud
- Label เป็นภาษาอังกฤษเป็นหลัก
- Export ให้อยู่ในรูป Draw.io XML เสมอ
```

### 3.3 Upload Templates

เข้า Project → **Add content** → Upload ไฟล์ template ที่ใช้บ่อย

Claude จะอ้างอิงได้ทุก chat ใน project นั้น

---

## Step 4: ทดสอบ End-to-End

ลองทดสอบ workflow เต็มๆ 1 รอบ:

### Test Case 1: สร้างจากศูนย์

```
ช่วยวาด network diagram สำหรับบริษัท SMB:
- 1 site
- Internet → Firewall → Core Switch → 4 Access Switches
- Server room (2 servers, 1 NAS)
- WiFi AP 3 ตัว
ใช้ Cisco icons, ภาษาอังกฤษ
```

**ควรได้**:
- Diagram แสดงในแชท
- ปุ่ม "Open in draw.io"
- คลิกแล้วเปิด Draw.io ได้ + แก้ไขต่อได้

### Test Case 2: ดึงจาก OneDrive

```
ช่วยหาไฟล์ชื่อ "network" ใน OneDrive ของฉัน
แล้วสรุปว่า diagram นั้นมีอะไรบ้าง
```

### Test Case 3: ใช้ template จาก repo

```
ไปที่ https://github.com/nutbadbot/diagram-templates
เปิดไฟล์ templates/network-infrastructure/3-tier-basic.md
แล้วปรับให้เป็น network ของบริษัท ABC ที่มี 3 สาขา
```

---

## 🆘 Troubleshooting

### ❌ Connector ไม่เชื่อมต่อ

- Clear cache/cookies แล้วลองใหม่
- ลอง incognito mode
- เช็คว่า organization admin อนุญาตให้เชื่อมหรือไม่

### ❌ Draw.io แสดงไม่ได้

- ต้องใช้ Claude Pro ขึ้นไป
- Browser ต้อง enable JavaScript
- ลอง Chrome/Edge/Safari เวอร์ชันล่าสุด

### ❌ Claude ไม่เห็นไฟล์ใน Drive/OneDrive

- Refresh connector: Disconnect → Connect ใหม่
- ตรวจ permissions ตอน OAuth ว่า allow ครบ
- ไฟล์อยู่ใน account เดียวกับที่ connect หรือเปล่า

---

## 📚 Next Steps

Setup เสร็จแล้ว → อ่านต่อ:
- [prompt-library.md](prompt-library.md) — prompt ตัวอย่าง
- [setup-github-mcp.md](setup-github-mcp.md) — (Advanced) เชื่อม GitHub
