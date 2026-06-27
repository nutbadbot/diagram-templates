# Rack Elevation 42U

> Rack diagram มาตรฐาน 42U — Front View + Rear View (Draw.io XML พร้อมทั้งคู่), U position, dual power feed A/B, cable management

## 📋 ใช้ตอนไหน

- ✅ ออกแบบ rack layout ก่อนติดตั้งจริง
- ✅ เอกสาร as-built หลังติดตั้ง
- ✅ DC project ทุกขนาด — SMB ถึง Enterprise
- ✅ ใช้คู่กับ 3-tier-data-center.md
- ❌ **ไม่เหมาะกับ**: diagram แบบ logical/topology (ใช้ template อื่นแทน)

---

## 🎨 Pragma Style Diagram (Draw.io XML)

```xml
<mxfile host="app.diagrams.net" version="24.0.0">
  <diagram name="42U Rack Elevation — Pragma Style">
    <mxGraphModel dx="1400" dy="900" grid="0" background="#1a1a2e">
      <root>
        <mxCell id="0"/><mxCell id="1" parent="0"/>

        <mxCell id="title" value="42U Rack Elevation — Front View" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=20;fontStyle=1;fontColor=#ffffff;" vertex="1" parent="1">
          <mxGeometry x="60" y="20" width="400" height="35" as="geometry"/>
        </mxCell>

        <mxCell id="ruler_bg" value="" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#0d0d1a;strokeColor=#333366;" vertex="1" parent="1">
          <mxGeometry x="40" y="60" width="30" height="840" as="geometry"/>
        </mxCell>

        <mxCell id="rack_frame" value="" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#111122;strokeColor=#4a4a88;strokeWidth=3;" vertex="1" parent="1">
          <mxGeometry x="70" y="60" width="360" height="840" as="geometry"/>
        </mxCell>

        <mxCell id="u42" value="42" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="40" y="62" width="30" height="20" as="geometry"/></mxCell>
        <mxCell id="u40" value="40" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="40" y="102" width="30" height="20" as="geometry"/></mxCell>
        <mxCell id="u35" value="35" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="40" y="202" width="30" height="20" as="geometry"/></mxCell>
        <mxCell id="u30" value="30" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="40" y="302" width="30" height="20" as="geometry"/></mxCell>
        <mxCell id="u25" value="25" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="40" y="402" width="30" height="20" as="geometry"/></mxCell>
        <mxCell id="u20" value="20" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="40" y="502" width="30" height="20" as="geometry"/></mxCell>
        <mxCell id="u15" value="15" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="40" y="602" width="30" height="20" as="geometry"/></mxCell>
        <mxCell id="u10" value="10" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="40" y="702" width="30" height="20" as="geometry"/></mxCell>
        <mxCell id="u5"  value="5"  style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="40" y="802" width="30" height="20" as="geometry"/></mxCell>
        <mxCell id="u1"  value="1"  style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="40" y="878" width="30" height="20" as="geometry"/></mxCell>


        <mxCell id="cm1" value="Cable Manager 1U" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#555577;fontColor=#aaaaaa;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="70" width="350" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="pp1" value="Patch Panel 24-port CAT6A  [U41]" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a3a5c;strokeColor=#4a90d9;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="90" width="350" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="cm2" value="Cable Manager 1U" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#555577;fontColor=#aaaaaa;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="110" width="350" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="core_sw" value="Core Switch  [U38-39]&#xa;Cisco Catalyst 9500 / Dell N3248  —  10GbE Uplink" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#0d2b1a;strokeColor=#2e7d32;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="130" width="350" height="40" as="geometry"/>
        </mxCell>

        <mxCell id="cm3" value="Cable Manager 1U" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#555577;fontColor=#aaaaaa;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="170" width="350" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="fw1" value="Firewall — Primary  [U36]&#xa;FortiGate 200F / Palo Alto PA-450  Active" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#2d1a0e;strokeColor=#ff9800;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="190" width="350" height="20" as="geometry"/>
        </mxCell>
        <mxCell id="fw2" value="Firewall — Standby  [U35]&#xa;FortiGate 200F / Palo Alto PA-450  Passive" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a0e06;strokeColor=#ff9800;fontColor=#aaaaaa;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="210" width="350" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="cm4" value="Cable Manager 1U" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#555577;fontColor=#aaaaaa;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="230" width="350" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="acc_sw1" value="Access Switch 1  [U33]  —  48x PoE+ 1GbE  Floor 1" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a0d2b;strokeColor=#6a1b9a;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="250" width="350" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="acc_sw2" value="Access Switch 2  [U32]  —  48x PoE+ 1GbE  Floor 2" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a0d2b;strokeColor=#6a1b9a;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="270" width="350" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="acc_sw3" value="Access Switch 3  [U31]  —  24x PoE+ 1GbE  Server Room" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a0d2b;strokeColor=#6a1b9a;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="290" width="350" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="cm5" value="Cable Manager 1U" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#555577;fontColor=#aaaaaa;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="310" width="350" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="srv1" value="Server 1  [U26-29]&#xa;Dell PowerEdge R750  —  2x Xeon / 256GB RAM&#xa;Hyper-V Node 1 (NFI-HVC01)" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#2d1a4a;strokeColor=#9c27b0;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="330" width="350" height="80" as="geometry"/>
        </mxCell>

        <mxCell id="srv2" value="Server 2  [U22-25]&#xa;Dell PowerEdge R750  —  2x Xeon / 256GB RAM&#xa;Hyper-V Node 2 (NFI-HVC02)" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a2a1a;strokeColor=#388e3c;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="410" width="350" height="80" as="geometry"/>
        </mxCell>

        <mxCell id="cm6" value="Cable Manager 1U" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#555577;fontColor=#aaaaaa;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="490" width="350" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="storage" value="Storage Array  [U17-20]&#xa;Dell MD3820 / PowerVault  —  SAS/iSCSI&#xa;Cluster Shared Volumes" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a0d;strokeColor=#f9a825;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="510" width="350" height="80" as="geometry"/>
        </mxCell>

        <mxCell id="kvm" value="KVM Switch 1U  [U16]  —  8-port  HDMI/USB" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a1a;strokeColor=#424242;fontColor=#aaaaaa;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="590" width="350" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="bkp" value="Backup Server  [U15]  —  Veeam B&amp;R / Commvault" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a0d;strokeColor=#ff9800;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="610" width="350" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="empty1" value="— Empty  [U12-14] —" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#111122;strokeColor=#333344;fontColor=#444466;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="630" width="350" height="60" as="geometry"/>
        </mxCell>

        <mxCell id="oob" value="OOB Management Switch  [U11]  —  iDRAC / iLO / IPMI" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a2a4a;strokeColor=#4a90d9;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="690" width="350" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="empty2" value="— Empty  [U8-10] —" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#111122;strokeColor=#333344;fontColor=#444466;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="710" width="350" height="60" as="geometry"/>
        </mxCell>

        <mxCell id="ups" value="UPS  [U5-7]&#xa;APC Smart-UPS 3000VA / Eaton 9PX&#xa;Runtime ~20 min @ full load" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#2a1a0a;strokeColor=#ff6600;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="770" width="350" height="60" as="geometry"/>
        </mxCell>

        <mxCell id="cm7" value="Cable Manager 1U  [U4]" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#555577;fontColor=#aaaaaa;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="830" width="350" height="20" as="geometry"/>
        </mxCell>
        <mxCell id="cm8" value="Cable Manager 1U  [U3]" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#555577;fontColor=#aaaaaa;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="850" width="350" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="pdu" value="PDU  [U1-2]  —  Vertical / Horizontal  20A" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a0a0a;strokeColor=#cc0000;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="75" y="870" width="350" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="leg_title" value="Legend" style="text;html=1;strokeColor=none;fillColor=none;align=left;fontSize=12;fontStyle=1;fontColor=#ffffff;" vertex="1" parent="1">
          <mxGeometry x="460" y="70" width="200" height="20" as="geometry"/>
        </mxCell>
        <mxCell id="leg1" value="Network / Switching" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#0d2b1a;strokeColor=#2e7d32;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="460" y="95" width="180" height="22" as="geometry"/>
        </mxCell>
        <mxCell id="leg2" value="Security / Firewall" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#2d1a0e;strokeColor=#ff9800;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="460" y="122" width="180" height="22" as="geometry"/>
        </mxCell>
        <mxCell id="leg3" value="Server / Compute" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#2d1a4a;strokeColor=#9c27b0;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="460" y="149" width="180" height="22" as="geometry"/>
        </mxCell>
        <mxCell id="leg4" value="Storage / NAS" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a0d;strokeColor=#f9a825;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="460" y="176" width="180" height="22" as="geometry"/>
        </mxCell>
        <mxCell id="leg5" value="Power / UPS" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#2a1a0a;strokeColor=#ff6600;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="460" y="203" width="180" height="22" as="geometry"/>
        </mxCell>
        <mxCell id="leg6" value="Patch Panel / Cable Mgmt" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a2a4a;strokeColor=#4a90d9;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="460" y="230" width="180" height="22" as="geometry"/>
        </mxCell>
        <mxCell id="leg7" value="Empty / Available" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#111122;strokeColor=#333344;fontColor=#444466;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="460" y="257" width="180" height="22" as="geometry"/>
        </mxCell>

        <mxCell id="sum_title" value="Rack Summary" style="text;html=1;strokeColor=none;fillColor=none;align=left;fontSize=12;fontStyle=1;fontColor=#ffffff;" vertex="1" parent="1">
          <mxGeometry x="460" y="310" width="200" height="20" as="geometry"/>
        </mxCell>
        <mxCell id="summary" value="Total: 42U&#xa;Used: 36U&#xa;Empty: 6U (U8-10, U12-14)&#xa;&#xa;Power: 2x PDU 20A&#xa;UPS: 3000VA (~20 min)&#xa;&#xa;Cooling: Front-to-Back&#xa;Weight: ~400kg est." style="rounded=1;whiteSpace=wrap;html=1;fillColor=#0d0d1a;strokeColor=#333366;fontColor=#aaaaaa;fontSize=10;align=left;spacingLeft=8;" vertex="1" parent="1">
          <mxGeometry x="460" y="335" width="200" height="140" as="geometry"/>
        </mxCell>

      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

---

## 🎨 Rear View (Draw.io XML)
> มุมมองจากด้านหลัง (Hot Aisle Side) — แสดง dual power feed A/B, PSU split ซ้าย/ขวา, port หลัง switch, PDU vertical ซ้าย-ขวา

```xml
<mxfile host="app.diagrams.net" version="24.0.0">
  <diagram name="42U Rack Elevation — Rear View">
    <mxGraphModel dx="1400" dy="900" grid="0" background="#1a1a2e">
      <root>
        <mxCell id="0"/><mxCell id="1" parent="0"/>
        <mxCell id="r_title" value="42U Rack Elevation — Rear View (Hot Aisle Side)" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=20;fontStyle=1;fontColor=#ffffff;" vertex="1" parent="1">
          <mxGeometry x="60" y="20" width="500" height="35" as="geometry"/>
        </mxCell>
        <mxCell id="r_note" value="มุมมองจากด้านหลัง — PDU A (ซ้าย / Feed A) | PDU B (ขวา / Feed B) | PSU 1 → Feed A | PSU 2 → Feed B" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=10;fontColor=#aaaaff;" vertex="1" parent="1">
          <mxGeometry x="40" y="56" width="600" height="16" as="geometry"/>
        </mxCell>
        <mxCell id="r_ruler_bg" value="" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#0d0d1a;strokeColor=#333366;" vertex="1" parent="1">
          <mxGeometry x="10" y="75" width="25" height="840" as="geometry"/>
        </mxCell>
        <mxCell id="r_u42" value="42" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="10" y="83" width="25" height="20" as="geometry"/></mxCell>
        <mxCell id="r_u40" value="40" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="10" y="123" width="25" height="20" as="geometry"/></mxCell>
        <mxCell id="r_u35" value="35" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="10" y="223" width="25" height="20" as="geometry"/></mxCell>
        <mxCell id="r_u30" value="30" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="10" y="323" width="25" height="20" as="geometry"/></mxCell>
        <mxCell id="r_u25" value="25" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="10" y="423" width="25" height="20" as="geometry"/></mxCell>
        <mxCell id="r_u20" value="20" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="10" y="523" width="25" height="20" as="geometry"/></mxCell>
        <mxCell id="r_u15" value="15" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="10" y="623" width="25" height="20" as="geometry"/></mxCell>
        <mxCell id="r_u10" value="10" style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="10" y="723" width="25" height="20" as="geometry"/></mxCell>
        <mxCell id="r_u5"  value="5"  style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="10" y="783" width="25" height="20" as="geometry"/></mxCell>
        <mxCell id="r_u1"  value="1"  style="text;html=1;strokeColor=none;fillColor=none;align=center;fontSize=9;fontColor=#888888;" vertex="1" parent="1"><mxGeometry x="10" y="883" width="25" height="20" as="geometry"/></mxCell>

        <mxCell id="r_pduA" value="PDU A&#xa;Feed A&#xa;20A&#xa;IEC&#xa;C13&#xa;×16" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#3a0000;strokeColor=#cc0000;fontColor=#ff8888;fontSize=8;verticalAlign=top;align=center;" vertex="1" parent="1">
          <mxGeometry x="40" y="75" width="22" height="840" as="geometry"/>
        </mxCell>

        <mxCell id="r_rack" value="" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#111122;strokeColor=#4a4a88;strokeWidth=3;" vertex="1" parent="1">
          <mxGeometry x="67" y="75" width="356" height="840" as="geometry"/>
        </mxCell>

        <mxCell id="r_zoneA" value="PSU 1 — Feed A" style="text;html=1;strokeColor=none;fillColor=none;align=left;fontSize=8;fontColor=#cc0000;" vertex="1" parent="1">
          <mxGeometry x="72" y="78" width="160" height="14" as="geometry"/>
        </mxCell>
        <mxCell id="r_zoneB" value="Feed B — PSU 2" style="text;html=1;strokeColor=none;fillColor=none;align=right;fontSize=8;fontColor=#ff6600;" vertex="1" parent="1">
          <mxGeometry x="246" y="78" width="172" height="14" as="geometry"/>
        </mxCell>

        <mxCell id="r_div" value="" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#2a2a44;strokeColor=#444488;" vertex="1" parent="1">
          <mxGeometry x="240" y="85" width="4" height="820" as="geometry"/>
        </mxCell>

        <mxCell id="r_pduB" value="PDU B&#xa;Feed B&#xa;20A&#xa;IEC&#xa;C13&#xa;×16" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#2a1000;strokeColor=#ff6600;fontColor=#ffaa55;fontSize=8;verticalAlign=top;align=center;" vertex="1" parent="1">
          <mxGeometry x="428" y="75" width="22" height="840" as="geometry"/>
        </mxCell>

        <mxCell id="r_cm1" value="Cable Manager 1U — Rear  [U42]" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#555577;fontColor=#888888;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="72" y="85" width="346" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_pp1" value="Patch Panel 24-port CAT6A — Rear (IDC Punch-down)  [U41]" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a2a4a;strokeColor=#4a90d9;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="72" y="105" width="346" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_cm2" value="Cable Manager 1U — Rear  [U40]" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#555577;fontColor=#888888;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="72" y="125" width="346" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_core_A" value="Core Switch  [U38-39]&#xa;PSU 1 → Feed A&#xa;Uplink SFP+ ×4  Stack-A" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#0d2b1a;strokeColor=#cc0000;fontColor=#ffaaaa;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="72" y="145" width="168" height="40" as="geometry"/>
        </mxCell>
        <mxCell id="r_core_B" value="Core Switch  [U38-39]&#xa;PSU 2 → Feed B&#xa;Console  Mgmt  Stack-B" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#0d2b1a;strokeColor=#ff6600;fontColor=#ffcc88;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="244" y="145" width="174" height="40" as="geometry"/>
        </mxCell>

        <mxCell id="r_cm3" value="Cable Manager 1U — Rear  [U37]" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#555577;fontColor=#888888;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="72" y="185" width="346" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_fw1_A" value="FW Primary  [U36]  PSU 1 → Feed A  WAN/LAN ports" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#2d1a0e;strokeColor=#cc0000;fontColor=#ffaaaa;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="72" y="205" width="168" height="20" as="geometry"/>
        </mxCell>
        <mxCell id="r_fw1_B" value="FW Primary  [U36]  PSU 2 → Feed B  HA/Console" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#2d1a0e;strokeColor=#ff6600;fontColor=#ffcc88;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="244" y="205" width="174" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_fw2_A" value="FW Standby  [U35]  PSU 1 → Feed A  WAN/LAN ports" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a0e06;strokeColor=#cc0000;fontColor=#cc8888;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="72" y="225" width="168" height="20" as="geometry"/>
        </mxCell>
        <mxCell id="r_fw2_B" value="FW Standby  [U35]  PSU 2 → Feed B  HA/Console" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a0e06;strokeColor=#ff6600;fontColor=#cc8844;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="244" y="225" width="174" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_cm4" value="Cable Manager 1U — Rear  [U34]" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#555577;fontColor=#888888;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="72" y="245" width="346" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_acc1" value="Access Switch 1  [U33]  —  Uplink SFP+×2  Stack  PSU (Single) → Feed A  (Floor 1)" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a0d2b;strokeColor=#cc0000;fontColor=#ffffff;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="72" y="265" width="346" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_acc2" value="Access Switch 2  [U32]  —  Uplink SFP+×2  Stack  PSU (Single) → Feed A  (Floor 2)" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a0d2b;strokeColor=#cc0000;fontColor=#ffffff;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="72" y="285" width="346" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_acc3" value="Access Switch 3  [U31]  —  Uplink SFP+×2  Console  PSU (Single) → Feed A  (Server Room)" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a0d2b;strokeColor=#cc0000;fontColor=#ffffff;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="72" y="305" width="346" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_cm5" value="Cable Manager 1U — Rear  [U30]" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#555577;fontColor=#888888;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="72" y="325" width="346" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_srv1_A" value="Server 1  [U26-29]&#xa;Dell PowerEdge R750&#xa;PSU 1 — 750W&#xa;→ PDU A  Feed A&#xa;NIC 1/2 (10GbE)" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1e0505;strokeColor=#cc0000;fontColor=#ffaaaa;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="72" y="345" width="168" height="80" as="geometry"/>
        </mxCell>
        <mxCell id="r_srv1_B" value="Server 1  [U26-29]&#xa;Dell PowerEdge R750&#xa;PSU 2 — 750W&#xa;→ PDU B  Feed B&#xa;iDRAC9  PCIe slots" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1e0c00;strokeColor=#ff6600;fontColor=#ffcc88;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="244" y="345" width="174" height="80" as="geometry"/>
        </mxCell>

        <mxCell id="r_srv2_A" value="Server 2  [U22-25]&#xa;Dell PowerEdge R750&#xa;PSU 1 — 750W&#xa;→ PDU A  Feed A&#xa;NIC 1/2 (10GbE)" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1e0505;strokeColor=#cc0000;fontColor=#ffaaaa;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="72" y="425" width="168" height="80" as="geometry"/>
        </mxCell>
        <mxCell id="r_srv2_B" value="Server 2  [U22-25]&#xa;Dell PowerEdge R750&#xa;PSU 2 — 750W&#xa;→ PDU B  Feed B&#xa;iDRAC9  PCIe slots" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1e0c00;strokeColor=#ff6600;fontColor=#ffcc88;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="244" y="425" width="174" height="80" as="geometry"/>
        </mxCell>

        <mxCell id="r_cm6" value="Cable Manager 1U — Rear  [U21]" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#555577;fontColor=#888888;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="72" y="505" width="346" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_stor_A" value="Storage Array  [U17-20]&#xa;Dell MD3820 / PowerVault&#xa;PSU 1 → Feed A&#xa;SAS Host Port 0, 1&#xa;iSCSI Port A0 / A1" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1e1000;strokeColor=#cc0000;fontColor=#ffcc88;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="72" y="525" width="168" height="80" as="geometry"/>
        </mxCell>
        <mxCell id="r_stor_B" value="Storage Array  [U17-20]&#xa;Dell MD3820 / PowerVault&#xa;PSU 2 → Feed B&#xa;SAS Host Port 2, 3&#xa;iSCSI Port B0 / B1" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1e1000;strokeColor=#ff6600;fontColor=#ffcc88;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="244" y="525" width="174" height="80" as="geometry"/>
        </mxCell>

        <mxCell id="r_kvm" value="KVM Switch 1U — Rear  [U16]  —  8x HDMI/USB  PSU (Single) → Feed A" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a1a;strokeColor=#cc0000;fontColor=#aaaaaa;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="72" y="605" width="346" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_bkp" value="Backup Server — Rear  [U15]  —  PSU (Single) → Feed A  NIC 1GbE  iDRAC9" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a0d;strokeColor=#cc0000;fontColor=#ffffff;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="72" y="625" width="346" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_empty1" value="— Empty  [U12-14] —" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#111122;strokeColor=#333344;fontColor=#444466;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="72" y="645" width="346" height="60" as="geometry"/>
        </mxCell>

        <mxCell id="r_oob" value="OOB Mgmt Switch — Rear  [U11]  —  Console ports iDRAC/iLO/IPMI  PSU (Single) → Feed A" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a2a4a;strokeColor=#cc0000;fontColor=#ffffff;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="72" y="705" width="346" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_empty2" value="— Empty  [U8-10] —" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#111122;strokeColor=#333344;fontColor=#444466;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="72" y="725" width="346" height="60" as="geometry"/>
        </mxCell>

        <mxCell id="r_ups" value="UPS — Rear  [U5-7]  APC Smart-UPS 3000VA / Eaton 9PX&#xa;Battery maintenance port  |  Output: IEC C13×6, C19×2  |  Bypass input → PDU A + PDU B" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#2a1a0a;strokeColor=#ff6600;fontColor=#ffffff;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="72" y="785" width="346" height="60" as="geometry"/>
        </mxCell>

        <mxCell id="r_cm7" value="Cable Manager 1U — Rear  [U4]" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#555577;fontColor=#888888;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="72" y="845" width="346" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_cm8" value="Cable Manager 1U — Rear  [U3]" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#555577;fontColor=#888888;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="72" y="865" width="346" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_pdu_ref" value="[U1-2] — Vertical PDU: ดูด้านข้าง Rack (PDU A ซ้าย / Feed A  |  PDU B ขวา / Feed B)" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a0a0a;strokeColor=#cc0000;fontColor=#ff8888;fontSize=9;" vertex="1" parent="1">
          <mxGeometry x="72" y="885" width="346" height="20" as="geometry"/>
        </mxCell>

        <mxCell id="r_hot" value="🔥 HOT AISLE — ลมร้อนออกจากหลัง Rack (Exhaust Air Out)" style="text;html=1;strokeColor=#cc3300;fillColor=#1a0800;rounded=1;align=center;fontSize=11;fontColor=#ff6600;fontStyle=1;" vertex="1" parent="1">
          <mxGeometry x="67" y="920" width="356" height="22" as="geometry"/>
        </mxCell>

        <mxCell id="r_leg_title" value="Legend — Rear View" style="text;html=1;strokeColor=none;fillColor=none;align=left;fontSize=12;fontStyle=1;fontColor=#ffffff;" vertex="1" parent="1">
          <mxGeometry x="460" y="85" width="200" height="20" as="geometry"/>
        </mxCell>
        <mxCell id="r_leg_A" value="PSU 1 — Feed A (PDU A)" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1e0505;strokeColor=#cc0000;fontColor=#ffaaaa;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="460" y="110" width="200" height="22" as="geometry"/>
        </mxCell>
        <mxCell id="r_leg_B" value="PSU 2 — Feed B (PDU B)" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1e0c00;strokeColor=#ff6600;fontColor=#ffcc88;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="460" y="137" width="200" height="22" as="geometry"/>
        </mxCell>
        <mxCell id="r_leg_s" value="Single PSU → Feed A only" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a0d2b;strokeColor=#cc0000;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="460" y="164" width="200" height="22" as="geometry"/>
        </mxCell>
        <mxCell id="r_leg_cm" value="Cable Manager / Tray" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#555577;fontColor=#aaaaaa;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="460" y="191" width="200" height="22" as="geometry"/>
        </mxCell>
        <mxCell id="r_leg_pwr" value="UPS / Power Infrastructure" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#2a1a0a;strokeColor=#ff6600;fontColor=#ffffff;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="460" y="218" width="200" height="22" as="geometry"/>
        </mxCell>
        <mxCell id="r_leg_e" value="Empty / Available" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#111122;strokeColor=#333344;fontColor=#444466;fontSize=10;" vertex="1" parent="1">
          <mxGeometry x="460" y="245" width="200" height="22" as="geometry"/>
        </mxCell>

        <mxCell id="r_sum_title" value="Power Feed Summary" style="text;html=1;strokeColor=none;fillColor=none;align=left;fontSize=12;fontStyle=1;fontColor=#ffffff;" vertex="1" parent="1">
          <mxGeometry x="460" y="295" width="200" height="20" as="geometry"/>
        </mxCell>
        <mxCell id="r_summary" value="PDU A (Feed A)&#xa;→ Server 1 PSU1&#xa;→ Server 2 PSU1&#xa;→ Storage PSU1&#xa;→ Core Sw PSU1&#xa;→ FW Primary PSU1&#xa;→ FW Standby PSU1&#xa;→ Access SW ×3&#xa;→ KVM, OOB, Backup&#xa;&#xa;PDU B (Feed B)&#xa;→ Server 1 PSU2&#xa;→ Server 2 PSU2&#xa;→ Storage PSU2&#xa;→ Core Sw PSU2&#xa;→ FW Primary PSU2&#xa;→ FW Standby PSU2&#xa;&#xa;UPS Output → PDU A + PDU B" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#0d0d1a;strokeColor=#333366;fontColor=#aaaaaa;fontSize=9;align=left;spacingLeft=6;verticalAlign=top;" vertex="1" parent="1">
          <mxGeometry x="460" y="320" width="200" height="270" as="geometry"/>
        </mxCell>

      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

---

## 🌊 Mermaid Template (Quick Reference)

```mermaid
block-beta
  columns 1
  block:rack["42U Rack"]:1
    cm1["U42 — Cable Manager"]
    pp1["U41 — Patch Panel 24-port"]
    cm2["U40 — Cable Manager"]
    core["U38-39 — Core Switch\nCisco 9500 / Dell N3248"]
    cm3["U37 — Cable Manager"]
    fw1["U36 — Firewall Primary\nFortiGate 200F Active"]
    fw2["U35 — Firewall Standby\nFortiGate 200F Passive"]
    acc1["U33 — Access Sw 1  48x PoE+"]
    acc2["U32 — Access Sw 2  48x PoE+"]
    srv1["U26-29 — Server 1\nDell R750 Hyper-V Node1"]
    srv2["U22-25 — Server 2\nDell R750 Hyper-V Node2"]
    stor["U17-20 — Storage Array\nDell MD3820 iSCSI"]
    bkp["U15 — Backup Server"]
    oob["U11 — OOB Mgmt Switch"]
    ups["U5-7 — UPS 3000VA"]
    pdu["U1-2 — PDU 20A"]
  end
```

---

## 💡 Prompt ตัวอย่าง

### แบบ A: สร้าง Rack ใหม่จาก BOM
```
ช่วยหา template rack-elevation-42u.md จาก
github.com/nutbadbot/diagram-templates
แล้วสร้าง rack diagram สำหรับ [ชื่อลูกค้า]:

BOM:
- Firewall: [model] x[จำนวน] ([1U/2U])
- Core Switch: [model] x[จำนวน] ([1U/2U])
- Access Switch: [model] x[จำนวน] ([1U])
- Server: [model] x[จำนวน] ([2U/4U])
- Storage: [model] x[จำนวน] ([2U/4U])
- UPS: [model] x[จำนวน] ([2U/3U])
- Patch Panel: [จำนวน] x 1U
- Cable Manager: ทุก 4U

แสดง U position + legend + summary
```

### แบบ B: As-Built Rack เดิม
```
ช่วยหา template rack-elevation-42u.md จาก
github.com/nutbadbot/diagram-templates
สร้าง as-built rack diagram จากที่ติดตั้งจริง:
- U42-41: [อุปกรณ์]
- U40-39: [อุปกรณ์]
[ระบุทุก U ที่มีอุปกรณ์]
- U ที่ว่าง: [รายการ]
```

### แบบ C: NFI Production Rack
```
ช่วยหา template rack-elevation-42u.md จาก
github.com/nutbadbot/diagram-templates
สร้าง rack diagram สำหรับ NFI:
- Hyper-V Node 1 (NFI-HVC01): Dell R750 4U
- Hyper-V Node 2 (NFI-HVC02): Dell R750 4U
- Storage: Dell MD3820 4U
- Firewall HA pair: 1U x2
- Core Switch: 2U
- Backup Server: 1U
- UPS: 3U
- PDU: 2U vertical
```

### แบบ D: Rear View / Power Feed A-B
```
ช่วยหา template rack-elevation-42u.md Rear View XML จาก
github.com/nutbadbot/diagram-templates
สร้าง Rear View สำหรับ [ชื่อลูกค้า]:

Dual PSU devices (Feed A / Feed B):
- Server 1: [hostname]  PSU1 → [PDU A model], PSU2 → [PDU B model]
- Server 2: [hostname]  PSU1 → [PDU A], PSU2 → [PDU B]
- Storage: [model]  PSU1 → [PDU A], PSU2 → [PDU B]
- Firewall HA: [model]  PSU1 → [PDU A], PSU2 → [PDU B]
- Core Switch: [model]  PSU1 → [PDU A], PSU2 → [PDU B]

Single PSU devices (Feed A only):
- Access SW ×[จำนวน] → Feed A
- OOB Switch, KVM, Backup Server → Feed A

PDU A (Feed A): [ยี่ห้อ/model, 20A หรือ 30A, IEC outlet จำนวน]
PDU B (Feed B): [ยี่ห้อ/model, 20A หรือ 30A, IEC outlet จำนวน]
UPS: [model] → bypass ไปทั้งสอง PDU
```

---

## 🔧 Parameters ที่ปรับได้

| Parameter | Default | ทางเลือก |
|---|---|---|
| Rack size | 42U | 22U, 32U, 47U |
| Server size | 4U (2S) | 1U (dense), 2U, 4U |
| Firewall | 1U per unit | 2U (high-end) |
| UPS | 3U | 2U, 5U |
| View | Front + Rear (XML พร้อมทั้งคู่) | เปิดใช้ทีละ diagram ใน Draw.io |
| Cable color | — | เพิ่ม color code ตาม VLAN |

---

## 📌 Notes สำหรับ SI

- **Cable Manager**: ใส่ทุก 4U เป็น best practice — ป้องกัน cable spaghetti
- **Patch Panel**: วางใกล้ switches เสมอ — ลด cable run
- **UPS**: คำนวณ load จาก nameplate รวม × 0.8 ก่อนเลือก VA
- **PDU**: vertical PDU ประหยัด U แต่ต้องการ side space
- **Cooling**: Front-to-Back airflow — servers หน้า cold aisle, หลัง hot aisle
- **Weight**: server 4U ≈ 25-35 kg, ตรวจ floor load capacity ก่อน
- **Empty U**: เพิ่ม blanking panel ทุก empty U เพื่อ airflow
- **Dual Power Feed A/B**: server/storage/firewall/core switch ต้องมี PSU 1 → PDU A (Feed A) และ PSU 2 → PDU B (Feed B) — ป้องกัน single PDU failure ทำให้ device ดับ
- **Hot Aisle / Cold Aisle**: cold aisle = หน้า rack (cold air intake), hot aisle = หลัง rack (exhaust air out) — Rear View diagram แสดงฝั่ง hot aisle
- **Single PSU devices**: Access switch, KVM, OOB มักมี single PSU — ถ้ามีหลาย unit ในกลุ่มเดียวให้สลับ Feed A/B ระหว่าง device แต่ละตัวเพื่อกระจาย load

### Related Templates
- Network topology → `3-tier-data-center.md`
- Virtualization → `hyper-v-failover-cluster.md`
- Backup → `backup-architecture.md`

**อัพเดตล่าสุด**: 2026-06-27 — เพิ่ม Rear View + dual power feed A/B
