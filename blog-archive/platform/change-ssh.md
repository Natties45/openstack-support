# วิธีการเปลี่ยน SSH เข้า Instance จาก Keypair มาใช้ Password

20/5/2021

---

## วิธีการเปลี่ยน SSH เข้า Instance จาก Keypair มาใช้ Password

แม้การใช้งาน keypair ในการ SSH เข้าเครื่อง Instance นั้นมีความปลอดภัยสูง แต่ก็มีผู้ใช้งานบางท่านอาจชอบใช้งาน SSH โดยใช้ Password เพราะสะดวกสบาย และรวดเร็วมากกว่า ในบทความนี้ผมจะพูดถึงวิธีเปลี่ยนการ SSH จาก Keypair เป็น Password กันนะครับ

---

ทำการ Set Password ของ user : root กันก่อนจะเริ่มนะครับ โดยใช้ Command ตามนี้

```
$ passwd root
```

เมื่อพิมพ์ Command แล้ว ระบบจะให้เราสร้าง "Password"

```
Enter new UNIX password :
Retype new UNIX password :
```

โดยตัวอย่างนี้ผมจะขอสร้าง user ใหม่นะครับ โดยใช้งาน command นี้ครับ

```
$ adduser <username>
```

หลังจากนั้น จะให้เราใส่ Password เหมือนกับตอนเรา Set Password ครับ

และ "Is the information correct? [Y/n] "ให้เราใส่ y ครับ เป็นอันเสร็จการสร้าง user

```
Is the information correct? [Y/n]
```

เพิ่ม username ที่สร้างใหม่เข้า group sudo ครับ

```
$ usermod -aG sudo <username>
```

เสร็จสิ้นขั้นตอนการสร้าง user ครับ ต่อมาจะทำการเปลี่ยนมาใช้ password แทน keypair ครับ

ให้ผู้ใช้งานเข้าไปที่ไฟล์ sshd_config เพื่อแก้ไขไฟล์โดยใช้งาน Command

```
$ vi /etc/ssh/sshd_config
```

และไปที่คำว่า "PubkeyAuthentication" โดยให้เราเปลี่ยนจาก "yes" เป็น "no" จากนั้นให้เรา save และออกจากไฟล์ครับ

และใช้ 2 Command ตามนี้ครับ

```
$ service sshd restart
$ service ssh restart
```

เมื่อดำเนินการตามขั้นตอนเรียบร้อยให้เราทดสอบโดย SSH เข้าใช้งาน Instance โดยไม่ใช้ Keypair ครับ

```
ssh <user>@<IP_Public>
```

> 

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

ที่มา: [https://blog.openlandscape.cloud/change-ssh](https://blog.openlandscape.cloud/change-ssh)
