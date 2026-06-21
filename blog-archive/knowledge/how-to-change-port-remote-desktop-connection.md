การใช้งาน Remote Desktop Connection ที่อยู่บน Windows Server นั้น ซึ่งตามปกติจะต้องทำการเปิด Port ไว้ที่หมายเลข 3389 (RDP) เพื่อให้สามารถ Remote เข้าเครื่องได้

![](https://lh4.googleusercontent.com/Fdv_a6V2S2iCecr4WLgDXg8dGpO2dBaCjPTjy7h1LqHAOQMoIcGKtVdd4S578nlr4hxxWP2vyuisO2uscYB4YE551UPptcl3nQt86QB3MqjdQsB5Mj0tKMjPfOWCSi3MmQ)
<!-- รูปภาพ: ภาพหน้าจอแสดงหน้า Remote Desktop Connection -->

ดังนั้นการใช้ Port ที่เป็นค่าเริ่มต้นนี้ อาจทำให้เซิร์ฟเวอร์มีโอกาสถูกโจมตีด้วยวิธีการสุ่ม Password (Brute-Force Attack) และนำไปสู่การถูกเจาะระบบได้ Openlandscape Cloud จึงอยากแนะนำการเปลี่ยน Port สำหรับใช้งาน Remote Desktop ซึ่งมีขั้นตอนดังนี้

## ขั้นตอนการเปลี่ยน Port สำหรับใช้งาน Remote Desktop

1. ทำการเปิด Run โดยกดปุ่ม Windows + R  ที่คีย์บอร์ด แล้วพิมพ์คำสั่ง regedit จากนั้นกด OK

![](https://lh6.googleusercontent.com/Hhtu-0LfiXz83nNEtoXgfFcKoY9tCme1t0-sKIfqaNIErvC3QpmdWw1dt1LPknUDFEu2cSEB6SJnxUcUpG3mdcwrGUp8cDrVffvrbUV2nokeDwWCYG11sKSNvNetcUOu5Q)
<!-- รูปภาพ: ภาพหน้าจอแสดงการพิมพ์คำสั่ง regedit ในหน้าต่าง Run -->

2. เมื่อเข้ามายังหน้า Registry Editor ให้เลือกที่ HKEY_LOCAL_MACHINE > System > CurrentControlSet > Control > Terminal Server > WinStations > RDP-Tcp

![](https://lh5.googleusercontent.com/cR9D82dD3-YqgcVx6SDbnp348wFQHSL_jqjT7RByk-FOAbeDm5TTpb0FbahAZcPyScFN2ZJARWBKw38r5oep7-DXkhMDz4nzJvsT3anyKTzRsyS1av77lCz1S8uwcx4NAA)
<!-- รูปภาพ: ภาพหน้าจอแสดงการนำทางใน Registry Editor ไปยัง RDP-Tcp -->

3. ที่ช่องทางด้านขวา ให้คลิกขวาที่ PortNumber แล้วเลือก Modify

![](https://lh6.googleusercontent.com/jar4It6k5vGQe8y6vx7DduqdpE2jxHN1sdVrbLy8J1y5I4duzSFSFJDJ9j23b8CjrjhOUrA0sotEodaC0DAt9vEnKLmHyZoTu4DSZ7jof33RlDCGkP9LB4ZBrDxqnCLSlQ)
<!-- รูปภาพ: ภาพหน้าจอแสดงการคลิกขวาที่ PortNumber และเลือก Modify -->

4. จากนั้นให้เลือก Base เป็น Decimal แล้วทำการกำหนด Port ตามที่ต้องการ โดยต้องมี 4 หน่วยและต้องไม่ซ้ำกับ Port อื่นที่มีการใช้งานอยู่ หากเรียบร้อยเเล้วกด OK

![](https://lh5.googleusercontent.com/5bxU9sPI4UG3QAgrtdkBorkf6dEdh0kf4H1DO8WWzoxo0jaeUJYauDGz3muGZG3hi52jhhD0l3O71s87q9uszZMpXJqT5Y1tYWm-ZkSwnZWKuAd8uqtlkcP99kVjQ4WkXA)
<!-- รูปภาพ: ภาพหน้าจอแสดงการเปลี่ยนค่า PortNumber เป็น Decimal และกำหนด Port ใหม่ -->

5. เมื่อเสร็จขั้นตอนการเปลี่ยน Port เรียบร้อยเเล้ว ต้องทำการเปิด Port ที่ส่วนของ Firewall ของเครื่อง เพื่ออนุญาตให้สามารถเชื่อมต่อผ่าน Port ตามที่กำหนดได้

ไปที่ Start > ค้นหา Windows Firewall with Advanced Security > คลิกที่ Windows Firewall with Advanced Security

![](https://lh5.googleusercontent.com/1bgvut4X0esrO8nvzFCp63bu_6D-4e66sQmGX691c8qI8lFLhTErenujy9-vUsQYHsygxiXYzszGkovy7gFMQHr2mx6y_UkrpKx4U13zhyZp_b7GZvjUFkiDbz3iwgOquQ)
<!-- รูปภาพ: ภาพหน้าจอแสดงหน้าต่าง Windows Firewall with Advanced Security -->

6. เลือกที่ Inbound Rules > New Rule…

![](https://lh4.googleusercontent.com/jwP6lUOKOcTSAxjR-D-TpPWm1MKm2zOCWunSsits46j_KBBrO81g6MOp761ruToy8BgFagIrW6WjPhGwdv2mAfcbH0IIwwfZue6OWYUqcQ48DvNTvwB6PuYU-cXvRgUNAA)
<!-- รูปภาพ: ภาพหน้าจอแสดงการเลือก Inbound Rules และ New Rule -->

7. เมื่อเข้ามายังหน้าต่าง New Inbound Rule Wizard เเละเลือกที่ Port จากนั้นกด  Next

![](https://lh6.googleusercontent.com/ziV5RGx7Es0KFaLcO5XpsQS2bvXr1WFKX4NmuqPSV8AbWqQ_hwtBSU6L9wkHyQLZtEwPKdRkU8HfDe5hnW18BfrFrt4xBXgG6HQOHFKSlNW89HfHO1GRao1pMkMgCMEh9Q)
<!-- รูปภาพ: ภาพหน้าจอแสดง New Inbound Rule Wizard เลือก Port -->

8. จากนั้นเลือกที่ TCP เเละเลือก Specific local ports โดยให้ใส่ Port ที่ทำการเปลี่ยนใหม่เเล้วกด Next

![](https://lh3.googleusercontent.com/PRqTEy5mWHlHCfsLwGyB07a05mm8-rdWLSsOh5yndgQmcrO28VJt1nVepz66LvLyx3Y4lCQVj2ikeRve1YrCwkYHcvrXVzM10PcEJfv1Gp3yHNbt-nBFz2DufLY8nZivag)
<!-- รูปภาพ: ภาพหน้าจอแสดงการเลือก TCP และระบุ Port ใหม่ -->

9. เลือก Allow the connection เเละกด Next

![](https://lh6.googleusercontent.com/QQOBGX4_eYYMyEzX0U9AvcWxCBdwtoLRlGfZeKsfbkcs4aGhte9M5DAYZkMbxD-c9hmOox7vKYV5zup_XcvB-RDZx3ZPmhHVDgH0KPuWDpHWSKPsmkcECElLmHvPiS25Xw)
<!-- รูปภาพ: ภาพหน้าจอแสดงการเลือก Allow the connection -->

กด Next

![](https://lh3.googleusercontent.com/j4a3nIUPUPjRqv4MiJLCNmkNJv3o_qLh6A6kjVBC2SojI3pntyMIm5y86H3q_VI0sM7tpAb_dueCziyzdVmCAAM-4fhqQuaFqOUEntZK4pFMWRRwmGk2DGIZ8ga04VeftA)
<!-- รูปภาพ: ภาพหน้าจอแสดงการเลือก Profile สำหรับ Firewall Rule -->

ทำการตั้งชื่อตามที่ต้องการ หากเรียบร้อยเเล้วกด Finish

![](https://lh5.googleusercontent.com/3Z7LnlJux67Jg9ZJxksAkRNrWSIsn2fSDO9Bfeqzu_BPx61fNiZebLxfRZ5fCPb566FA7PvYNgm8cJhHgwmUnHhy-wUxmm2A-wxDw97iQvSUBdsNNNlpTMJMioUegzEz2A)
<!-- รูปภาพ: ภาพหน้าจอแสดงการตั้งชื่อ Rule และกด Finish -->

10. จากตัวอย่างภาพด้านล่าง จะเห็นรายการที่ทำการ Allow Port ไว้เรียบร้อยเเล้ว

![](https://lh4.googleusercontent.com/vWDW1ohREeNES5saIfe8Ntz--gLjjB4ZlW2f_X8B8iNg8BbTWWzt6h__OC-WjelU0_SJiYHf9QVn5XZfmHXiIrThEuqczhrfgH-HiGfGxwTP-KK0AuBEgSX3U1qQe7nJug)
<!-- รูปภาพ: ภาพหน้าจอแสดงรายการ Inbound Rule ที่สร้างไว้เรียบร้อย -->

11. เมื่อทำการ Allow Port เรียบร้อยเเล้ว ให้ดำเนินการปิดหน้าต่างทั้งหมดแล้วทำการ Restart เครื่อง 1 รอบ

12. จากนั้นให้ดำเนินการเปิด Port ที่ต้องการใช้งานบนเครื่อง Instance ก่อน เมื่อเรียบร้อยแล้วสามารถ Remote เข้าใช้งาน โดยใช้  IP Address:port ได้เลย

![](https://lh3.googleusercontent.com/NGHQVTu5Jez7oqOZuoFh7KhDAa6BAd_PxazgFGswedNmTEYi6HoSkE9aZ5df8K5BoSjIvF3ezI3l1aDolJFhNLUJb4rYrJYgHlqPYRRMKupDerdfkqZji33urClh9fo0WA)
<!-- รูปภาพ: ภาพหน้าจอแสดงการ Remote Desktop ด้วย IP Address และ Port ใหม่ -->



---

ที่มา: [https://blog.openlandscape.cloud/how-to-change-port-remote-desktop-connection](https://blog.openlandscape.cloud/how-to-change-port-remote-desktop-connection)