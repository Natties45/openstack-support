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

## Key Phrases
- "เบื้องต้นแนะนำให้ตรวจสอบว่าได้เปิดพอร์ตที่ใช้งานใน Security Group และกำหนด Source ถูกต้องหรือไม่"
- "รบกวนแนบภาพผล Ping และ Tracert พร้อมระบุพอร์ตที่ใช้งาน และช่วงเวลาที่พบปัญหา"
- "ผู้ใช้บริการสามารถเพิ่ม Rule ใน Security Group..."
