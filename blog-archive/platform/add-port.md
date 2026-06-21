# วิธีการ เพิ่ม Port เข้า Security Group บน gate.openlandscape.cloud

20/9/2022

---

![ภาพปกวิธีการ เพิ่ม Port](/_next/image?url=https%3A%2F%2Fblog-wp.openlandscape.cloud%2Fadd-port%2F%25e0%25b8%25a7%25e0%25b8%25b4%25e0%25b8%2598%25e0%25b8%25b5%25e0%25b8%2581%25e0%25b8%25b2%25e0%25b8%25a3%25e0%25b9%2580%25e0%25b8%259e%25e0%25b8%25b4%25e0%25b9%2588%25e0%25b8%25a1_port_%25e0%25b9%2580%25e0%25b8%2582%25e0%25b9%2589%25e0%25b8%25b2_security_group_%25e0%25b8%259a%25e0%25b8%2599_openlandscape_c%2F&w=3840&q=75)
<!-- รูปภาพ: ภาพปกบทความ วิธีการเพิ่ม Port เข้า Security Group -->

## วิธีการ เพิ่ม Port เข้า Security Group บน gate.openlandscape.cloud

หลังจากการสร้าง Security Group เรียบร้อยแล้ว ผู้ใช้บริการสามารถ เพิ่ม Port เข้าไปใน Security Group ที่สร้างได้ โดยเปิด Port ได้มากกว่า 1 Port ต่อ 1 Security Group หากผู้ใช้บริการมี Security Group อยู่แล้ว สามารถทำการเพิ่ม Port เข้า Security Group เดิมที่มีอยู่ได้ โดยมีขั้นตอนดังนี้

---

1. เมื่ออยู่หน้า Security Group ให้กดปุ่ม Action ของ Security Group ที่ผู้ใช้บริการได้สร้างไว้ตามในรูป โดยมีเมนู Rename, Manage และ Delete (ให้เลือก Manage เพื่อทำการเพิ่ม Port)

---

2. เมื่อเข้าสู่หน้า Manage ผู้ใช้บริการเลือกเมนูที่ปรากฏบนหน้าจอสำหรับการจัดการ Port เมื่อต้องการเพิ่ม Port สามารถกดที่ปุ่ม "+ Add Rule" ที่อยู่ด้านขวาบนเพื่อเพิ่ม Port ที่ต้องการใช้งานได้

---

3. เมื่อกดปุ่ม Add Rule จะพบกับหน้า Add Rule ผู้ใช้บริการสามารถใส่รายละเอียดของ Port ที่ต้องการเพิ่มได้ โดยมีหัวข้อให้เลือกดังต่อไปนี้

- Rule คือ การเลือกประเภทการใช้งาน โดยสามารถเลือกประเภทของ Port ได้ตามต้องการและหากต้องการกำหนดเลข Port เองสามารถเลือก Custom TCP, Custom UDP
- Direction คือ การเลือกประเภทการทำงานโดยแบ่งเป็น Ingress ขารับเข้าข้อมูล, Egress ขาส่งออกข้อมูล
- Open Port คือ การแบ่ง Port โดยให้เลือกใส่ Port เดียว, Port Range ใช้กำหนดระยะที่ทำการเปิด Port, All Ports สำหรับเปิด Port ทั้งหมด (ซึ่งแนะนำให้เปิดใช้เฉพาะ Port ที่จะเป็นเท่านั้น)
- Port Number คือ การกำหนดเลข Port ที่ต้องการใช้
- Remote คือ การให้เลือก CIDR มีไว้สำหรับเจาะจง IP เข้าใช้งาน Instances โดยปกติ ถ้าใช้ 0.0.0.0/0 ทุก IP สามารถเข้าถึงได้ ถ้าต้องการเจาะจง Port และ Allow แค่ 1 IP ที่สามารถเข้าใช้งานได้ ยกตัวอย่างเช่น เลือกประเภทของ Port เป็น SSH และให้ Fix ที่ CIDR Adress เป็นต้น

---

4. เมื่อทำการเพิ่ม Port ใน Security Group เรียบร้อยแล้ว ผู้ใช้บริการสามารถนำ Security Group เพิ่มเข้าไปใน Instance โดยเข้าไปที่หน้า Instance และทำการกดเลือก Instance ที่ผู้ใช้บริการต้องการเพิ่ม Security Group ไว้ใช้งาน

5. หลังจากนั้น ให้ผู้ใช้บริการกดที่แถบ Security Group และกดปุ่ม Manage Security Group เพื่อเพิ่ม Security Group ในการใช้งานเข้าไปใน Instance ที่ผู้ใช้บริการต้องการใช้งาน

---

6. หลังกดปุ่ม Manage Security Group จะมีหน้าให้ผู้ใช้บริการทำการเพิ่ม Security Group เข้าไป โดยทำการกด "+" ตรง Security Group ที่ผู้ใช้บริการต้องการใช้งาน และทำการกด Save

---

หากมีข้อสงสัย หรือต้องการสอบถามข้อมูลเพิ่มเติมสามารถติดต่อ OpenLandscape ผ่านทางอีเมล technical-support@ols.co.th หรือ Call Center 02-257-7189 ได้ตลอด 24 ชั่วโมง

---

Share :

---

[Chanakan Budrak](/author/gigi)จบการศึกษาจากคณะมนุษยศาสตร์ มหาวิทยาลัยศรีนครินทรวิโรฒ มีความชื่นชอบและติดข่าวสารวงการเทคโนโลยีใหม่ ๆ อยู่เสมอ ด้วยความที่เทคโนโลยีเป็นเรื่องที่ใกล้ตัวมาก จึงมีความเชื่อว่าแม้จะเป็นคนธรรมดาทั่วไปก็สามารถเรียนรู้เรื่องเทคโนโลยีได้

##### สมัครใช้บริการของเรา

ให้ทุกการพัฒนาของคุณมีประสิทธิภาพมากกว่าที่เคย

[Get Started](https://openlandscape.cloud?utm_source=blog&utm_medium=getstarted)##### Related posts

---

![อัปเกรดเวอร์ชัน PHP 7.2 เป็น 7.x บน Ubuntu](https://blog-wp.openlandscape.cloud/upgrade-php-ubuntu/02-01/)
<!-- รูปภาพ: ภาพประกอบบทความที่เกี่ยวข้อง: อัปเกรดเวอร์ชัน PHP -->

###### OLS Cloud Tutorial

29/1/2026

อัปเกรดเวอร์ชัน PHP 7.2 เป็น 7.x บน Ubuntu

![PHP คืออะไร ? มาทำความรู้จักภาษาคอมพิวเตอร์ที่ได้รับความนิยมและวิธีติดตั้งบน Ubuntu](https://blog-wp.openlandscape.cloud/php-ubuntu/01-01-2/)
<!-- รูปภาพ: ภาพประกอบบทความที่เกี่ยวข้อง: PHP คืออะไร -->

###### Knowledge Base

29/1/2026

PHP คืออะไร ? มาทำความรู้จักภาษาคอมพิวเตอร์ที่ได้รับความนิยมและวิธีติดตั้งบน Ubuntu

![วิธีการเปลี่ยน Path Directory Owncloud to New Volumes](https://blog-wp.openlandscape.cloud/path-directory-owncloud-to-new-volumes/03-01/)
<!-- รูปภาพ: ภาพประกอบบทความที่เกี่ยวข้อง: วิธีการเปลี่ยน Path Directory -->

###### OLS Cloud Tutorial

29/1/2026

วิธีการเปลี่ยน Path Directory Owncloud to New Volumes



---

ที่มา: [https://blog.openlandscape.cloud/add-port](https://blog.openlandscape.cloud/add-port)
