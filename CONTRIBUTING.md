# 🤝 วิธีเพิ่ม Template ใหม่

> สำหรับทีม Pragma ที่อยากแชร์ diagram ดีๆ เข้ามาในคลัง

---

## 📝 ขั้นตอน

### 1. เลือกหมวด

Template ของคุณเข้าข่ายหมวดไหน?

| หมวด (folder) | ใช้สำหรับ |
|---|---|
| `templates/pre-sales/` | SMB, 3-tier data center, SD-WAN, cloud architecture (AWS/Azure/GCP), microservices, serverless |
| `templates/design/` | VLAN, firewall/DMZ, WiFi, rack elevation, Hyper-V, backup, AD DS, iSCSI, Spine-Leaf, OT/Purdue |
| `templates/handover/` | approval workflow, CI/CD pipeline, incident response |

ถ้าไม่เข้าหมวดไหนเลย เปิด Issue ถามก่อนครับ

### 2. ตั้งชื่อไฟล์

Format: `[ชื่อสั้นๆ-อธิบาย].md`

✅ ดี:
- `3-tier-data-center.md`
- `hyper-v-failover-cluster.md`
- `backup-architecture.md`

❌ ไม่ดี:
- `template1.md`
- `my_diagram.md`
- `สำหรับลูกค้าเอบีซี.md` (ไม่ควรมีชื่อลูกค้า)

### 3. โครงสร้างไฟล์ Template

ทุก template ต้องมี:

````markdown
# ชื่อ Template

> คำอธิบายสั้นๆ 1 บรรทัด

## 📋 ใช้ตอนไหน
- ใช้กับลูกค้าที่...
- เหมาะสำหรับ...
- **ไม่เหมาะกับ**: ...

## 🎨 Pragma Style Diagram (Draw.io XML)

```xml
<mxfile host="app.diagrams.net" version="24.0.0">
  <diagram name="...">
    <mxGraphModel background="#1a1a2e">
      <!-- XML ที่นี่ — ต้องใช้ Pragma Dark Style -->
    </mxGraphModel>
  </diagram>
</mxfile>
```

## 🌊 Mermaid Template

```mermaid
flowchart TB
  A --> B
```

## 💡 Prompt ตัวอย่าง

```
ใช้ template [ชื่อ].md แบบ Pragma Style
ปรับสำหรับ [ลูกค้า]:
- [spec 1]
- [spec 2]
```

## 🔧 Parameters ที่ปรับได้

| Parameter | Default | ทางเลือก |
|---|---|---|
| ... | ... | ... |

## 📌 Notes

- ข้อควรระวัง
- Related templates
````

### 4. Submit ผ่าน Git

```bash
# Clone repo
git clone https://github.com/nutbadbot/diagram-templates.git
cd diagram-templates

# สร้าง branch ใหม่
git checkout -b add-template-xxx

# เพิ่มไฟล์
# ... (สร้างไฟล์ของคุณใน templates/xxx/)

# Commit
git add .
git commit -m "Add template: [ชื่อ template]"

# Push
git push origin add-template-xxx

# เปิด Pull Request บน GitHub
```

### 5. ถ้าไม่ถนัด Git

เปิด [Issue](https://github.com/nutbadbot/diagram-templates/issues) แล้วแนบไฟล์มาได้เลย — ทีม maintain จะช่วย merge ให้

---

## ✅ Checklist ก่อน Submit

- [ ] ไฟล์อยู่ในหมวดที่ถูกต้อง
- [ ] ชื่อไฟล์ตาม format (kebab-case, ภาษาอังกฤษ)
- [ ] มีส่วน "ใช้ตอนไหน" พร้อม ✅ และ ❌
- [ ] **ใช้ Pragma Dark Style** — background `#1a1a2e`, layer swimlanes
- [ ] Draw.io XML ทดสอบเปิดใน Draw.io แล้วแสดงผลถูกต้อง
- [ ] มี Mermaid version (quick reference)
- [ ] มี prompt ตัวอย่างอย่างน้อย 1 แบบ
- [ ] มีตาราง Parameters ที่ปรับได้ — **ระบุทางเลือก vendor หลายๆ ตัว ไม่ lock เฉพาะยี่ห้อเดียว**
- [ ] มี Related Templates ใน Notes
- [ ] **ไม่มีข้อมูลลูกค้า/ข้อมูลลับ** (IP จริง, ชื่อบริษัทลูกค้า, credentials)

---

## 🎨 Pragma Dark Style — ข้อกำหนด

ทุก template ใช้ **Pragma Dark Style** มาตรฐาน:

| Layer | Fill Color | Stroke Color | ใช้สำหรับ |
|---|---|---|---|
| Internet / WAN | `#1a2a4a` | `#4a90d9` | Cloud, ISP, external endpoint |
| Security | `#2d1a0e` | `#ff9800` | Firewall, WAF, SBC, Gateway |
| Core / Compute | `#0d2b1a` | `#2e7d32` | Core switch, Server, K8s, Function |
| Access / Edge | `#1a1030` | `#7c4dff` | Voice VLAN, Access switch, Queue |
| Data | `#0d1f2b` | `#0288d1` | Database, Storage, Cache |
| Reject / Error | `#3a1010` | `#e53935` | Reject node, Error state, Block |
| Endpoint | `#1a1a1a` | `#424242` | PC, Phone, End device |

**Node shapes:**
- Process / Service → `rounded=1` rectangle
- Decision → `rhombus`
- Database → `shape=cylinder3`
- Start / End → `ellipse`
- Icon (network device) → ใช้ shape library ที่เหมาะสมกับ vendor จริงของลูกค้า หรือ generic icon ถ้าไม่ fix vendor

**ข้อสำคัญ — Vendor Agnostic:**
> Template ต้องออกแบบให้ปรับ vendor ได้ง่าย อย่า hardcode ชื่ออุปกรณ์ลงใน label หลัก ให้ใส่ในตาราง Parameters แทน ตัวอย่างเช่น label ว่า "Core Switch" แทน "Cisco Nexus 9500" และระบุ vendor ใน Parameters table ว่า default คืออะไร ทางเลือกคืออะไรบ้าง

---

## ⚠️ ข้อห้าม

- ❌ ไม่ใส่ข้อมูลลูกค้าจริง (ชื่อ, IP จริง, credentials)
- ❌ ไม่ใส่ไฟล์ binary ขนาดใหญ่ (>5MB) — ใช้ external link
- ❌ ไม่ copy template จากที่อื่นโดยไม่มี attribution
- ❌ ไม่ใช้ light theme (white background) — ทุก template ต้องเป็น Pragma Dark Style
- ❌ ไม่ lock vendor ลงใน template หลัก — ให้ระบุใน Parameters แทน

---

## 🏆 Template ที่ดีควรมี

1. **Generalization**: ปรับใช้ได้กับหลาย use case และหลาย vendor
2. **Documentation**: มีคำอธิบายครบ ไม่ต้องถามทีมเพิ่ม
3. **Pragma Style**: dark theme สม่ำเสมอทุก template
4. **Best practices**: สะท้อน standard ของทีม Pragma
5. **Tested**: ลองใช้จริงกับ Claude แล้วได้ผลดี
