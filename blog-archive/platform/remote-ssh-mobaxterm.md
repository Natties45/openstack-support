# การ SSH เข้าใช้งาน Linux Server ด้วยโปรแกรม MobaXterm

###### OLS Cloud Tutorial

20/5/2021

---

การ SSH เข้าใช้งาน Linux Server ด้วยโปรแกรม MobaXterm ในขั้นตอนของการ SSH เพื่อเข้าใช้งาน Server นั้น โดยปกติเราอาจจะคุ้นเคยกับการใช้โปรแกรมที่ชื่อว่า PuttyGen กันอยู่บ้าง แต่ในบทความนี้เราจะมาแนะนำอีกโปรแกรม ที่ใช้งานได้ดีไม่แพ้กัน นั่นก็คือโปรแกรม "MobaXterm" ข้อดีของการใช้โปรแกรมนี้ในการเข้าใช้งาน Linux Server  (ทั้งๆที่อาจจะมีโปรแกรมอื่นๆให้เราเลือกใช้งานอีกเยอะแยะ) ก็คือ

1. ติดตั้งง่าย
2. มีลูกเล่นในการใช้งาน เช่น Multiple Console, Spile Console
3. ใช้งานง่าย

ขั้นตอนการติดตั้ง

1.สามารถ Downloadโปรแกรม MobaXterm ได้ที่ URL : https://mobaxterm.mobatek.net/download.html

** ความแตกต่างระหว่าง Portable กับ Installer

หากลง Installer จะได้ Local Terminal ซึ่งจะเป็น Console ของเครื่องที่เราติดตั้งนั้นๆ ซึ่งการลงแบบ Portable จะไม่มี Feature นี้

2. หลังจาก Download เสร็จเรียบร้อยแล้ว ให้ทำการติดตั้งโปรแกรม MobaXterm หลังจากนั้นให้เปิดโปรแกรมขึ้นมา จะเห็นเป็นหน้าต่างโปรแกรมขึ้นมาตามภาพด้านล่าง

3. การ SSH เข้า Server จะมี 2 วิธีดังนี้

3.1 การ SSH ผ่าน Tool ของโปรแกรม MobaXterm

- เข้าไปที่ส่วนของ Session เพื่อเริ่มต้นการ Remote เข้า Server

- เลือกเมนู SSH สำหรับ Linux server (แต่ถ้าหากคุณใช้ Window Server  สามารถเลือกเป็นเมนู RDP แทน ก็สามารถใช้ได้เช่นกัน)

กรอกรายละเอียดตาม กรอบสีแดง และกด enable ตามเครื่องหมาย ถูก ตามภาพด้านบน

*** รายละเอียดของ instance สามารถดูได้ผ่านหน้าเว็ป หรือ Email ที่คุณได้รับ

Remote host : IP ของ server หรือ Instance ที่เราจะใช้ Connect ส่วนใหญ่จะเป็น IP Public

Specify username:  ชื่อ User ที่สามารถเข้าใช้งานในที่นี้ จะแสดงใน Email หลังจากที่สร้างเครื่องเรียบร้อยแล้ว

Use private key : การใช้ Key สำหรับเข้าเครื่อง

- เมื่อกรอกรายละเอียดเสร็จเรียบร้อยกด OK

- เย้!! ที่นี้ก็สามารถเข้าใช้งานได้แล้ว

3.2 การ SSH ผ่าน Command Line (For installer Edition)

- เข้าไปที่ Start local terminal จะได้หน้าตาแบบนี้

- การใช้งานจะเหมือนใช้ linux command เลยซึ่ง ถ้าคุ้นเคยก็จะสามาถใช้งานได้ง่ายมาก แต่ถ้าไม่คุ้นเคย ก็ลองทำตามด้านล่างดูก่อนนะครับ

Basic command สำหรับการใช้ Remote linux

cd : change directory  คือ การเปลี่ยน path หรือ directory

ls  : list command คือ การโชว์ file, folder, และ directory

ssh : secure shell  คือ การremote เข้าใช้งาน linux server

---

- ใช้คำสั่ง cd เข้าไปใน Folder หรือ directory ที่มี keypair.pem (.pem คือนามสกุลของไฟล์ keypair)

- เมื่ออยู่ใน Folder ที่มีไฟล์ .pem ให้ใช้คำสั่ง

> ssh -i <keypair.pem> root@<203.xxx.xxx.xxx>

- จะได้ดังนี้หน้าดังนี้ครับ

ถ้าอยากรู้ feature ของตัวนี้เพิ่มเติม แนะนำให้ลองเล่นดูก่อนนะครับ รับรองใช้งานง่ายม๊ากมาก

### แต่ถ้าหากใครยังติดปัญหาในการ SSH อยู่ ลองเข้าไปดูวิธีการแก้ปัญหาที่ http://203.150.107.90/login-ssh-server/ เพื่อลองแก้ไขปัญหานั้นเองได้เลยครับ

### 

### 

## ติดตามข่าวสารใหม่ๆ หรือข้อมูลน่ารู้อีกมากมายได้ที่

## OpenLandscape Fanpage | https://www.facebook.com/openlandscapecloud/   OpenLandscape Twitter | https://www.twitter.com/olscloud/  OpenLandscape Cloud | https://openlandscape.cloud/  OpenLandscape Blog | http://203.150.107.90/

---

Share :

---

[Amornmet Nitatorn](/author/amornmet)จบการศึกษาจาก คณะวิทยาศาสตร์และศิลปศาสตร์ สาขาระบบสารสนเทศมหาวิทยาลัยบูรพา วิทยาเขตจันทบุรี

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

ที่มา: [https://blog.openlandscape.cloud/remote-ssh-mobaxterm](https://blog.openlandscape.cloud/remote-ssh-mobaxterm)
