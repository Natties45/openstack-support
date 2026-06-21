# วิธีการสร้าง Network, IP บน gate.openlandscape.cloud

###### OLS Cloud Tutorial

14/3/2023

---

# วิธีการสร้าง Network, IP บน gate.openlandscape.cloud

Network คือ ระบบคอมพิวเตอร์ ที่มีคอมพิวเตอร์เชื่อมต่อกันมากกว่า 1 คอมพิวเตอร์ ซึ่งทำให้ส่งข้อมูลภายในกลุ่มก้อนเดียวกันสะดวกขึ้นซึ่งวิธีการสร้างมีดังนี้

---

1. อันดับแรกให้กดเลือกเมนู Networks จากเมนูทางด้านซ้ายแล้วจะพบหน้าดังรูป จากนั้นมาที่แถบ Private Network คือ ระบบคอมพิวเตอร์ที่มีการเชื่อมต่อกันภายใน โดยใช้ IP Private เพื่อให้ง่ายต่อการควบคุมจะเห็นว่ามี Default ที่เลือกไว้ตอนสร้าง Instances เริ่มแรกจะถูกกำหนดเป็น 192.168.0.0/24 จะได้ทั้งหมด 254 IP ถ้าหากคุณต้องการสร้างเพิ่มให้ทำการกดที่ Create Network

---

2. จากนั้นจะมี Pop-up ขึ้นมา ให้กรอกรายละเอียดตามที่คุณต้องการให้เรียบร้อย ในส่วนของ Network Address นี้ คือ การกำหนด IP Address สำหรับ Network ซึ่งรูปแบบจะเป็น <IP subnet >/<subnet> เมื่อสร้างเสร็จแล้วจะถูกแสดงบนตาราง เมื่อเลือกแล้วให้ทำการ กด Create เป็นเสร็จขั้นตอนนี้

*เงื่อนไขในการ Generate IP ถ้าสร้างทิ้งไว้ ไม่ว่าจะใช้งานหรือไม่ จะมีการคิดค่าใช้จ่าย

---

วิธีการนำไปใช้จะมีในกรณีที่ คุณต้องการให้ Instances มีสอง Private Network หรือต้องการย้าย Instances ไปอยู่อีก Private Network หนึ่ง ซึ่งมีวิธีดังนี้

1. อันดับแรกคุณต้องทำการ Shutoff ก่อน โดยไปที่หน้า Instances กดที่ปุ่มนี้ เลือกที่ Start/Stop Instances

---

2. เมื่อ shutoff เสร็จแล้ว ให้กลับไปที่หน้า Network กดที่ปุ่มตามในรูปภาพ และเลือกที่ Manage Network

3. หลังจากกดแล้วระบบจะแสดงหน้านี้ จะเห็นว่าฝั่งทางซ้ายคือ Instances ที่อยู่ในวง Private Network นี้ ส่วนทางขวาคือ Instances ที่อยู่ภายในวง Private Network อื่น จากนั้นถ้าต้องการให้ Instances นี้ไปอยู่ในวง Private Network เดียวกัน ให้ทำการย้ายไปทางฝั่งซ้าย กด Save เป็นการย้ายเสร็จสิ้น

---

## วิธีการ Generate Public IP เพิ่ม

ต่อไปเป็นส่วนของ Public IP คือ IP address ที่ใช้อยู่บนโลก Internet ซึ่งจะเป็นเลขเฉพาะที่ใช้อยู่บนโลก Internet และ ไม่สามารถซ้ำได้ ซึ่งในการ Generate IP เพิ่มนั้น จะมีในกรณีที่ต้องการเพิ่ม Public IP ในเครื่อง Instances ที่คุณยังไม่ได้เลือก Public IP ในตอนสร้างเครื่องไว้ครั้งแรก ซึ่งก่อนจะทำการ Generate IP คุณต้องทำการ Shutoff ก่อน โดยไปที่หน้า Instances กดที่ปุ่มจุดสามจุด (Kebab) เลือกที่ Start/Stop Instances

เมื่อ Shutoff เสร็จแล้ว ให้กลับไปที่หน้า Network แถบ Public IP จากนั้นกดไปที่ Generate IP

กดเลือก Instances ที่ต้อง Generate Public IP เพิ่ม กด Generate เป็นการเสร็จสิ้นของขั้นตอนนี้

---

## การทำ Detach และ Attach IP Public

Detach IP Public คือ การถอด IP Public ออกจากเครื่อง

Attach IP Public คือ การนำ IP Public ไปติดกับ Instances

การถอด Public IP สามารถทำได้ โดยเข้ามาที่หน้า Network ส่วนของ Public IP แล้วทำการเลือก Public IP ที่ต้องการถอด โดยกดตรง Action จะมี Dropdown List ให้กดที่ Detach Public IP

ส่วนการใส่ Public IP เข้า VM จะมีขั้นตอน คล้าย ๆ กัน โดยกดที่ Attach Instance แล้วทำการ เลือก Instances ที่ต้องการ

หากมีข้อสงสัยหรือต้องการสอบถามข้อมูลเพิ่มเติม สามารถติดต่อ OpenLandscape ได้ผ่านทางอีเมล technical-support@ols.co.th หรือ Call Center 02-257-7189 ได้ตลอด 24 ชั่วโมง

---

### รับชมเป็นรูปแบบวิดีโอได้ที่นี่

### 

---

## 

## ติดตามข่าวสารใหม่ๆ หรือข้อมูลน่ารู้อีกมากมายได้ที่

## OpenLandscape Fanpage | https://www.facebook.com/openlandscapecloud/
  OpenLandscape Twitter | https://www.twitter.com/olscloud/
  OpenLandscape Cloud | https://openlandscape.cloud/

## 

---

---

Share :

---

[Chanakan Budrak](/author/gigi)จบการศึกษาจากคณะมนุษยศาสตร์ มหาวิทยาลัยศรีนครินทรวิโรฒ มีความชื่นชอบและติดข่าวสารวงการเทคโนโลยีใหม่ ๆ อยู่เสมอ ด้วยความที่เทคโนโลยีเป็นเรื่องที่ใกล้ตัวมาก จึงมีความเชื่อว่าแม้จะเป็นคนธรรมดาทั่วไปก็สามารถเรียนรู้เรื่องเทคโนโลยีได้

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

ที่มา: [https://blog.openlandscape.cloud/network-ip](https://blog.openlandscape.cloud/network-ip)
