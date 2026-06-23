# Network & Security — Response Style Guide

> DNA สกัดจาก Network/Port/IP/DNS FAQ

## Structure
1. **เปิด:** "เรียน ผู้ใช้บริการ"
2. **ระบุปัญหา/คำถาม**
3. **แนะนำขั้นตอน:** ชี้ที่เมนูใน Gate → step-by-step
4. **แนบลิงก์:** blog link
5. **Troubleshoot (incident):** ขอ instance name, IP, port, เวลา, ผล Ping/Tracert
6. **ปิด:** "ขอบคุณครับ"

## Tone
- เทคนิค กระชับ ชัดเจน
- "เบื้องต้นแนะนำให้ตรวจสอบ 2 ส่วน..."
- "ผู้ใช้บริการสามารถตั้งค่า Security Group..."
- "รบกวนแนบผล Ping และ Tracert..."

## Required Elements
- ทุก Port question → แนบ https://blog.openlandscape.cloud/add-port/
- ทุก IP question → แนบ https://blog.openlandscape.cloud/network-ip
- Incident → ขอ instance name, public IP, เวลา, port
- DNS question → แนบ https://blog.openlandscape.cloud/scheduler-flushdns

## Variant: Ticket Reply Mode (ในระบบ internal.openlandscape.cloud)

เมื่อตอบใน Ticket (threaded) ให้ปรับรูปแบบดังนี้:

| สถานะ | รูปแบบ |
|---|---|
| **Reply แรก** (ไม่มีประวัติ) | ใช้ "เรียน ผู้ใช้บริการ" + ปิด "ขอบคุณครับ" ได้ |
| **Reply ถัดไป** (ใน thread เดียวกัน) | **ไม่ต้อง** ขึ้น "เรียน ผู้ใช้บริการ" และ **ไม่ต้อง** ปิด "ขอบคุณครับ" — ตอบตรงประเด็น |
| **Reply แจ้ง progress** | ปิดด้วย "ครับ/ค่ะ — หากมีความคืบหน้าจะแจ้งให้ทราบอีกครั้งครับ" |
| **Gender particle** | ใช้ "ครับ" หรือ "ค่ะ" ตามเพศเจ้าหน้าที่ผู้ตอบ |

> หมายเหตุ: ใน Ticket system จะมี Timestamp + Email sender กำกับอยู่แล้ว ไม่ต้องใส่ชื่อตัวเอง

## Key Phrases
- "เบื้องต้นแนะนำให้ตรวจสอบว่าได้เปิดพอร์ตที่ใช้งานใน Security Group และกำหนด Source ถูกต้องหรือไม่"
- "รบกวนแนบภาพผล Ping และ Tracert พร้อมระบุพอร์ตที่ใช้งาน และช่วงเวลาที่พบปัญหา"
- "ผู้ใช้บริการสามารถเพิ่ม Rule ใน Security Group..."
