# SSH Key เข้าใช้งาน Linux Server ด้วยโปรแกรม PuTTY

###### OLS Cloud Tutorial

20/5/2021

---

โดยปกติการ SSH แบบ Key Authentication เพื่อเข้าใช้งาน Linux Server
บนระบบปฏิบัติการของ Windows นั้น จะมีขั้นตอนที่แตกต่างจากระบบอื่นๆอยู่พอสมควรค่ะ
ดังนั้นในบทความนี้ …เราจะมาสอนวิธีการเหล่านั้น ให้กับผู้ที่ใช้ Windows กันค่ะ

สิ่งที่ต้องการในการเข้าใช้งาน Linux Server

- โปรแกรม PuTTY  วิธีติดตั้ง PuTTY
- key ที่มีสกุล .ppk  วิธีการแปลงไฟล์ .pem เป็น .ppk

หากมีครบทั้งสองข้อแล้ว ก็สามารถเข้า Linux Server ได้ โดยเริ่มทำตามตามขั้นตอนดังนี้ค่ะ

---

1. เข้าใช้งาน โดยการกรอก IP ของ Linux Server ที่ต้องการจะเชื่อมต่อ Port การใช้งานเป็น 22

2. เลือก Connection Type เป็น SSH

3. เป็นส่วนของการบันทึกค่าที่ตั้งค่าไว้ เพื่อเพิ่มความสะดวกในการเข้าใช้งานครั้งต่อไป จะได้ไม่ต้องกรอกข้อมูลเพื่อทำการเชื่อมต่ออีก

4. คลิกที่ Connection > Data ใส่ Auto-login username เป็น username ในการเข้าใช้งาน Linux Server ที่จะเชื่อมต่อ

หมายเหตุ : User ในการเข้าใช้งานจะส่งไปที่ Email ของผู้ใช้บริการ

5. คลิกที่ Connection > SSH > Auth คลิกปุ่ม Browse เพื่อเลือกไฟล์ Private Key กลับไปหน้าแรก คลิกที่ Session เพื่อตั้งชื่อ Sessions ในส่วนของ Saved Sessions แล้วคลิกปุ่ม Save

6. คลิกปุ่ม Open เพื่อเริ่มการใช้งาน การเข้าใช้งาน Linux Server โดยโปรแกรม Secure Shell (SSH) เป็นครั้งแรก จะแสดงหน้าจอเตือน เกี่ยวกับ Key ที่ใช้ในการ SSH ดังรูป คลิกปุ่ม Yes เพื่อยืนยันความถูกต้อง

7.แสดงหน้าจอ พร้อมการใช้งาน Linux Server

## ติดตามข่าวสารใหม่ๆ หรือข้อมูลน่ารู้อีกมากมายได้ที่

## OpenLandscape Fanpage | https://www.facebook.com/openlandscapecloud/
  OpenLandscape Twitter | https://www.twitter.com/olscloud/
  OpenLandscape Cloud | https://openlandscape.cloud/

---

Share :

---

[premmikach](/author/premmika-ch)The most level of happiness is being able to feel like you are giving back to this world. Happiness :)

##### สมัครใช้บริการของเรา

ให้ทุกการพัฒนาของคุณมีประสิทธิภาพมากกว่าที่เคย

[Get Started](https://openlandscape.cloud?utm_source=blog&utm_medium=getstarted)##### Related posts

---

###### OLS Cloud Tutorial

29/1/2026

อัปเกรดเวอร์ชัน PHP 7.2 เป็น 7.x บน Ubuntu

###### Knowledge Base

29/1/2026

PHP คืออะไร ? มาทำความรู้จักภาษาคอมพิวเตอร์ที่ได้รับความนิยมและวิธีติดตั้งบน Ubuntu

###### OLS Cloud Tutorial

29/1/2026

วิธีการเปลี่ยน Path Directory Owncloud to New Volumes



---

ที่มา: [https://blog.openlandscape.cloud/remote-linux-server-window](https://blog.openlandscape.cloud/remote-linux-server-window)
