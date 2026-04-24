# 💬 Prompt Library สำหรับทีม Pragma

> รวม prompt ที่ทดสอบแล้วว่าใช้งานได้ผลดีกับ Claude

---

## 🎯 หลักการเขียน Prompt ที่ดี

### สูตร 4W+H

1. **What** — ต้องการ diagram อะไร
2. **Who** — ใช้กับใคร (internal/client/SMB/enterprise)
3. **Where** — deploy ที่ไหน (on-prem/cloud/hybrid)
4. **Which** — ใช้ icon/technology ของใคร (Cisco/Fortinet/AWS)
5. **How** — format, language, detail level

### ตัวอย่างเปรียบเทียบ

❌ **prompt ไม่ดี**:
```
วาด network ให้หน่อย
```

✅ **prompt ที่ดี**:
```
วาด network diagram สำหรับ SMB ที่มี 50 คน (What + Who)
Deploy on-premise ที่สำนักงานเดียว (Where)
อุปกรณ์ Cisco + FortiGate firewall (Which)
Draw.io XML format, label อังกฤษ, ใช้ Cisco icons (How)
```

---

## 📚 Prompts แยกตามงาน

### 🌐 Network & Infrastructure

#### N1: สร้าง Network Topology พื้นฐาน

```
ช่วยวาด network topology สำหรับ [ขนาดบริษัท] ที่มี:
- [จำนวน] sites/branches
- Internet connection: [รายละเอียด]
- Firewall: [ยี่ห้อ/รุ่น]
- Core switches: [จำนวน, redundant หรือไม่]
- Access switches: [จำนวน, ต่อ floor/zone]
- Servers: [จำนวน, ประเภท]
- Wireless: [จำนวน AP, SSID อะไรบ้าง]

ใช้ icons ของ [Cisco/Fortinet/Aruba/etc.]
Export เป็น Draw.io XML
Label ภาษา[ไทย/อังกฤษ]
```

#### N2: Multi-site Network

```
วาด WAN diagram สำหรับบริษัทที่มี:
- HQ ที่กรุงเทพ
- Branches: [list ของสาขา]
- เชื่อมด้วย [MPLS/SD-WAN/VPN]
- Internet breakout ที่ [HQ/ทุกสาขา]
- Redundancy: [primary/secondary links]

แสดง link bandwidth + SLA
```

#### N3: Rack Diagram

```
สร้าง rack diagram 42U สำหรับ:
- [จำนวน] servers ขนาด 2U
- [จำนวน] switches 1U
- 1 firewall 1U
- 1 KVM + 1 monitor
- 2 PDU (vertical)
- 1 cable manager ทุก 4U

แสดง front view + back view
```

---

### 🏛️ System Architecture

#### A1: 3-Tier Application

```
วาด application architecture แบบ 3-tier สำหรับ [ชื่อระบบ]:
- Presentation: [web/mobile], tech stack: [React/Angular]
- Application: [Node.js/Java Spring/Python]
- Database: [MySQL/PostgreSQL/MongoDB]

แสดง:
- Load balancer หน้า presentation
- API Gateway ระหว่าง presentation กับ app
- Cache layer (Redis)
- DB replication (primary-replica)

Style: boxes + arrows, minimal color
```

#### A2: Microservices

```
วาด microservices architecture สำหรับ [ชื่อระบบ]:
- Services: [list ของ services]
- แต่ละ service มี own database
- Communication: [REST/gRPC/message queue]
- API Gateway: [Kong/nginx/AWS API GW]
- Service discovery: [Consul/Eureka]
- Monitoring: [Prometheus + Grafana]

แสดง data flow ด้วยลูกศรมีเลขลำดับ
```

#### A3: Cloud Architecture (AWS)

```
วาด AWS architecture สำหรับ [ระบบ]:
- Region: [ap-southeast-1]
- VPC: 2 AZs (HA)
- Public subnet: ALB, NAT Gateway, Bastion
- Private subnet: EC2 (ASG), RDS (Multi-AZ)
- S3 + CloudFront สำหรับ static content
- Route 53 DNS
- CloudWatch + CloudTrail

ใช้ AWS official icons
แสดง security group flows
```

---

### 🔄 Process & Workflow

#### P1: Business Process Flow

```
สร้าง process flow สำหรับ [ชื่อ process] เช่น "อนุมัติจัดซื้อ":

Actors:
- [Requester]
- [Manager]
- [Finance]
- [System]

Steps:
1. Requester กรอกฟอร์ม
2. System ตรวจสอบ
3. Manager อนุมัติ/ปฏิเสธ
...

ใช้ swimlane diagram (แต่ละ actor 1 lane)
Decision point ใช้ diamond
แสดง condition ที่ edge
```

#### P2: CI/CD Pipeline

```
วาด CI/CD pipeline สำหรับ [project]:
- Source: GitHub
- Trigger: push to main branch
- Stages:
  1. Lint + Unit tests
  2. Build Docker image
  3. Push to registry
  4. Deploy to staging
  5. Integration tests
  6. Manual approval
  7. Deploy to production
- Tools: [Jenkins/GitLab CI/GitHub Actions]

แสดง parallel steps + artifacts
```

---

## 🛠️ Prompts ช่วยแก้งานเดิม

### ✏️ E1: แปลง Visio → Draw.io

```
[upload ไฟล์ .vsdx]

ช่วยแปลง Visio นี้เป็น Draw.io XML
รักษา:
- Layout เดิม
- Icons เดิม (ถ้ามี Cisco/AWS ให้ใช้ของ Draw.io แทน)
- Label เดิม
- Connections เดิม
```

### ✏️ E2: อัพเดต diagram เดิม

```
[upload ไฟล์เดิม]

ช่วยแก้ diagram นี้:
- [การเปลี่ยนแปลงที่ 1]
- [การเปลี่ยนแปลงที่ 2]
- [การเปลี่ยนแปลงที่ 3]

ส่วนอื่นๆ ให้คงเดิม
Highlight ส่วนที่เปลี่ยนด้วยกรอบสีส้ม
```

### ✏️ E3: เขียน documentation จาก diagram

```
[upload หรือ paste diagram]

ช่วยเขียน architecture documentation จาก diagram นี้:

Sections:
1. Overview (2-3 paragraphs)
2. Component descriptions (list แต่ละส่วน + หน้าที่)
3. Data flow (step-by-step)
4. Integration points
5. Security considerations
6. Scalability & HA

ภาษา: [ไทย/อังกฤษ]
Format: Markdown
ความยาว: 2-3 หน้า A4
```

### ✏️ E4: วิเคราะห์ diagram

```
[upload diagram]

ช่วยวิเคราะห์ architecture นี้:
- จุดแข็ง
- จุดอ่อน / risks
- Single points of failure
- Scalability concerns
- Security gaps
- ข้อเสนอแนะในการปรับปรุง
```

---

## 🎨 Prompts สำหรับงานประจำ

### 📋 D1: สร้าง diagram template ใหม่

```
ช่วยสร้าง Draw.io template สำหรับ [ประเภท diagram]
ที่ทีมจะใช้ซ้ำๆ กับลูกค้าหลายๆ ราย

ต้องมี:
- Placeholder สำหรับ [fields ที่จะเปลี่ยน]
- Style guide (colors, fonts)
- Comments อธิบายแต่ละส่วน
- Instructions ตอนเอาไปใช้

Save เป็น .drawio ที่ reusable
```

### 📋 D2: Batch update หลาย diagrams

```
[upload หลายไฟล์]

ช่วย:
- เปลี่ยน logo/header ทุกไฟล์เป็น [new logo]
- Update year จาก 2024 → 2026
- เปลี่ยนชื่อบริษัทจาก X เป็น Y
- รักษา content อื่นๆ ไว้

Export เป็น zip
```

---

## 💎 Pro Tips

### 🔥 ใช้ตัวอย่างประกอบเสมอ

ดีกว่าอธิบายยาวๆ:

```
ช่วยทำ network diagram สไตล์เดียวกันกับไฟล์นี้:
[upload ตัวอย่าง]

แต่เปลี่ยนเนื้อหาเป็น: [รายละเอียดใหม่]
```

### 🔥 บอก scale ก่อน

ต่างกันเยอะระหว่าง:
- "simple overview" = 5-10 components
- "detailed technical" = 20-30 components
- "enterprise-grade" = 50+ components + zones

### 🔥 แบ่งเป็นหลาย diagram ถ้าใหญ่มาก

```
ระบบนี้ใหญ่มาก ขอให้แยกเป็น:
1. High-level architecture (1 diagram)
2. Network topology (1 diagram)
3. Data flow (1 diagram)
4. Security zones (1 diagram)
```

### 🔥 ขอ review ตัวเอง

```
[หลัง Claude สร้าง diagram]

ช่วย review diagram ที่เพิ่งสร้างเอง
- มีอะไรขาด?
- มี best practices อะไรที่น่าเพิ่ม?
- Cisco/AWS standard แนะนำอะไรเพิ่มเติม?
```

---

## 📝 Template Prompt แบบ fill-in-the-blank

Copy แล้วเติมช่องว่าง:

```
# Context
ฉันเป็น [role] ที่บริษัท Pragma
กำลังทำงานให้ลูกค้า [industry]

# Task
ช่วย [สร้าง/แก้ไข/วิเคราะห์] [diagram type]

# Requirements
- [requirement 1]
- [requirement 2]
- [requirement 3]

# Constraints
- ใช้ icon ของ [vendor]
- Label ภาษา [ไทย/อังกฤษ]
- ขนาด [simple/detailed/enterprise]
- Output: Draw.io XML

# References
[paste template หรือ link ถ้ามี]
```

---

**เพิ่ม prompt ใหม่**: Contribute ผ่าน Pull Request ที่ [repo นี้](https://github.com/nutbadbot/diagram-templates)
