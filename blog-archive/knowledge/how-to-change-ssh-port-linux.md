ค่าเริ่มต้นปกติของ SSH Port คือ 22 ซึ่งการเปลี่ยน SSH  Port เป็นอีกวิธีหนึ่งที่ช่วยป้องกันการสุ่ม Hack จากผู้ไม่ประสงค์ดีได้ในระดับหนึ่ง

โดยจะมีขั้นตอนอย่างไรบ้าง OpenLandscape Cloud ได้เรียบเรียงข้อมูลการเปลี่ยน SSH Port บน Linux มาให้คุณได้ทำเองง่าย ๆ ใน 4 ขั้นตอน ดังนี้

---

# ขั้นตอนการเปลี่ยน SSH Port บน Linux

1. คุณสามารถเข้าไปเเก้ไขที่ไฟล์ sshd_config โดยพิมพ์คำสั่ง `vi /etc/ssh/sshd_config`

![SSH Port ภาพประกอบ 1](https://lh6.googleusercontent.com/6bNXOBzL3G0CQjbnlTdNBINNORBcjXXLjs6jShY4RzHGLCWMETG86BtXYzhiN3HadFnX3XSvAC6WPbrbntZMvn9_Uvc9irxnwZ_o_KHvA4fPXga2KsbOVZAixvUcD6rv8A)
<!-- รูปภาพ: ภาพหน้าจอแสดงการใช้คำสั่ง vi /etc/ssh/sshd_config -->

2. เมื่อเข้ามายังไฟล์ Config ให้ทำการกำหนด Port ที่ต้องการ (นำเครื่องหมาย # ข้างหน้าออก) เเละทำการ Save ไฟล์

![SSH Port ภาพประกอบ 2](https://lh4.googleusercontent.com/unDjYeRsZDzoFsZ31fQbuJhFIe-OFFOqcASoos9R5z4Ei1TPBc7Nc62ykSzfAetvRgVmuscozYHCPYsupN_n7ESgR5EAmLfsNsk2ewlNjsDxB1rHKkDZjtbFFAggkB6jEQ)
<!-- รูปภาพ: ภาพหน้าจอแสดงไฟล์ sshd_config ก่อนแก้ไข Port -->

![SSH Port ภาพประกอบ 3](https://lh5.googleusercontent.com/j5AEaHUpiqPxS4nVK1icoAcH-YoIT3LfDiEcPE2nFJl1Jg2d206MKaUSRcNy122DBVMe-4GiIe6Hl-oHnYwu_wtB9PqeJvsXRFb54WbKzNfuUnjxK8EyyeGlrjFOun7IYg)
<!-- รูปภาพ: ภาพหน้าจอแสดงการเปลี่ยนค่า Port ในไฟล์ sshd_config -->

3. จากนั้นทำการ Restart service sshd โดยพิมพ์คำสั่ง systemctl restart sshd

![SSH Port ภาพประกอบ 4](https://lh3.googleusercontent.com/OqG-8BDDhUupuEUxI7rNmiL5uWX9tHf8ouB7vUg4RxJv54QRg04BYH33vRtlETSDEoRX-iGMdh3qbGUTWv8hlSTmzU9VsJRbMYf-EE_B5-taSrUnnEJuZuwrgaiiARG6WQ)
<!-- รูปภาพ: ภาพหน้าจอแสดงการ restart service sshd -->

4.  หากดำเนินการเรียบร้อยเเล้ว ทำการทดสอบ SSH โดยเปลี่ยน Port ตามที่กำหนดไว้ได้เลย (โดยต้องทำการเปิด Port ที่ต้องการใช้งานบนเครื่อง Instance ก่อน)

![SSH Port ภาพประกอบ 5](https://lh6.googleusercontent.com/35qZRxlxKQqNsMht2R4CTw2JJg_g5H21m0nZlJFKJTBfoj7U0xaTuEsZxCm4LSFniogDFs2TloTgIlQgSa8RXCBiSUBlr5wKIcDv5on-nisCwxjingSGoEXka2UOhsKvWQ)
<!-- รูปภาพ: ภาพหน้าจอแสดงการทดสอบ SSH ด้วย Port ใหม่ -->

![SSH Port ภาพประกอบ 6](https://lh6.googleusercontent.com/wZ95JWCuJFu-V5h4dRGoN1JJkLLWRQuPcF1QZ0u6AnXVNzc_ursrDfIFm0EDOyCl9DlrpWi_m4fK-nPBfkW2CbHmcErMWnaHCylWDSzH-I0fZfrRfUy5Ss2T1c7_VWVdgw)
<!-- รูปภาพ: ภาพหน้าจอแสดงการเชื่อมต่อ SSH ด้วย Port ใหม่สำเร็จ -->



---

ที่มา: [https://blog.openlandscape.cloud/how-to-change-ssh-port-linux](https://blog.openlandscape.cloud/how-to-change-ssh-port-linux)