# วิธีเปลี่ยนการใช้งานจาก SSH Password เป็น Key Pair

###### OLS Cloud Tutorial

20/5/2021

---

## วิธีเปลี่ยนการใช้งานจาก SSH Password เป็น Key Pair

1.ในกรณีที่ทางผู้ใช้บริการสร้าง Instances ของคุณเป็น Password สามารถดำเนินการตามวิธีด้านล่างดังต่อไปนี้

$ ssh-keygen -t rsa

คำสั่งด้านบนเพื่อเป็นการสร้าง Key Pair ขึ้นมา

[ หลังจากใช้คำสั่งสามารถ Enter เพื่อเป็น Default ได้เลย ]

ในส่วนนี้เราจะได้ไฟล์ข้อมูลเพิ่มขึ้นมา 2 ไฟล์ ตามภาพด้านล่าง

ไฟล์ที่เราจะใช้งานในการเข้าเครื่องของเราเองหรือที่เรียกว่า Private Key นั้นจะอยู่ในไฟล์ id_rsa ครับ

ให้เราทำการ เข้าไปในไฟล์ id_rsa ซึ่งจะใช้คำสั้ง

$ nano /root/.ssh/id_rsa

ให้ทำการคัดลอกข้อมูลในไฟล์ดังกล่าวและนำข้อมูลมานั้นใส่ใน notepad เพื่อทำการ save ไฟล์เป็น Type .pem "ตัวอย่างเช่น gate-key.pem"

ใน SSH ได้นั้นจะต้อง copy ข้อมูลในไฟล์ id_rsa.pub ไปไว้ใน authorized_keys ก่อนโดยสามารถใช้คำสั่ง

$ cat id_rsa.pub >> authorized_keys

เป็นการคัดลอกข้อมูลในไฟล์ id_rsa.pub มาใส่ใน authorized_keys

ต่อไปเป็นการปิดการใช้งาน SSH Password โดยการแก้ไขไฟล์

$ nano /etc/ssh/sshd_config

ให้ค้นหาข้อความด้านล่างพร้อมเปลี่ยนค่า yes เป็น no เพื่อปิดการใช้งาน Password ตามตัวอย่างด้านล่างพร้อม save ไฟล์

หลังจากดำเนินการ save ให้ดำเนินการ reload service ตามคำสั่งด้านล่าง

$ systemctl restart ssh

เท่านี้ทางผู้ใช้บริการสามารถใช้งาน SSH ผ่าน Key Pair ได้โดยไม่ต้อง Password ในการ SSH อีกต่อไปเพื่อความปลอดภัยในการใช้งาน

---

Share :

---

[Yaowalak Laddapong](/author/yaowalak)จบการศึกษาจากคณะเทคโนโลยีวิศวกรรมอิเล็กทรอนิกส์ มหาวิทยาลัยเทคโนโลยีพระจอมเกล้าพระนครเหนือ มีความชื่นชอบด้านเทคโนโลยี คือความท้าทายอย่างหนึ่ง หากเราได้แสวงหา ศึกษา ลงมือทำแล้ว ทำให้เราสามารถนำไปพัฒนา ต่อยอดความรู้นั้นได้

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

ที่มา: [https://blog.openlandscape.cloud/ssh-password-to-key-pair](https://blog.openlandscape.cloud/ssh-password-to-key-pair)
