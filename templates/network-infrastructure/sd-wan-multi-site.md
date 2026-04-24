# SD-WAN Multi-Site Network

> SD-WAN topology สำหรับองค์กรที่มีหลาย site — HQ + Branches

## 📋 ใช้ตอนไหน

- ✅ องค์กรที่มี 2+ sites (HQ + branches)
- ✅ ต้องการ internet breakout ที่แต่ละ site
- ✅ ต้องการ backup link (4G LTE หรือ MPLS)
- ✅ Vendor: Cisco Viptela, Fortinet SD-WAN, VMware VeloCloud
- ❌ **ไม่เหมาะกับ**: Single site, งบน้อย

---

## 🎨 Pragma Style Diagram (Draw.io XML)

```xml
<mxfile host="app.diagrams.net" version="24.0.0">
  <diagram name="SD-WAN Multi-Site — Pragma Style">
    <mxGraphModel dx="1400" dy="900" grid="0" background="#1a1a2e">
      <root>
        <mxCell id="0"/><mxCell id="1" parent="0"/>
        <mxCell id="title" value="SD-WAN Multi-Site Network" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=22;fontStyle=1;fontColor=#ffffff;" vertex="1" parent="1">
          <mxGeometry x="100" y="20" width="800" height="40" as="geometry"/>
        </mxCell>

        <mxCell id="L1" value="INTERNET / ISP" style="swimlane;startSize=30;fillColor=#1a2a4a;strokeColor=#4a90d9;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="70" width="920" height="110" as="geometry"/>
        </mxCell>
        <mxCell id="isp" value="ISP&#xa;True / AIS Fiber" style="strokeColor=#ffffff;sketch=0;html=1;fillColor=#036897;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.routers.atm_router;fontColor=#ffffff;fontSize=11;" vertex="1" parent="L1">
          <mxGeometry x="330" y="20" width="78" height="53" as="geometry"/>
        </mxCell>
        <mxCell id="lte" value="4G LTE Backup&#xa;AIS / DTAC" style="sketch=0;html=1;fillColor=#e65100;strokeColor=#ff9800;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.modems_and_phones.mobile_access_ip_phone_2;fontColor=#ffffff;fontSize=11;" vertex="1" parent="L1">
          <mxGeometry x="510" y="15" width="90" height="60" as="geometry"/>
        </mxCell>

        <mxCell id="L2" value="SECURITY LAYER — SD-WAN Edge (Fortinet)" style="swimlane;startSize=30;fillColor=#2d1a0e;strokeColor=#8b3a0f;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="210" width="920" height="200" as="geometry"/>
        </mxCell>
        <mxCell id="hq_box" value="HQ — Bangkok" style="swimlane;startSize=25;fillColor=#3d1f0a;strokeColor=#ff9800;fontColor=#ffffff;fontSize=11;fontStyle=1;html=1;" vertex="1" parent="L2">
          <mxGeometry x="30" y="35" width="360" height="140" as="geometry"/>
        </mxCell>
        <mxCell id="hq_fw" value="FortiGate 200F&#xa;SD-WAN Edge / Firewall&#xa;500 Mbps + 4G Backup" style="sketch=0;points=[[0.015,0.015,0],[0.985,0.015,0],[0.985,0.985,0],[0.015,0.985,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0.25,0],[1,0.5,0],[1,0.75,0],[0.75,1,0],[0.5,1,0],[0.25,1,0],[0,0.75,0],[0,0.5,0],[0,0.25,0]];verticalLabelPosition=bottom;html=1;verticalAlign=top;aspect=fixed;align=center;shape=mxgraph.cisco19.rect;prIcon=firewall;fillColor=#8b3a0f;strokeColor=#ff9800;fontColor=#ffffff;fontSize=10;" vertex="1" parent="hq_box">
          <mxGeometry x="112" y="28" width="128" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="tunnel_label" value="◄── SD-WAN IPsec Tunnel ──►" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=11;fontStyle=2;fontColor=#00bcd4;" vertex="1" parent="L2">
          <mxGeometry x="390" y="85" width="150" height="30" as="geometry"/>
        </mxCell>
        <mxCell id="br_box" value="Branch — [City]" style="swimlane;startSize=25;fillColor=#3d1f0a;strokeColor=#ff9800;fontColor=#ffffff;fontSize=11;fontStyle=1;html=1;" vertex="1" parent="L2">
          <mxGeometry x="530" y="35" width="360" height="140" as="geometry"/>
        </mxCell>
        <mxCell id="br_fw" value="FortiGate 60F&#xa;SD-WAN Edge / Firewall&#xa;200 Mbps + 4G Backup" style="sketch=0;points=[[0.015,0.015,0],[0.985,0.015,0],[0.985,0.985,0],[0.015,0.985,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0.25,0],[1,0.5,0],[1,0.75,0],[0.75,1,0],[0.5,1,0],[0.25,1,0],[0,0.75,0],[0,0.5,0],[0,0.25,0]];verticalLabelPosition=bottom;html=1;verticalAlign=top;aspect=fixed;align=center;shape=mxgraph.cisco19.rect;prIcon=firewall;fillColor=#8b3a0f;strokeColor=#ff9800;fontColor=#ffffff;fontSize=10;" vertex="1" parent="br_box">
          <mxGeometry x="112" y="28" width="128" height="60" as="geometry"/>
        </mxCell>

        <mxCell id="L3" value="CORE LAYER — Distribution Switch" style="swimlane;startSize=30;fillColor=#0d2b1a;strokeColor=#2e7d32;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="440" width="920" height="130" as="geometry"/>
        </mxCell>
        <mxCell id="hq_core" value="Core Switch L3&#xa;24x 1G + 4x SFP+&#xa;(HQ)" style="strokeColor=#ffffff;sketch=0;html=1;fillColor=#2e7d32;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.switches.layer_3_switch;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L3">
          <mxGeometry x="175" y="30" width="64" height="64" as="geometry"/>
        </mxCell>
        <mxCell id="br_core" value="Distribution Switch&#xa;16x 1G&#xa;(Branch)" style="strokeColor=#ffffff;sketch=0;html=1;fillColor=#2e7d32;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.switches.layer_3_switch;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L3">
          <mxGeometry x="665" y="30" width="64" height="64" as="geometry"/>
        </mxCell>

        <mxCell id="L4" value="ACCESS LAYER — PoE Switch" style="swimlane;startSize=30;fillColor=#1a0d2b;strokeColor=#6a1b9a;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="600" width="920" height="130" as="geometry"/>
        </mxCell>
        <mxCell id="hq_acc" value="Access Switch x2&#xa;24x PoE+ 1G (HQ)" style="strokeColor=#ffffff;sketch=0;html=1;fillColor=#6a1b9a;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.switches.layer_2_remote_switch;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L4">
          <mxGeometry x="147" y="35" width="101" height="50" as="geometry"/>
        </mxCell>
        <mxCell id="br_acc" value="Access Switch x1&#xa;16x PoE+ 1G (Branch)" style="strokeColor=#ffffff;sketch=0;html=1;fillColor=#6a1b9a;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;shape=mxgraph.cisco.switches.layer_2_remote_switch;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L4">
          <mxGeometry x="637" y="35" width="101" height="50" as="geometry"/>
        </mxCell>

        <mxCell id="L5" value="WIRELESS ZONE — WiFi 6 Access Points (via PoE+)" style="swimlane;startSize=30;fillColor=#0d1f2b;strokeColor=#0288d1;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="760" width="920" height="130" as="geometry"/>
        </mxCell>
        <mxCell id="hq_ap" value="WiFi 6 AP x4&#xa;Corporate + Guest (HQ)" style="points=[[0.03,0.36,0],[0.18,0,0],[0.5,0.34,0],[0.82,0,0],[0.97,0.36,0],[1,0.67,0],[0.975,0.975,0],[0.5,1,0],[0.025,0.975,0],[0,0.67,0]];verticalLabelPosition=bottom;sketch=0;html=1;verticalAlign=top;aspect=fixed;align=center;shape=mxgraph.cisco19.wireless_access_point2;fillColor=#0288d1;strokeColor=#ffffff;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L5">
          <mxGeometry x="183" y="20" width="50" height="50" as="geometry"/>
        </mxCell>
        <mxCell id="br_ap" value="WiFi 6 AP x2&#xa;Corporate + Guest (Branch)" style="points=[[0.03,0.36,0],[0.18,0,0],[0.5,0.34,0],[0.82,0,0],[0.97,0.36,0],[1,0.67,0],[0.975,0.975,0],[0.5,1,0],[0.025,0.975,0],[0,0.67,0]];verticalLabelPosition=bottom;sketch=0;html=1;verticalAlign=top;aspect=fixed;align=center;shape=mxgraph.cisco19.wireless_access_point2;fillColor=#0288d1;strokeColor=#ffffff;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L5">
          <mxGeometry x="673" y="20" width="50" height="50" as="geometry"/>
        </mxCell>

        <mxCell id="L6" value="END DEVICES" style="swimlane;startSize=30;fillColor=#1a1a1a;strokeColor=#424242;fontColor=#ffffff;fontSize=13;fontStyle=1;html=1;" vertex="1" parent="1">
          <mxGeometry x="40" y="920" width="920" height="130" as="geometry"/>
        </mxCell>
        <mxCell id="laptop" value="Laptops / PCs&#xa;(Wireless)" style="verticalLabelPosition=bottom;html=1;verticalAlign=top;align=center;shape=mxgraph.floorplan.laptop;fillColor=#aaaaaa;strokeColor=#ffffff;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L6">
          <mxGeometry x="120" y="20" width="60" height="53" as="geometry"/>
        </mxCell>
        <mxCell id="mobile" value="Smartphones&#xa;(Wireless)" style="sketch=0;verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=#ffffff;fillColor=#aaaaaa;align=center;outlineConnect=0;shape=mxgraph.citrix2.mobile;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L6">
          <mxGeometry x="280" y="20" width="25" height="50" as="geometry"/>
        </mxCell>
        <mxCell id="pc" value="Desktop PCs&#xa;(Wired)" style="fontColor=#ffffff;verticalAlign=top;verticalLabelPosition=bottom;align=center;html=1;fillColor=#aaaaaa;strokeColor=#ffffff;strokeWidth=2;shape=mxgraph.networks.desktop_pc;fontSize=10;" vertex="1" parent="L6">
          <mxGeometry x="630" y="15" width="30" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="mobile2" value="Smartphones&#xa;(Wireless)" style="sketch=0;verticalLabelPosition=bottom;aspect=fixed;html=1;verticalAlign=top;strokeColor=#ffffff;fillColor=#aaaaaa;align=center;outlineConnect=0;shape=mxgraph.citrix2.mobile;fontColor=#ffffff;fontSize=10;" vertex="1" parent="L6">
          <mxGeometry x="780" y="20" width="25" height="50" as="geometry"/>
        </mxCell>

        <mxCell id="e1" value="500 Mbps" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#4a90d9;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="isp" target="hq_fw"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e2" value="200 Mbps" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#4a90d9;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="isp" target="br_fw"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e3" value="Backup" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#ff9800;strokeWidth=2;dashed=1;fontColor=#ff9800;fontSize=10;" edge="1" parent="1" source="lte" target="hq_fw"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e4" value="Backup" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#ff9800;strokeWidth=2;dashed=1;fontColor=#ff9800;fontSize=10;" edge="1" parent="1" source="lte" target="br_fw"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e5" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#00bcd4;strokeWidth=3;dashed=1;" edge="1" parent="1" source="hq_fw" target="br_fw"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e6" value="1G" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#2e7d32;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="hq_fw" target="hq_core"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e7" value="1G" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#2e7d32;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="br_fw" target="br_core"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e8" value="1G" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#6a1b9a;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="hq_core" target="hq_acc"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e9" value="1G" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#6a1b9a;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="br_core" target="br_acc"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e10" value="PoE+" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#0288d1;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="hq_acc" target="hq_ap"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e11" value="PoE+" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#0288d1;strokeWidth=2;fontColor=#ffffff;fontSize=10;" edge="1" parent="1" source="br_acc" target="br_ap"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e12" value="WiFi" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#aaaaaa;strokeWidth=2;dashed=1;fontColor=#aaaaaa;fontSize=10;" edge="1" parent="1" source="hq_ap" target="laptop"><mxGeometry relative="1" as="geometry"/></mxCell>
        <mxCell id="e13" value="WiFi" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#aaaaaa;strokeWidth=2;dashed=1;fontColor=#aaaaaa;fontSize=10;" edge="1" parent="1" source="br_ap" target="pc"><mxGeometry relative="1" as="geometry"/></mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

---

## 💡 Prompt ตัวอย่าง

```
ใช้ template sd-wan-multi-site.md แบบ Pragma Style
ปรับสำหรับ [ชื่อบริษัท]:
- HQ: [ที่ตั้ง + users]
- Branch: [ที่ตั้ง + users]
- SD-WAN: [Vendor]
- Internet: HQ [Mbps] / Branch [Mbps]
- Backup: 4G LTE
```

---

## 🔧 Parameters ที่ปรับได้

| Parameter | Default | ทางเลือก |
|---|---|---|
| Sites | HQ + 1 Branch | 2-20+ |
| Vendor | Fortinet | Cisco, VMware |
| Backup | 4G LTE | MPLS, Secondary ISP |
| Bandwidth | 500/200 Mbps | ตาม requirement |

---

## 📌 Notes สำหรับ SI
- FortiGate 200F → HQ ที่ต้องการ throughput สูง
- FortiGate 60F → Branch ขนาดเล็ก-กลาง
- SD-WAN tunnel ใช้ IPsec encryption โดย default
- ถ้า branch < 20 users → FortiGate 40F ประหยัดกว่า

### Related Templates
- Single site → `smb-single-site.md`
- Firewall zones → `firewall-dmz-zones.md`
