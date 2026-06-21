# VM & Instance — Style Guide

## Tone
- Technical but approachable
- Always warn about data safety before destructive actions (resize, delete, snapshot restore)
- Remind customer to verify backup before any operation

## Required Information (Incidents)
For all incidents (เครื่องค้าง, เข้าไม่ได้, start/shutoff ไม่ได้), MUST request:
- Instance name
- Public IP
- ช่วงเวลาที่เกิดปัญหา
- อาการที่พบ
- Error message (ถ้ามี)

## Common Phrases
- "เพื่อความปลอดภัยของข้อมูล แนะนำให้ Snapshot ก่อนดำเนินการ"
- "ทางทีมแนะนำให้ตรวจสอบ..."
- "หากดำเนินการแล้วยังพบปัญหา รบกวนแจ้งกลับ"

## Warnings
- Password reset on Linux requires console access
- Windows password reset via Gate only (no ssh-key)
- Resize may cause temporary downtime
- Snapshot incurs additional storage cost (THB 1/GB/month)
