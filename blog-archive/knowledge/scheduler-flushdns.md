# วิธีตั้งค่า Scheduler สำหรับเรียกใช้งาน FlushDNS

31/5/2021

---

สำหรับใครที่กำลังมองหาวิธีตั้งค่า Schedule สำหรับเรียกใช้งาน FlushDNS ทาง OpenLandscape Cloud ได้รวบรวมขั้นตอนการใช้งานมาให้คุณแล้วที่บทความนี้ ถ้าพร้อมแล้วไปดูกันได้เลย

1. ค้นหาโปรเเกรม Notepad จากนั้นคลิกขวา เลือก Ran as Administrator

2. ใส่คำสั่ง ipconfig /flushdns ลงในไฟล์ Notepad

3. ทำการบันทึกไฟล์ เลือก File > Save As เเละตั้งชื่อไฟล์ FlushDNS.bat (สำหรับนามสกุลต้องใช้เป็น .bat ) หลังจากนั้นกดปุ่ม Save

4. เลือกเข้าไปตั้งค่าที่ Task Scheduler เพื่อสั่งให้โปรแกรมทำงานตามเวลาที่ต้องการ โดยคลิกขวาที่ Task Scheduler Library เลือก Create Task

5. เลือกที่แท็บ General ให้ทำการตั้งชื่อและใส่รายละเอียดในช่อง Name และ Description ตามที่ต้องการ

เลือกเป็น Run with highest privileges

เลือก Configure For : เป็นเครื่อง Windows Server ที่ใช้งาน

6. เลือกที่เเท็บ Triggers > New จะมีหน้าต่าง New Trigger ขึ้นมา ให้เลือกตั้งค่าตามช่วงเวลาที่ต้องการให้ทำงาน Drop down ที่ Begin the task เเละเลือก At log on จากนั้นกดปุ่ม OK จะแสดง Trigger ที่ทำการสร้างไว้ขึ้นมา

7. เลือกที่เเท็บ Actions > New จะเเสดงหน้าต่าง New Action ขึ้นมา ในส่วนของ Action จะเลือกเป็น "Start a program" และในส่วนของ Setting > Program/script  คลิกที่ Browse ให้ทำการเลือกไฟล์ Notepad ที่ทำการเขียน Script ไว้ หากเรียบร้อยแล้วให้กดปุ่ม OK

8. ผลลัพธ์ Action ที่ได้ทำการสร้างไว้จะแสดงขึ้นมา หากเรียบร้อยแล้วให้กดปุ่ม OK

9. เมื่อทำการตั้งค่าเรียบร้อยเเล้ว Task ที่สร้างขึ้นใหม่จะแสดงในรายการ Task Schedule ซึ่งแสดงว่าได้ทำการสร้าง Task ไว้แล้ว เมื่อถึงเวลาที่ตั้งค่าไว้ ก็จะทำงานตามคำสั่งที่ทำการเขียนไว้

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

ที่มา: [https://blog.openlandscape.cloud/scheduler-flushdns](https://blog.openlandscape.cloud/scheduler-flushdns)