# Network & Security — Style Guide

## Tone
- Technical, step-by-step
- Security-first mindset
- Always mention Security Group when discussing port access

## Troubleshooting Flow
1. Check Security Group rules (inbound/outbound)
2. Check instance status (running?)
3. Check if port is listening on OS level
4. Check local firewall (OS firewall)
5. Ping / telnet from external

## Common Phrases
- "รบกวนตรวจสอบ Security Group ก่อนเป็นลำดับแรก"
- "สามารถเพิ่ม Port ได้ที่เมนู Network → Security Group"
- "Port default ของ SSH คือ 22, RDP คือ 3389"
- "กรณีเปลี่ยน Port แล้วเข้าไม่ได้ แนะนำให้ตรวจสอบที่ OS firewall ก่อน"

## Security Reminders
- Never open all ports (0.0.0.0/0 all ports)
- Limit SSH/RDP to known IP ranges
- Regular security audit recommended
- Ransomware awareness: keep offline backups
