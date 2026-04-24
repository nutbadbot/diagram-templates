# 🔌 (Advanced) เชื่อม GitHub กับ Claude ด้วย MCP

> สำหรับคนที่อยากให้ Claude เข้าถึง GitHub โดยตรง — ไม่ต้อง manual upload

⚠️ **ต้องมี**: ความรู้ command line พื้นฐาน + Node.js

ถ้าไม่สะดวก — ข้ามเลย! ใช้วิธี manual download/upload ก็เพียงพอสำหรับงานส่วนใหญ่

---

## 🤔 MCP คืออะไร

**MCP (Model Context Protocol)** คือโปรโตคอลที่ทำให้ AI ต่อกับ tool ภายนอกได้ — คล้าย USB แต่สำหรับ AI

เมื่อเชื่อม GitHub MCP แล้ว Claude จะสามารถ:
- ✅ อ่าน repo โดยตรง
- ✅ Create/update files
- ✅ เปิด/ปิด Issues + Pull Requests
- ✅ Search ใน repo
- ✅ Review commits

---

## 📋 Prerequisites

- [ ] Node.js v18+ ([download](https://nodejs.org))
- [ ] Claude Desktop ([download](https://claude.ai/download)) — **ไม่ใช่ web version**
- [ ] GitHub Personal Access Token (PAT)

---

## Step 1: สร้าง GitHub Personal Access Token

### 1.1 ไปที่ GitHub Settings

[github.com/settings/tokens](https://github.com/settings/tokens)

### 1.2 Generate new token (classic)

1. คลิก **Generate new token** → **Generate new token (classic)**
2. Note: ตั้งชื่อ เช่น `Claude MCP Access`
3. Expiration: 90 days (หรือตามความเหมาะสม)

### 1.3 Scopes ที่ต้องเลือก

**สำหรับ repo ส่วนตัว**:
- ✅ `repo` (ทั้งหมด)
- ✅ `read:org` (ถ้าต้องเข้า org)
- ✅ `read:user`

**สำหรับ Pragma org**:
- ตรวจสอบว่า org อนุญาต fine-grained tokens หรือ classic
- บาง org ต้องให้ admin approve token

### 1.4 เก็บ Token

⚠️ **Token จะแสดงครั้งเดียว** — copy ไว้เลย, format: `ghp_xxxxxxxxxx...`

---

## Step 2: ติดตั้ง GitHub MCP Server

### 2.1 วิธี Official (Docker) — แนะนำ

```bash
# Pull image
docker pull ghcr.io/github/github-mcp-server

# Test run
docker run -i --rm \
  -e GITHUB_PERSONAL_ACCESS_TOKEN=ghp_your_token_here \
  ghcr.io/github/github-mcp-server
```

### 2.2 วิธี npm (ถ้าไม่มี Docker)

```bash
npm install -g @modelcontextprotocol/server-github
```

---

## Step 3: Config ใน Claude Desktop

### 3.1 หา config file

**Mac**:
```bash
~/Library/Application Support/Claude/claude_desktop_config.json
```

**Windows**:
```
%APPDATA%\Claude\claude_desktop_config.json
```

**Linux**:
```
~/.config/Claude/claude_desktop_config.json
```

### 3.2 Edit config

ถ้าไฟล์ไม่มี → สร้างใหม่

**สำหรับ Docker**:
```json
{
  "mcpServers": {
    "github": {
      "command": "docker",
      "args": [
        "run",
        "-i",
        "--rm",
        "-e",
        "GITHUB_PERSONAL_ACCESS_TOKEN",
        "ghcr.io/github/github-mcp-server"
      ],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_your_token_here"
      }
    }
  }
}
```

**สำหรับ npm**:
```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-github"
      ],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_your_token_here"
      }
    }
  }
}
```

### 3.3 Restart Claude Desktop

ปิด-เปิด Claude ใหม่

---

## Step 4: ทดสอบ

ใน Claude Desktop (chat ใหม่):

```
ช่วยลิสต์ repos ใน GitHub ของฉันหน่อย
```

ถ้าเห็นไอคอน 🔨 ที่มุมล่าง chat → ติดตั้งสำเร็จ

---

## Step 5: ใช้งานจริง

### ตัวอย่าง: Add template ใหม่

```
ช่วยเพิ่ม template ใหม่ใน repo nutbadbot/diagram-templates
- Path: templates/network-infrastructure/new-template.md
- Content: [paste content]
- Commit message: "Add: new network template"
- Open Pull Request to main
```

### ตัวอย่าง: Review PR

```
มี PR #5 ใน nutbadbot/diagram-templates
ช่วย review ให้หน่อย ดูว่า:
- Template format ถูกต้องมั้ย
- มี XML ที่ valid มั้ย
- Documentation ครบมั้ย
```

### ตัวอย่าง: Search

```
ช่วยหา template ทั้งหมดที่เกี่ยวกับ AWS ใน repo
```

---

## 🛠️ Troubleshooting

### ❌ "MCP server failed to start"

- ตรวจ Node.js version: `node -v` (ต้อง ≥18)
- ตรวจ config JSON syntax ผ่าน [jsonlint.com](https://jsonlint.com)
- ดู logs: Claude Desktop → Settings → Developer → View Logs

### ❌ "Permission denied"

- Token หมดอายุ? สร้างใหม่
- Scopes ไม่ครบ? เพิ่ม `repo`
- Org blocking? ขอ admin approve

### ❌ "Tool not showing up"

- Restart Claude completely (ไม่ใช่แค่ปิดหน้าต่าง)
- ตรวจ config file path ถูกต้อง
- ลอง absolute path แทน `npx`

---

## 🔒 Security Best Practices

1. **ห้าม commit token เข้า git**
2. ใช้ token แยกสำหรับแต่ละ use case
3. ตั้ง expiration ไม่เกิน 90 วัน
4. Scope น้อยที่สุดที่ทำงานได้ (principle of least privilege)
5. Review token usage เป็นระยะที่ [github.com/settings/tokens](https://github.com/settings/tokens)
6. ถ้า token leak → **Revoke ทันที**

---

## 📖 References

- [GitHub MCP Server docs](https://github.com/github/github-mcp-server)
- [Model Context Protocol](https://modelcontextprotocol.io)
- [Claude Desktop](https://claude.ai/download)

---

## 🤷 ถ้า setup ไม่ได้

ไม่เป็นไร! ใช้วิธี manual ก็ได้ผลดี:

1. Claude สร้างเนื้อหาให้
2. Copy-paste ไปใส่ GitHub web
3. หรือ download แล้ว push ด้วย git เอง

Workflow นี้ใช้งานได้ 95% ของ use case อยู่แล้ว 🙂
