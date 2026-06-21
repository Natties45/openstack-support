# OLS Support Copilot

> AI-powered customer support reply drafting for OpenLandscape Cloud

## วิธีใช้

1. **Clone repo** ไปวางในเครื่อง staff
```bash
git clone <this-repo>
cd ols-support-agent
```

2. **เปิดด้วย opencode**
```bash
opencode
```

3. **พิมพ์ข้อความจากลูกค้าได้เลย** (dante รับอัตโนมัติ):
```
ลืมรหัสผ่าน Instance แล้ว SSH เข้าไม่ได้ครับ ต้องทำยังไง
```

4. **AI จะร่างคำตอบ** — ตรวจสอบ → กดส่งให้ลูกค้า

5. **ถ้าพอใจคำตอบใหม่** จาก web research → `/vergil` เพื่อบันทึก

## โครงสร้างโปรเจค

```
ols-support-agent/
├── knowledge/          # ฐานความรู้จาก Google Sheet FAQ (9 หมวด)
├── style-guide/        # DNA การตอบแยกตามหมวด (6 styles)
├── blog-index.yaml     # ดัชนีบทความ blog.openlandscape.cloud
├── .opencode/
│   ├── agents/         # dante (ตอบ) + nero (ค้น web) + vergil (บันทึก)
│   ├── skills/         # 10 skills แยกตามหมวด
│   └── commands/       # /dante, /vergil
├── opencode.json       # OpenCode configuration
└── AGENTS.md           # Global rules
```

## หมวดความรู้ (9 Categories)

| หมวด | File | เนื้อหา |
|------|------|--------|
| VM & Instance | vm-instance.yaml | สร้าง/จัดการ/แก้ปัญหา VM |
| Network & Security | network-security.yaml | Port, IP, DNS, Security Group |
| Domain | domain.yaml | จด/ต่ออายุ/DNS/ย้ายโดเมน |
| SSL | ssl.yaml | ซื้อ/CSR/ติดตั้ง/ต่ออายุ SSL |
| Billing & Payment | billing.yaml | เติมเงิน, ภาษี, WHT, ใบกำกับ |
| Account & Gate | account.yaml | สมัคร, Login, โปรไฟล์, Ranking |
| NOC Scripts | noc-scripts.yaml | แม่แบบ Call Center |
| Abuse Handling | abuse.yaml | Brute force, Phishing, Ban |
| Generic Replies | generic.yaml | รับทราบ, แจ้งผล, ติดตาม |

## Style Guide (6 Styles)

| Style | ใช้กับ |
|-------|--------|
| vm-style | VM/Instance ทั่วไป |
| network-style | Network, Port, IP, DNS |
| billing-style | การเงิน, ภาษี, เอกสาร |
| noc-style | NOC/Call Center |
| abuse-style | แจ้งเตือน, ระงับบัญชี |
| generic-style | คำตอบทั่วไป |

## MCP Tools

- **context7** — ค้น tech docs/articles (ติดตั้งแล้ว)
- **webfetch** — built-in ดึงหน้าเว็บ
- **blog.openlandscape.cloud** — ยังติด Cloudflare → แผนภายหลัง

## Self-Learning

- คำถามที่ไม่มีใน knowledge → nero ค้น web → staff approve → `/vergil` บันทึก
- เก็บใน `knowledge/{category}.yaml` พร้อม keywords ภาษาไทย

## นโยบายความปลอดภัย

- ห้ามบันทึกข้อมูลลูกค้า (IP, email, ชื่อ, เบอร์) ใน repo
- ห้าม commit credentials, API keys
- Repo นี้ใช้สำหรับ structure + knowledge เท่านั้น
