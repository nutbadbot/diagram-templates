# SMB Single-Site Network

> Network topology สำหรับ SMB 20-100 users — single site, simple และ cost-effective

## 📋 ใช้ตอนไหน

- ✅ SMB 20-100 users, single office
- ✅ งบจำกัด ต้องการ simple design
- ✅ ต้องการ WiFi + Wired + Internet
- ❌ **ไม่เหมาะกับ**: Multi-site, 100+ users, ต้องการ HA

---

## 🎨 Pragma Style Diagram (Draw.io XML)

```xml
<mxfile host="app.diagrams.net" version="24.0.0">
  <diagram name="SMB Single Site — Pragma Style">
    <mxGraphModel dx="1400" dy="900" grid="0" background="#1a1a2e">
      <root>
        <mxCell id="0"/><mxCell id="1" parent="0"/>
        <mxCell id="title" value="SMB Single-Site Network" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=22;fontStyle=1;fontColor=#ffffff;" vertex="1" parent="1">
          <mxGeometry x="100" y="20" width="800" height="40" as="geometry"/>
        </mxCell>

        <mxCell id="L1" value="INTERNET / ISP" style="swimlane;startSize=30;fillColor=#1a2a4a;strokeColor=#4a90d9;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="70" width="920" height="110" as="geometry"/>
        </mxCell>
        <mxCell id="isp" value="ISP&#xa;True / AIS&#xa;300 Mbps" style="strokeColor=#ffffff;sketch=0;html=1;fillColor=#036897;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.routers.atm_router;fontColor=#ffffff;fontSize=11;" vertex="1" parent="L1">
          <mxGeometry x="330" y="20" width="78" height="53" as="geometry"/>
        </mxCell>
        <mxCell id="lte" value="4G LTE Backup&#xa;50 Mbps" style="sketch=0;html=1;fillColor=#e65100;strokeColor=#ff9800;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.modems_and_phones.mobile_access_ip_phone_2;fontColor=#ffffff;fontSize=11;" vertex="1" parent="L1">
          <mxGeometry x="510" y="15" width="90" height="60" as="geometry"/>
        </mxCell>

        <mxCell id="L2" value="SECURITY LAYER — Firewall / UTM" style="swimlane;startSize=30;fillColor=#2d1a0e;strokeColor=#8b3a0f;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="210" width="920" height="130" as="geometry"/>
        </mxCell>
        <mxCell id="fw" value="FortiGate 60F&#xa;Firewall / UTM&#xa;300 Mbps + 4G Backup" style="sketch=0;points=[[0.015,0.015,0],[0.985,0.015,0],[0.985,0.985,0],[0.015,0.985,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0.25,0],[1,0.5,0],[1,0.75,0],[0.75,1,0],[0.5,1,0],[0.25,1,0],[0,0.75,0],[0,0.5,0],[0,0.25,0]];verticalLabelPosition=bottom;html=1;verticalAlign=top;aspect=fixed;align=center;shape=mxgraph.cisco19.rect;prIcon=firewall;fillColor=#8b3a0f;strokeColor=#ff9800;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L2">
          <mxGeometry x="390" y="25" width="128" height="60" as="geometry"/>
        </mxCell>

        <mxCell id="L3" value="CORE LAYER — L2/L3 Switch" style="swimlane;startSize=30;fillColor=#0d2b1a;strokeColor=#2e7d32;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="370" width="920" height="130" as="geometry"/>
        </mxCell>
        <mxCell id="core" value="Core Switch&#xa;24x 1G + 4x SFP+&#xa;PoE+ Ready" style="strokeColor=#ffffff;sketch=0;html=1;fillColor=#2e7d32;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.switches.layer_3_switch;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L3">
          <mxGeometry x="420" y="25" width="64" height="64" as="geometry"/>
        </mxCell>

        <mxCell id="L4" value="ACCESS LAYER — PoE Switch" style="swimlane;startSize=30;fillColor=#1a0d2b;strokeColor=#6a1b9a;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="530" width="920" height="130" as="geometry"/>
        </mxCell>
        <mxCell id="acc" value="Access Switch&#xa;24x PoE+ 1G" style="strokeColor=#ffffff;sketch=0;html=1;fillColor=#6a1b9a;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.switches.layer_2_remote_switch;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L4">
          <mxGeometry x="300" y="35" width="101" height="50" as="geometry"/>
        </mxCell>
        <mxCell id="nas" value="NAS / File Server&#xa;Storage" style="shape=cylinder3;whiteSpace=wrap;html=1;fillColor=#6a1b9a;strokeColor=#ffffff;fontColor=#ffffff;fontSize=10;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="L4">
          <mxGeometry x="580" y="20" width="60" height="70" as="geometry"/>
        </mxCell>

        <mxCell id="L5" value="WIRELESS ZONE — WiFi 6 Access Points (via PoE+)" style="swimlane;startSize=30;fillColor=#0d1f2b;strokeColor=#0288d1;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="690" width="920" height="130" as="geometry"/>
        </mxCell>
        <mxCell id="ap1" value="WiFi 6 AP&#xa;Corporate SSID" style="points=[[0.03,0.36,0],[0.18,0,0],[0.5,0.34,0],[0.82,0,0],[0.97,0.36,0],[1,0.67,0],[0.975,0.975,0],[0.5,1,0],[0.025,0.975,0],[0,0.67,0]];verticalLabelPosition=bottom;sketch=0;html=1;verticalAlign=top;aspect=fixed;align=center;shape=mxgraph.cisco19.wireless_access_point2;fillColor=#0288d1;strokeColor=#ffffff;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L5">
          <mxGeometry x="250" y="25" width="50" height="50" as="geometry"/>
        </mxCell>
        <mxCell id="ap2" value="WiFi 6 AP&#xa;Guest SSID" style="points=[[0.03,0.36,0],[0.18,0,0],[0.5,0.34,0],[0.82,0,0],[0.97,0.36,0],[1,0.67,0],[0.975,0.975,0],[0.5,1,0],[0.025,0.975,0],[0,0.67,0]];verticalLabelPosition=bottom;sketch=0;html=1;verticalAlign=top;aspect=fixed;align=center;shape=mxgraph.cisco19.wireless_access_point2;fillColor=#0288d1;strokeColor=#ffffff;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L5">
          <mxGeometry x="570" y="25" width="50" height="50" as="geometry"/>
        </mxCell>

        <mxCell id="L6" value="END DEVICES" style="swimlane;startSize=30;fillColor=#1a1a1a;strokeColor=#424242;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="850" width="920" height="130" as="geometry"/>
        </mxCell>
        <mxCell id="pc" value="Workstations&#xa;(Wired)" style="fontColor=#ffffff;verticalAlign=top;verticalLabelPosition=bottom;align=center;html=1;fillColor=#aaaaaa;strokeColor=#ffffff;strokeWidth=2;shape=mxgraph.networks.desktop_pc;fontSize=10;" vertex="1" parent="L6">
          <mxGeometry x="100" y="20" width="30" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="laptop" value="Laptops&#xa;(WiFi)" style="verticalLabelPosition=bottom;html=1;verticalAlign=top;align=center;shape=mxgraph.floorplan.laptop;fillColor=#aaaaaa;strokeColor=#ffffff;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L6">
          <mxGeometry x="280" y="20" width="60" height="53" as="geometry"/>
        </mxCell>
        <mxCell id="mobile" value="Smartphones&#xa;(WiFi)" style="sketch=0;verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=#ffffff;fillColor=#aaaaaa;align=center;outlineConnect=0;shape=mxgraph.citrix2.mobile;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L6">
          <mxGeometry x="480" y="20" width="25" height="50" as="geometry"/>
        </mxCell>
        <mxCell id="phone" value="IP Phones&#xa;(PoE)" style="sketch=0;html=1;fillColor=#aaaaaa;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.modems_and_phones.ip_phone;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L6">
          <mxGeometry x="700" y="15" width="53" height="70" as="geometry"/>
        </mxCell>

        <mxCell id="e1" value="300 Mbps" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#4a90d9;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="isp" target="fw"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e2" value="Backup" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#ff9800;strokeWidth=2;dashed=1;fontColor=#ff9800;fontSize=10;" edge="1" parent="1" source="lte" target="fw"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e3" value="1G" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#2e7d32;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="fw" target="core"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e4" value="1G" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#6a1b9a;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="core" target="acc"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e5" value="1G" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#6a1b9a;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="core" target="nas"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e6" value="PoE+" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#0288d1;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="acc" target="ap1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e7" value="PoE+" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#0288d1;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="acc" target="ap2"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e8" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#aaaaaa;strokeWidth=2;dashed=1;" edge="1" parent="1" source="ap1" target="laptop"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e9" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#aaaaaa;strokeWidth=2;dashed=1;" edge="1" parent="1" source="ap2" target="mobile"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e10" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#aaaaaa;strokeWidth=2;" edge="1" parent="1" source="acc" target="pc"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e11" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#aaaaaa;strokeWidth=2;" edge="1" parent="1" source="acc" target="phone"><mxGeometry relative="1" as="geometry"/></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

---

## 💡 Prompt ตัวอย่าง

### แบบ A: SMB พื้นฐาน
```
ใช้ template smb-single-site.md แบบ Pragma Style
ปรับสำหรับ [ชื่อบริษัท]:
- Users: [จำนวน]
- Internet: [ISP + bandwidth]
- Firewall: [model]
- WiFi: [จำนวน AP + vendor]
```

### แบบ B: เพิ่ม CCTV / IoT
```
ใช้ template smb-single-site.md แบบ Pragma Style
เพิ่ม IoT zone:
- CCTV 8 กล้อง (PoE)
- NVR 1 ตัว
- แยก VLAN จาก Corporate
```

---

## 🔧 Parameters ที่ปรับได้

| Parameter | Default | ทางเลือก |
|---|---|---|
| Internet | 300 Mbps Fiber | 100-1000 Mbps |
| Firewall | FortiGate 60F | Sophos XG, Cisco Meraki |
| Core Switch | 24-port L3 | 48-port, PoE++ |
| AP จำนวน | 2 | 1-10 ตาม office size |
| NAS | มี | ไม่มี (ใช้ Cloud แทน) |

---

## 📌 Notes สำหรับ SI
- SMB ส่วนใหญ่ไม่ต้องการ Distribution layer — Core เชื่อม Access ตรงได้
- ถ้า users < 30 → FortiGate 40F พอ
- ถ้ามี CCTV → แยก VLAN และ PoE budget ให้ครบ
- NAS ควรต่อ Core switch โดยตรง ไม่ใช่ผ่าน Access

### Related Templates
- Multi-site → `sd-wan-multi-site.md`
- WiFi detail → `enterprise-wifi-deployment.md`
