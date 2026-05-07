# 🤝 วิธีเพิ่ม Template ใหม่

> สำหรับทีม Pragma ที่อยากแชร์ diagram ดีๆ เข้ามาในคลัง

---

## 📝 ขั้นตอน

### 1. เลือกหมวด

Template ของคุณเข้าข่ายหมวดไหน?

| หมวด | ตัวอย่าง |
|---|---|
| `network-infrastructure/` | network topology, rack, firewall zone, SD-WAN, Hyper-V, backup, VLAN |
| `system-architecture/` | microservices, 3-tier app, cloud (AWS/Azure) |
| `process-flow/` | business workflow, approval, CI/CD pipeline |

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
- [ ] **ใช้ Pragma Dark Style** — background `#1a1a2e`, layer swimlanes, Cisco icons
- [ ] Draw.io XML ทดสอบเปิดใน Draw.io แล้วแสดงผลถูกต้อง
- [ ] มี Mermaid version (quick reference)
- [ ] มี prompt ตัวอย่างอย่างน้อย 1 แบบ
- [ ] มีตาราง Parameters ที่ปรับได้
- [ ] มี Related Templates ใน Notes
- [ ] **ไม่มีข้อมูลลูกค้า/ข้อมูลลับ** (IP จริง, ชื่อบริษัทลูกค้า, credentials)

---

## ⚠️ ข้อห้าม

- ❌ ไม่ใส่ข้อมูลลูกค้าจริง (ชื่อ, IP จริง, credentials)
- ❌ ไม่ใส่ไฟล์ binary ขนาดใหญ่ (>5MB) — ใช้ external link
- ❌ ไม่ copy template จากที่อื่นโดยไม่มี attribution
- ❌ ไม่ใช้ light theme (white background) — ทุก template ต้องเป็น Pragma Dark Style

---

## 🏆 Template ที่ดีควรมี

1. **Generalization**: ปรับใช้ได้กับหลาย use case
2. **Documentation**: มีคำอธิบายครบ ไม่ต้องถามทีมเพิ่ม
3. **Pragma Style**: dark theme สม่ำเสมอทุก template
4. **Best practices**: สะท้อน standard ของทีม Pragma
5. **Tested**: ลองใช้จริงกับ Claude แล้วได้ผลดี
