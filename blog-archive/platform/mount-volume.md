# มาเพิ่มพื้นที่ Instance ด้วย Mount Volume บน Linux กันเถอะ!

###### FAQ

20/4/2022

---

## มาเพิ่มพื้นที่ Instance ด้วย Mount Volume บน Linux กันเถอะ!

หนึ่งในปัญหาการใช้งาน Instance ส่วนใหญ่ที่เรามักจะพบกัน คือ ปัญหาหน่วยความจำเต็ม หรือ Disk เต็ม ทำให้เราไม่สามารถเก็บข้อมูลเพิ่มได้ หรือ ปัญหา Run Service บาง Service ไม่ได้ แล้วอย่างนี้เราจะทำยังไงเมื่อพื้นที่เต็มละ คำตอบง่าย ๆ ก็คือเราจะต้องเพิ่ม Disk เพื่อให้เพียงพอต่อการใช้งานนั่นเอง แล้วอย่างนี้การเพิ่มพื้นที่ หรือ หน่วยความจำบน Instance กับ คอมพิวเตอร์ ต่างกันหรือไม่ แล้วขั้นตอนมีอะไรบ้าง และถ้า OS ต่างกันมีวิธีต่างกันมั้ย วันนี้เราเลยจะมาอธิบายวิธีเพิ่มพื้นที่ Instance ด้วยการ Mount Volume บน Linux กันค่ะ สำหรับใครที่ต้องการ เพิ่มพื้นที่ Instance ด้วยการ Mount New Volume บน Windows Server 2012 R2 สามารถคลิกเข้าไปอ่านกันได้ค่ะ

---

### การเพิ่มพื้นที่ บน Instance ต่างกับ เพิ่มบนคอมพิวเตอร์หรือไม่

คำตอบก็คือต่างกันค่ะ เพราะว่าบนคอมพิวเตอร์ เวลาที่หน่วยความจำเต็ม หรือ พื้นที่จัดเก็บ เราก็แค่เปลี่ยน หรือ เพิ่มหน่วยความจำ ด้วยการเพิ่ม RAM หรือ Disk ตามขนาดที่เราต้องการได้ จากนั้นตั้งค่าอีกนิดหน่อยเพียงเท่านี้ก็เสร็จเรียบแล้วค่ะ

แต่ !!

สำหรับ Instance นั้นเราจะต้องสร้าง Volume เพิ่ม เพื่อนำไป Mount กับ Instance ที่เราต้องการ แค่นี้การเพิ่มหน่วยความจำเสร็จเรียบร้อยแล้วค่ะ

---

### ขั้นตอนการสร้าง Volume

อันดับแรกให้กด Create Volume ด้านขวาบน เพื่อสร้าง Volume

ใส่ข้อมูลของ Volume ที่เราต้องการ เช่น Name, Size (GB), Attach to (Instance)

หลังจากนั้น คุณจะได้ Volume เพื่อนำมาเชื่อมกับ Instance แต่ยังไม่สามารถใช้งานได้ ดังนั้นเราต้องทำการ Mount Volume ก่อนใน Instance ถึงจะใช้งาน Volume ตัวนั้นได้ค่ะ

---

### ขั้นตอนการ Mount Volume

อันดับแรกให้คุณเปิด Terminal ของ Instance ขึ้นมา

ทำการ Check ว่า Volume ที่สร้างนั้น อยู่ในเครื่อง Instance ยัง โดยใช้ Command : lsblk จะได้ตามตัวอย่าง

ให้คุณทำการแบ่ง Partition โดยใช้ Command : sudo fdisk /dev/vdb ตามตัวอย่าง

จากนั้น ลองใช้ Command : lsblk ดูว่ามีอะไรที่เปลี่ยน

ต่อมา ใช้ Command : mkfs.ext4 /dev/vdc1 เพื่อสร้าง filesystem ของ /dev/vdc1

จากนั้นให้ใช้ Command : mkdir [ชื่อที่จะตั้ง] เพื่อสร้าง Directory ที่ใช้เก็บ Disk

และใช้ Command : mount -t ext4 /dev/vdc1 /[ชื่อ directory ที่สร้างไว้ก่อนหน้านี้] เพื่อผูก Disk ไว้กับ Directory โดยจะเป็นไฟล์ประเภท ext4 และใช้ df -h เพื่อตรวจสอบว่าเราได้ทำการ Mount ไว้ค่ะ

พอถึงจุดนี้ ทุกคนคงคิดว่าทำการ Mount Volume สำเร็จแล้ว แต่จริงๆไม่ใช่ค่ะ เพราะถ้าทำการ Reboot Volume ที่ Mount จะหายไป แต่ก็มีวิธีตั้งค่าให้ Volume ที่ Mount ยังอยู่เมื่อทำการ Reboot แล้ว โดยมีวิธีดังนี้ค่ะ

---

### Config Volume Mount on Linux

อันดับแรกให้ใช้ command $ blkid เพื่อดู UUID ของ Volume ที่ทำการ Mount

ต่อมา ทำการ Copy UUID ของ Volume ที่เราจะทำการ Config

ทำการแก้ไขไฟล์ fstab โดยใช้คำสั่ง $sudo vi /etc/fstab

นำ UUID ที่ได้ copy มาวางไว้ตามตำแหน่ง

เสร็จแล้วทำการ Save แลพทำการ Reboot เครื่อง และตรวจสอบโดยใช้คำสั่ง df -h เพื่อดูว่า Volume ที่ Mount นั้นยังอยู่รึป่าว

## ติดตามข่าวสารใหม่ๆ หรือข้อมูลน่ารู้อีกมากมายได้ที่

## OpenLandscape Fanpage | https://www.facebook.com/openlandscapecloud/
  OpenLandscape Twitter | https://www.twitter.com/olscloud/
  OpenLandscape Cloud | https://openlandscape.cloud/

## 

## 

---

Share :

---

[Chanakan Budrak](/author/gigi)จบการศึกษาจากคณะมนุษยศาสตร์ มหาวิทยาลัยศรีนครินทรวิโรฒ มีความชื่นชอบและติดข่าวสารวงการเทคโนโลยีใหม่ ๆ อยู่เสมอ ด้วยความที่เทคโนโลยีเป็นเรื่องที่ใกล้ตัวมาก จึงมีความเชื่อว่าแม้จะเป็นคนธรรมดาทั่วไปก็สามารถเรียนรู้เรื่องเทคโนโลยีได้

##### สมัครใช้บริการของเรา

ให้ทุกการพัฒนาของคุณมีประสิทธิภาพมากกว่าที่เคย

[Get Started](https://openlandscape.cloud?utm_source=blog&utm_medium=getstarted)##### Related posts

---

###### FAQ

29/1/2026

วิธีการยืนยันตัวตน eKYC บน Openlandscape Cloud

###### FAQ

29/1/2026

การสมัครสมาชิกและเข้าใช้งานระบบ eKYC

###### FAQ

29/1/2026

OLS Package ! ครอบคลุมผู้ใช้ทุกระดับ พร้อมใช้งานแล้ว บน OpenLandscape Cloud



---

ที่มา: [https://blog.openlandscape.cloud/mount-volume](https://blog.openlandscape.cloud/mount-volume)
