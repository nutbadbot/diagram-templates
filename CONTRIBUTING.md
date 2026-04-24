# 🤝 วิธีเพิ่ม Template ใหม่

> สำหรับทีม Pragma ที่อยากแชร์ diagram ดีๆ เข้ามาในคลัง

---

## 📝 ขั้นตอน

### 1. เลือกหมวด

Template ของคุณเข้าข่ายหมวดไหน?

| หมวด | ตัวอย่าง |
|---|---|
| `network-infrastructure/` | network topology, rack, firewall zone, SD-WAN |
| `system-architecture/` | microservices, 3-tier app, cloud (AWS/Azure) |
| `process-flow/` | business workflow, approval, CI/CD pipeline |

ถ้าไม่เข้าหมวดไหนเลย เปิด Issue ถามก่อนครับ

### 2. ตั้งชื่อไฟล์

Format: `[ชื่อสั้นๆ-อธิบาย].md`

✅ ดี:
- `3-tier-data-center.md`
- `aws-microservices-basic.md`
- `firewall-dmz-standard.md`

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

## 🖼️ Preview
(แนบรูป preview ถ้าได้)

## 📝 Draw.io XML

```xml
<mxfile>
<!-- XML ที่นี่ -->
</mxfile>
```

## 🌊 Mermaid version (ถ้ามี)

```mermaid
graph TD
  A --> B
```

## 💡 Prompt ตัวอย่างสำหรับใช้กับ Claude

```
นี่คือ template [ชื่อ]:
[paste XML/Mermaid]

ช่วยปรับให้เป็น...
```

## 🔧 Parameters ที่ควรปรับ

| Parameter | Default | ความหมาย |
|---|---|---|
| ... | ... | ... |

## 📌 Notes

- ข้อควรระวัง
- เคสพิเศษ
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
- [ ] ชื่อไฟล์ตาม format
- [ ] มี "ใช้ตอนไหน" ครบถ้วน
- [ ] มี Draw.io XML (อย่างน้อย 1 format)
- [ ] มี prompt ตัวอย่าง
- [ ] **ไม่มีข้อมูลลูกค้า/ข้อมูลลับ** (IP จริง, ชื่อบริษัทลูกค้า, credentials)
- [ ] ทดสอบแล้วเปิดใน Draw.io ได้

---

## ⚠️ ข้อห้าม

- ❌ ไม่ใส่ข้อมูลลูกค้าจริง (ชื่อ, IP, credentials)
- ❌ ไม่ใส่ไฟล์ binary ขนาดใหญ่ (>5MB) — ใช้ external link
- ❌ ไม่ copy template จากที่อื่นโดยไม่มี attribution

---

## 🏆 Template ที่ดีควรมี

1. **Generalization**: ปรับใช้ได้กับหลาย use case
2. **Documentation**: มีคำอธิบายครบ ไม่ต้องถามทีมเพิ่ม
3. **Best practices**: สะท้อน standard ของทีม Pragma
4. **Tested**: ลองใช้จริงกับ Claude แล้วได้ผลดี
