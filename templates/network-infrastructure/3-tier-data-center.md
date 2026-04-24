# 3-Tier Data Center Network

> Network topology มาตรฐานสำหรับ Data Center แบบ 3-tier (Core / Distribution / Access)

## 📋 ใช้ตอนไหน

- ✅ Enterprise data center 100-1000 users
- ✅ ต้องการ HA (redundant)
- ✅ ใช้กับ Cisco Catalyst หรือ Nexus series
- ❌ **ไม่เหมาะกับ**: SMB < 50 users, Spine-Leaf architecture

---

## 🎨 Pragma Style Diagram (Draw.io XML)

```xml
<mxfile host="app.diagrams.net" version="24.0.0">
  <diagram name="3-Tier Data Center — Pragma Style">
    <mxGraphModel dx="1400" dy="900" grid="0" background="#1a1a2e">
      <root>
        <mxCell id="0"/><mxCell id="1" parent="0"/>
        <mxCell id="title" value="3-Tier Data Center Network" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=22;fontStyle=1;fontColor=#ffffff;" vertex="1" parent="1">
          <mxGeometry x="100" y="20" width="800" height="40" as="geometry"/>
        </mxCell>

        <mxCell id="L1" value="INTERNET / ISP" style="swimlane;startSize=30;fillColor=#1a2a4a;strokeColor=#4a90d9;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="70" width="920" height="110" as="geometry"/>
        </mxCell>
        <mxCell id="isp" value="ISP&#xa;Internet" style="strokeColor=#ffffff;sketch=0;html=1;fillColor=#036897;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.routers.atm_router;fontColor=#ffffff;fontSize=11;" vertex="1" parent="L1">
          <mxGeometry x="421" y="20" width="78" height="53" as="geometry"/>
        </mxCell>

        <mxCell id="L2" value="SECURITY LAYER — Firewall HA Pair" style="swimlane;startSize=30;fillColor=#2d1a0e;strokeColor=#8b3a0f;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="210" width="920" height="150" as="geometry"/>
        </mxCell>
        <mxCell id="fw1" value="Firewall Primary&#xa;Active" style="sketch=0;points=[[0.015,0.015,0],[0.985,0.015,0],[0.985,0.985,0],[0.015,0.985,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0.25,0],[1,0.5,0],[1,0.75,0],[0.75,1,0],[0.5,1,0],[0.25,1,0],[0,0.75,0],[0,0.5,0],[0,0.25,0]];verticalLabelPosition=bottom;html=1;verticalAlign=top;aspect=fixed;align=center;shape=mxgraph.cisco19.rect;prIcon=firewall;fillColor=#8b3a0f;strokeColor=#ff9800;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L2">
          <mxGeometry x="240" y="30" width="128" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="fw2" value="Firewall Secondary&#xa;Standby" style="sketch=0;points=[[0.015,0.015,0],[0.985,0.015,0],[0.985,0.985,0],[0.015,0.985,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0.25,0],[1,0.5,0],[1,0.75,0],[0.75,1,0],[0.5,1,0],[0.25,1,0],[0,0.75,0],[0,0.5,0],[0,0.25,0]];verticalLabelPosition=bottom;html=1;verticalAlign=top;aspect=fixed;align=center;shape=mxgraph.cisco19.rect;prIcon=firewall;fillColor=#5a2a0a;strokeColor=#ff9800;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L2">
          <mxGeometry x="540" y="30" width="128" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="ha_label" value="◄── HA Pair ──►" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=10;fontStyle=2;fontColor=#00bcd4;" vertex="1" parent="L2">
          <mxGeometry x="385" y="55" width="140" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="L3" value="CORE LAYER — L3 Switch (HSRP/VRRP)" style="swimlane;startSize=30;fillColor=#0d2b1a;strokeColor=#2e7d32;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="390" width="920" height="150" as="geometry"/>
        </mxCell>
        <mxCell id="core1" value="Core Switch 1&#xa;Cisco Nexus 9500&#xa;10G Uplink" style="strokeColor=#ffffff;sketch=0;html=1;fillColor=#2e7d32;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.switches.layer_3_switch;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L3">
          <mxGeometry x="240" y="35" width="64" height="64" as="geometry"/>
        </mxCell>
        <mxCell id="core2" value="Core Switch 2&#xa;Cisco Nexus 9500&#xa;10G Uplink" style="strokeColor=#ffffff;sketch=0;html=1;fillColor=#2e7d32;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.switches.layer_3_switch;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L3">
          <mxGeometry x="590" y="35" width="64" height="64" as="geometry"/>
        </mxCell>

        <mxCell id="L4" value="DISTRIBUTION LAYER — L3 Switch" style="swimlane;startSize=30;fillColor=#1a0d2b;strokeColor=#6a1b9a;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="570" width="920" height="150" as="geometry"/>
        </mxCell>
        <mxCell id="dist1" value="Dist Switch 1&#xa;Catalyst 9500" style="strokeColor=#ffffff;sketch=0;html=1;fillColor=#6a1b9a;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.switches.layer_3_switch;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L4">
          <mxGeometry x="120" y="35" width="64" height="64" as="geometry"/>
        </mxCell>
        <mxCell id="dist2" value="Dist Switch 2&#xa;Catalyst 9500" style="strokeColor=#ffffff;sketch=0;html=1;fillColor=#6a1b9a;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.switches.layer_3_switch;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L4">
          <mxGeometry x="420" y="35" width="64" height="64" as="geometry"/>
        </mxCell>
        <mxCell id="dist3" value="Dist Switch 3&#xa;Catalyst 9500" style="strokeColor=#ffffff;sketch=0;html=1;fillColor=#6a1b9a;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.switches.layer_3_switch;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L4">
          <mxGeometry x="720" y="35" width="64" height="64" as="geometry"/>
        </mxCell>

        <mxCell id="L5" value="ACCESS LAYER — PoE Switch" style="swimlane;startSize=30;fillColor=#0d1f2b;strokeColor=#0288d1;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="750" width="920" height="150" as="geometry"/>
        </mxCell>
        <mxCell id="acc1" value="Access Stack 1&#xa;Floor 1 / 48x PoE+" style="strokeColor=#ffffff;sketch=0;html=1;fillColor=#0288d1;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.switches.layer_2_remote_switch;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L5">
          <mxGeometry x="90" y="40" width="101" height="50" as="geometry"/>
        </mxCell>
        <mxCell id="acc2" value="Access Stack 2&#xa;Floor 2 / 48x PoE+" style="strokeColor=#ffffff;sketch=0;html=1;fillColor=#0288d1;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.switches.layer_2_remote_switch;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L5">
          <mxGeometry x="390" y="40" width="101" height="50" as="geometry"/>
        </mxCell>
        <mxCell id="acc3" value="Access Stack 3&#xa;Floor 3 / 48x PoE+" style="strokeColor=#ffffff;sketch=0;html=1;fillColor=#0288d1;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.switches.layer_2_remote_switch;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L5">
          <mxGeometry x="690" y="40" width="101" height="50" as="geometry"/>
        </mxCell>

        <mxCell id="L6" value="END DEVICES" style="swimlane;startSize=30;fillColor=#1a1a1a;strokeColor=#424242;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="930" width="920" height="130" as="geometry"/>
        </mxCell>
        <mxCell id="pc" value="Workstations&#xa;(Wired)" style="fontColor=#ffffff;verticalAlign=top;verticalLabelPosition=bottom;align=center;html=1;fillColor=#aaaaaa;strokeColor=#ffffff;strokeWidth=2;shape=mxgraph.networks.desktop_pc;fontSize=10;" vertex="1" parent="L6">
          <mxGeometry x="100" y="25" width="30" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="laptop" value="Laptops&#xa;(Wireless)" style="verticalLabelPosition=bottom;html=1;verticalAlign=top;align=center;shape=mxgraph.floorplan.laptop;fillColor=#aaaaaa;strokeColor=#ffffff;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L6">
          <mxGeometry x="300" y="25" width="60" height="53" as="geometry"/>
        </mxCell>
        <mxCell id="srv" value="Server Farm&#xa;(Rack)" style="shape=cylinder3;whiteSpace=wrap;html=1;fillColor=#aaaaaa;strokeColor=#ffffff;fontColor=#ffffff;fontSize=10;verticalLabelPosition=bottom;verticalAlign=top;" vertex="1" parent="L6">
          <mxGeometry x="600" y="20" width="60" height="70" as="geometry"/>
        </mxCell>
        <mxCell id="phone" value="IP Phones&#xa;(PoE)" style="sketch=0;html=1;fillColor=#aaaaaa;strokeColor=#ffffff;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.modems_and_phones.ip_phone;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L6">
          <mxGeometry x="800" y="20" width="53" height="70" as="geometry"/>
        </mxCell>

        <mxCell id="e1" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#4a90d9;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="isp" target="fw1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e2" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#4a90d9;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="isp" target="fw2"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e3" value="HA" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#00bcd4;strokeWidth=2;dashed=1;fontColor=#00bcd4;fontSize=10;" edge="1" parent="1" source="fw1" target="fw2"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e4" value="10G" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#2e7d32;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="fw1" target="core1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e5" value="10G" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#2e7d32;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="fw2" target="core2"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e6" value="HSRP" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#00bcd4;strokeWidth=2;dashed=1;fontColor=#00bcd4;fontSize=10;" edge="1" parent="1" source="core1" target="core2"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e7" value="10G" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#6a1b9a;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="core1" target="dist1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e8" value="10G" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#6a1b9a;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="core1" target="dist2"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e9" value="10G" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#6a1b9a;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="core2" target="dist2"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e10" value="10G" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#6a1b9a;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="core2" target="dist3"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e11" value="1G" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#0288d1;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="dist1" target="acc1"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e12" value="1G" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#0288d1;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="dist2" target="acc2"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e13" value="1G" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#0288d1;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="dist3" target="acc3"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e14" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#aaaaaa;strokeWidth=2;dashed=1;fontColor=#aaaaaa;fontSize=10;" edge="1" parent="1" source="acc1" target="pc"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e15" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#aaaaaa;strokeWidth=2;dashed=1;fontColor=#aaaaaa;fontSize=10;" edge="1" parent="1" source="acc2" target="laptop"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e16" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#aaaaaa;strokeWidth=2;dashed=1;fontColor=#aaaaaa;fontSize=10;" edge="1" parent="1" source="acc3" target="phone"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e17" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#aaaaaa;strokeWidth=2;fontColor=#aaaaaa;fontSize=10;" edge="1" parent="1" source="core1" target="srv"><mxGeometry relative="1" as="geometry"/></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

---

## 💡 Prompt ตัวอย่าง

### แบบ A: Enterprise 3-tier
```
ใช้ template 3-tier-data-center.md แบบ Pragma Style
ปรับสำหรับ [ชื่อลูกค้า]:
- Users: [จำนวน]
- Firewall: [Fortinet/Palo Alto/Cisco]
- Core: [Cisco Nexus/Catalyst model]
- Distribution: [จำนวน + model]
- Access: [จำนวน floors + ports]
```

### แบบ B: Collapsed Core (2-tier)
```
ใช้ template 3-tier-data-center.md แบบ Pragma Style
แต่ทำเป็น Collapsed Core 2-tier:
- รวม Core + Distribution เป็น layer เดียว
- Access layer 6 ตัว
- HA pair Firewall
```

### แบบ C: เพิ่ม Server Farm
```
ใช้ template 3-tier-data-center.md แบบ Pragma Style
เพิ่ม Server Farm zone:
- Production servers
- Management servers
- Backup storage
- iDRAC/iLO OOB management
```

---

## 🔧 Parameters ที่ปรับได้

| Parameter | Default | ทางเลือก |
|---|---|---|
| Firewall | HA Pair | Single, Cluster |
| Core Switch | Cisco Nexus 9500 | Catalyst 9500, Arista 7050 |
| Distribution | 3 ตัว | 2-8 ตาม zone |
| Access | 48-port PoE+ | 24-port, PoE++ |
| Uplink Core-Dist | 10G | 25G, 40G, 100G |

---

## 📌 Notes สำหรับ SI
- **HA Pair Firewall**: Active-Passive หรือ Active-Active
- **HSRP/VRRP**: ที่ Core layer สำหรับ gateway redundancy
- **Uplink**: Core → Distribution ควร 10G ขึ้นไป
- **Access**: PoE+ (802.3at) สำหรับ IP Phone + AP

### Related Templates
- SD-WAN → `sd-wan-multi-site.md`
- Firewall Zones → `firewall-dmz-zones.md`
- WiFi → `enterprise-wifi-deployment.md`
