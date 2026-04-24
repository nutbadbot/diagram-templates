# 📋 Team Workflow Automation Ideas

> รวบรวมงาน repetitive ของทีม Pragma ที่ Claude ช่วยได้ — เก็บไว้คุยกันในทีม

---

## 🎯 วัตถุประสงค์

เอกสารนี้ใช้เป็น **starter kit** สำหรับทีมไปคุยกันว่า:
- งานไหนทำซ้ำๆ ทุกวัน/สัปดาห์/เดือน
- Claude ช่วยลดเวลาได้แค่ไหน
- ควรลงทุนทำ template อะไรเพิ่ม

---

## 💡 ไอเดียเริ่มต้น (แยกตามประเภทงาน)

### 1️⃣ งาน Pre-Sales / Proposal

| งานที่ทำซ้ำ | Pain point | Claude ช่วยได้ | Priority |
|---|---|---|---|
| วาด architecture ตอบ RFP | ใช้เวลา 2-4 ชม./ครั้ง | สร้างจาก template + spec ให้ใน 10 นาที | 🔥 High |
| ปรับ diagram ตาม feedback ลูกค้า | แก้ไปแก้มา เสียเวลา | ส่ง diff + feedback ให้ Claude | 🔥 High |
| เปลี่ยน logo/branding ในหลาย slides | งาน manual ที่น่าเบื่อ | Batch update | 🟡 Medium |
| เขียน technical proposal (เนื้อหาซ้ำ 60-70%) | Copy-paste จาก proposal เดิม | ใช้ template + Claude customize | 🔥 High |

### 2️⃣ งาน Implementation / Deployment

| งานที่ทำซ้ำ | Pain point | Claude ช่วยได้ | Priority |
|---|---|---|---|
| ทำ As-Built document หลัง implement | ต้องเขียนเอกสารใหม่ทุกโปรเจกต์ | สร้าง draft จาก design doc + config | 🔥 High |
| แปลง Visio → Draw.io (หรือกลับกัน) | Format ไม่ตรงกับที่ลูกค้าต้องการ | Convert + preserve styling | 🟡 Medium |
| Update IP addressing ใน diagram | Client เปลี่ยน IP plan บ่อย | Find & replace + validate | 🟡 Medium |
| สร้าง rack diagram จาก BOM | ใช้ Excel list → วาด | Claude อ่าน BOM แล้วสร้าง rack | 🟢 Low |

### 3️⃣ งาน Operations / Support

| งานที่ทำซ้ำ | Pain point | Claude ช่วยได้ | Priority |
|---|---|---|---|
| เขียน incident report | Format ซ้ำๆ | Template + fill-in details | 🟡 Medium |
| วาด troubleshooting flow | อธิบายให้ junior เข้าใจ | สร้าง flowchart จากคำอธิบาย | 🟢 Low |
| Update network topology หลัง MAC | เปลี่ยนเล็กน้อย แต่ต้อง update diagram | Incremental update | 🔥 High |
| สรุป root cause analysis | เขียนยาวทุกครั้ง | Structure + ภาษาให้อ่านง่าย | 🟡 Medium |

### 4️⃣ งาน Internal / Knowledge Management

| งานที่ทำซ้ำ | Pain point | Claude ช่วยได้ | Priority |
|---|---|---|---|
| ทำ knowledge base จาก case จริง | ไม่มีเวลาเขียน | Claude สกัด knowledge จาก ticket/email | 🟡 Medium |
| เขียน runbook | ซ้ำกับของลูกค้าราย A แต่ต้องปรับ | ใช้ template + customize | 🟡 Medium |
| สร้าง training material สำหรับ junior | Copy-paste จากหลายที่ | Claude compile ให้ | 🟢 Low |

---

## 🧪 Experiment ที่ทีมควรลอง (Week 1-2)

### Experiment 1: Visio ลูกค้าเก่า → Claude
1. เลือก Visio ของลูกค้าเก่าที่ deploy เสร็จแล้ว
2. ให้ Claude ลอง:
   - แปลงเป็น Draw.io
   - สรุป architecture
   - เสนอ improvements
3. วัดผล: Claude แม่นแค่ไหน? ต้องแก้มากมั้ย?

### Experiment 2: PDF proposal → Editable diagram
1. เอา proposal PDF เก่า
2. ให้ Claude:
   - Extract diagram ออกมา
   - ทำเป็น editable version
3. วัดผล: เทียบกับ redraw เองใช้เวลาต่างกันแค่ไหน

### Experiment 3: As-Built from template
1. เอาโปรเจกต์ที่เพิ่งจบ
2. ให้ Claude:
   - ใช้ template + final config
   - สร้าง As-Built document
3. วัดผล: เทียบกับการเขียนเองใช้เวลาต่างกันแค่ไหน

---

## 📊 Template สำหรับทีมกรอก

ทีมสามารถ copy ตารางนี้แล้วเพิ่ม idea ได้:

```markdown
### [ประเภทงาน]

| งานที่ทำซ้ำ | ความถี่ | Pain point | Claude ช่วยได้ | ประโยชน์ |
|---|---|---|---|---|
| [งาน] | [รายวัน/สัปดาห์/เดือน] | [pain] | [solution] | [save time/money] |
```

---

## 🚀 Next Step

1. **Week 1**: ทีมทุกคนกรอกตารางข้างบน (ใส่งานที่ตัวเองทำซ้ำๆ)
2. **Week 2**: Vote ว่า top 3 ไอเดียไหนที่ควรทำ template ก่อน
3. **Week 3**: Build templates + ทดลองใช้จริง
4. **Week 4**: Review — อะไร work, อะไรไม่ work, ต่อยังไง

---

## 💬 Discussion Questions (สำหรับ team meeting)

1. งานไหนที่ทำเหนื่อยที่สุดแต่ไม่ได้ใช้ความคิดสร้างสรรค์?
2. งานไหนที่ทำผิดบ่อยเพราะต้องทำซ้ำเยอะ?
3. ถ้า Claude ทำได้ 80% แล้วเราแค่ review — พอใจมั้ย?
4. มี concern เรื่อง data security ของลูกค้ามั้ย?
5. ใครอยากเป็น "Claude champion" ของทีม (คนที่เก่งที่สุด แล้วสอนคนอื่น)?

---

**หมายเหตุ**: เอกสารนี้เป็น living document — อัพเดตได้ทุกครั้งที่เจอไอเดียใหม่
