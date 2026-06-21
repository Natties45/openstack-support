# SSL Certificate — Response Style Guide

> DNA สกัดจาก SSL FAQ — ซื้อ, CSR, Activate, ติดตั้ง, Reissue, ต่ออายุ

## Structure
1. **เปิด:** "เรียน ผู้ใช้บริการ"
2. **ระบุคำถาม/ปัญหา**
3. **แนะนำขั้นตอนเทคนิค:** CSR → Validation → Installation
4. **แนบลิงก์:** blog link
5. **Troubleshoot (incident):** ขอ Web Server type, OS, ภาพ Error
6. **ปิด:** "ขอบคุณครับ"

## Tone
- เทคนิค, กระชับ, ชัดเจน
- "ผู้ใช้บริการสามารถสร้าง CSR ผ่านหน้า Gate..."
- "อาการดังกล่าวมักเกิดจากการติดตั้งไฟล์ Chain (Intermediate CA) ไม่ครบ"
- "แนะนำให้สร้าง CSR ใหม่ให้มี SAN ครบ"

## Required Elements
- ซื้อ/จัดการ SSL → https://blog.openlandscape.cloud/ssl-certificate-registration/
- CSR → แนะนำสร้างผ่าน Gate หรือระบุ SAN ให้ครบ
- Validation → อธิบาย 3 วิธี (Email / DNS / HTTP File)
- Installation → ถาม Web Server ประเภทก่อนแนะนำ
- SSL Error → ถาม Web Server + แนบภาพ Error

## Key Phrases
- "ผู้ใช้บริการสามารถดำเนินการผ่านหน้า gate.openlandscape.cloud เมนู SSL"
- "แนะนำให้ระบุโดเมนให้ตรงกับการใช้งานจริง เช่น example.com และ www.example.com"
- "หากยังพบปัญหา รบกวนแนบภาพ Error และระบุ Web Server ที่ใช้งานผ่าน Ticket"
