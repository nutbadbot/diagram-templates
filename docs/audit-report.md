# Audit Report — Diagram Templates

> ตรวจสอบความครบถ้วนของ template 23 ไฟล์ตามมาตรฐาน repo

**วันที่ audit**: 2026-06-27 (อัปเดต 2026-06-27 เพิ่ม 5 templates ใหม่)  
**ผู้ตรวจ**: Claude (Cowork mode)  
**ไฟล์ที่ตรวจ**: templates/pre-sales/ (7), templates/design/ (13), templates/handover/ (3)

---

## สรุปผล

| หัวข้อ | สถานะ |
|---|---|
| Template ทั้งหมด | 23 ไฟล์ |
| ผ่านครบทุก section | **12 ไฟล์** |
| มี section ขาด | **11 ไฟล์** |
| Section ที่ขาดบ่อยที่สุด | อัพเดตล่าสุด (11 ไฟล์) |

---

## ตารางผลตรวจสอบ (รายไฟล์)

**คำอธิบาย**: ✅ = มีครบ / ❌ = ขาด / ⚠️ = มีแต่ไม่ครบ

| ไฟล์ | ใช้ตอนไหน (✅❌) | XML Dark | Mermaid | ตารางข้อมูล | Prompt ≥2 แบบ | Parameters | Notes SI | Related | อัพเดตล่าสุด |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **pre-sales/** | | | | | | | | | |
| smb-single-site.md | ✅ | ✅ | ✅ | ✅ | ⚠️ (1 แบบ)* | ✅ | ✅ | ✅ | ❌ |
| 3-tier-data-center.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| sd-wan-multi-site.md | ✅ | ✅ | ✅ | ✅ | ❌ (1 แบบ) | ✅ | ✅ | ✅ | ❌ |
| 3-tier-web-app.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| microservices-aws.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| azure-landing-zone.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| serverless-aws.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| **design/** | | | | | | | | | |
| hyper-v-failover-cluster.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| vlan-segmentation.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| firewall-dmz-zones.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| enterprise-wifi-deployment.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| spine-leaf-fabric.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| voip-deployment.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| backup-architecture.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| rack-elevation-42u.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| vsan-cluster.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| ad-ds-topology.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| iscsi-san-multipath.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| fortigate-ha.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| ot-purdue-model.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **handover/** | | | | | | | | | |
| approval-workflow.md | ✅ | ✅ | ✅ | ✅ | ❌ (1 แบบ) | ✅ | ✅ | ✅ | ❌ |
| cicd-pipeline.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| incident-response.md | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

> \* smb-single-site.md มี prompt แบบเดียว แต่มีหลาย variant ภายใน — ถือว่า borderline

---

## รายละเอียด Section ที่ขาด

### ❌ ขาด "อัพเดตล่าสุด" — 11 ไฟล์

ไม่มีบรรทัด `อัพเดตล่าสุด` ท้ายไฟล์:

| ไฟล์ | folder |
|---|---|
| smb-single-site.md | pre-sales |
| 3-tier-data-center.md | pre-sales |
| sd-wan-multi-site.md | pre-sales |
| microservices-aws.md | pre-sales |
| azure-landing-zone.md | pre-sales |
| serverless-aws.md | pre-sales |
| firewall-dmz-zones.md | design |
| enterprise-wifi-deployment.md | design |
| spine-leaf-fabric.md | design |
| voip-deployment.md | design |
| approval-workflow.md | handover |

**แนะนำ**: เพิ่มบรรทัดนี้ท้ายแต่ละไฟล์:
```
**อัพเดตล่าสุด**: YYYY-MM-DD — initial template
```

---

### ❌ ขาด Prompt อย่างน้อย 2 แบบ — 2 ไฟล์

| ไฟล์ | Prompt ที่มี | ขาด |
|---|---|---|
| sd-wan-multi-site.md | 1 แบบ (generic) | แบบ B เช่น "document existing SD-WAN" หรือ "เพิ่ม branch" |
| approval-workflow.md | 1 แบบ (generic) | แบบ B เช่น "procurement approval" หรือ "document existing flow" |

---

## ไฟล์ที่ผ่านครบทุก section (12 ไฟล์)

- templates/pre-sales/3-tier-web-app.md
- templates/design/hyper-v-failover-cluster.md
- templates/design/vlan-segmentation.md
- templates/design/backup-architecture.md
- templates/design/rack-elevation-42u.md
- templates/design/vsan-cluster.md
- templates/design/ad-ds-topology.md
- templates/design/iscsi-san-multipath.md
- templates/design/fortigate-ha.md
- templates/design/ot-purdue-model.md
- templates/handover/cicd-pipeline.md
- templates/handover/incident-response.md

---

## ข้อสังเกตเพิ่มเติม

**Pragma Dark Style**: ทุก template ใช้ `background="#1a1a2e"` ถูกต้องสม่ำเสมอ — ✅ ผ่านทุกไฟล์

**Layer bars**: ทุก template ใช้ swimlane ด้วย startSize=30 และ fontStyle=1 — ✅ ผ่านทุกไฟล์

**ตารางข้อมูล**: ทุก template มีตาราง copy-ready อย่างน้อย 1 ตาราง — ✅ ผ่านทุกไฟล์

**Parameters table**: ทุก template มีตาราง "Parameters ที่ปรับได้" — ✅ ผ่านทุกไฟล์

---

**อัพเดตล่าสุด**: 2026-06-27 — initial audit
