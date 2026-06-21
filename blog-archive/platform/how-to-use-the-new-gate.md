# วิธีการใช้งาน gate.openlandscape.cloud รูปแบบใหม่ บน OpenLandscape Cloud

###### OLS Cloud Tutorial

29/1/2026

---

#### บทความวิธีการใช้งาน gate.openlandscape.cloud รูปแบบใหม่นี้มีหัวข้ออะไรบ้าง

วิธีการสร้าง Instance

วิธีการใส่ Security Group ใน Instance

วิธีการสร้าง Volume, การ Extend Volume และการลบ Volume

วิธีการลบ Instance

วิธีการ Resize Instance

---

# วิธีการใช้งาน gate.openlandscape.cloud

เมื่อผู้ใช้บริการเข้ามาบนหน้าเว็บ gate.openlandscape.cloud จะพบหน้าให้บริการรูปแบบใหม่ โดยมีวิธีการใช้งานดังต่อไปนี้

## 1. วิธีการสร้าง Instance

### 1.1 กด CREATE INSTANCE

ผู้ใช้บริการสามารถกดสร้าง Instance ได้จากปุ่ม "CREATE INSTANCE" จากเมนูที่อยู่ขวามือบน หรือ ปุ่ม "สร้าง INSTANCE" ตรงกลางด้านล่าง

### 1.2 กดสร้าง Instance

เมื่อกด สร้าง Instance จะพบตัวเลือกต่าง ๆ ในการสร้าง Instance ที่มีหัวข้อ ดังต่อไปนี้

- เลือก OS คือ ระบบปฏิบัติการ Linux และ Windows ที่ผู้ใช้บริการต้องการสร้าง

- เลือก Applications คือ ระบบโปรแกรมที่ผู้ใช้บริการต้องการใช้งาน โดยไม่ต้องลงโปรแกรมนั้น สามารถใช้งานได้เลย

- เลือก Server Package จะมีทั้งหมด 2 แบบ คือ

แบบ Pay Per Use
จ่ายตามที่ใช้งานจริง, สร้างและลบได้ตามต้องการ, จำกัดโควต้าการสร้าง
และยืดหยุ่นในการใช้งาน

แบบ Annual Plan
จ่ายครั้งเดียวใช้ได้ตลอดปี, ใช้งานได้อย่างต่อเนื่อง, ไม่จำกัดโควต้าการสร้าง,
ประหยัดค่าใช้จ่ายได้มากขึ้น และพิเศษรับสิทธิ์ใช้งานเพิ่ม ฟรี 1 เดือน ( 12+1 เดือน ) โดยจะมีแจ้งเตือน

*หากคุณเลือกสร้างแพ็กเกจแบบรายปี (Annual Plan) ระบบจะทำการเรียกหักค่าบริการในรูปแบบเงินสดที่เติมเข้ามาในระบบ (Money Credit) เท่านั้น

- เลือก Spec ของ Instance ที่ผู้ใช้บริการต้องการสร้าง โดยมี CPU RAM DISK ให้เลือกตามแถบดังตัวอย่างภาพด้านล่าง

แบบ Starter

เหมาะสำหรับการพัฒนาระดับเริ่มต้น ใช้ทดสอบระบบ การสร้างเว็บไซต์ หรือ แอปพลิเคชันระดับเริ่มต้น

แบบ CPU-Optimized

เหมาะสำหรับการพัฒนาโปรเจกต์ หรือแอปพลิเคชันที่เน้นการประมวลผลข้อมูลระดับสูง รวมถึงการสร้างเว็บที่ต้องการรองรับผู้เข้าใช้งานจำนวนมาก และการทำ Machine Leaning

แบบ Memory-Optimized

เหมาะสำหรับการพัฒนาที่ต้องเน้นใช้งาน Cache ของหน่วยความจำสูงเป็นหลัก ไม่ว่าจะเป็น Database หรือ การประมวลผลข้อมูลขนาดใหญ่ (Big Data) ได้แบบไหลลื่นและมีประสิทธิภาพมากที่สุด

- เลือก Authentication โดยสามารถเลือกได้ 2 วิธี คือ

วิธีที่ 1 เลือกแบบ Password คือ รหัสผ่านสำหรับเข้า SSH Instance จะจัดส่งผ่านทางอีเมลและระบบแจ้งเตือน Notifications สามารถดูรายละเอียดเพิ่มเติมได้ที่

> Link : https://blog.openlandscape.cloud/notification-feature

วิธีที่ 2 เลือก Keypairs คือ Key ที่ใช้ SSH เข้าเครื่อง Linux (ถ้าเลือกระบบ Windows ไม่ต้องเลือกใช้ Keypairs) หรือต้องการใช้โปรแกรม Putty หรือ Mobaxterm  สามารถดูขั้นตอนการใช้งานได้ที่

> Link : https://blog.openlandscape.cloud/ssh-key

- วิธีใส่ Keypair

กด Select/Create ในหัวข้อ Key Pairs หน้าจอจะแสดง Pop-Up ขึ้นมา ให้ผู้ใช้บริการทำการเลือก Key Pair ที่มีอยู่แล้ว หรือทำการสร้างใหม่ แล้วทำการกด Save เป็นการเสร็จสิ้นในขั้นตอนนี้

กรณีที่ผู้ใช้บริการต้องการสร้างใหม่ให้กดที่ Add New Key Pair

ถ้าต้องการ Import ให้กดที่ Import Existing Key Pair

*หมายเหตุ สามารถดูรายละเอียดและวิธีการสร้าง Key Pairs เพิ่มเติมได้ที่
> Link : https://blog.openlandscape.cloud/create-import-keypair

- เลือก Networks คือ วง Internet โดยปกติจะเลือก Default เป็นค่ามาตรฐาน
แต่จะไม่สามารถออก Internet ได้ หากจะใช้งาน Internet ให้ทำการ Enable Private Networks เพื่อ Instance หรือ VM จะได้รับ Public IP และสามารถใช้งาน Internet ได้

- เลือก External IP คือ IP ที่ในการออก Internet
กรณีไม่กดเลือก Enable Public IP จะทำการออก Internet ไปข้างนอกไม่ได้ และไม่ได้ Public IP

- เลือก Select from existing หากผู้ใช้บริการมีการจอง Public IP ภายใน Account ของผู้ใช้บริการสามารถเลือก Public IP นั้นมาสร้างได้

- Attach Volume จะมีทั้ง 2 แบบ คือ
เลือก Server Package แบบ Pay Per use สามารถสร้าง Volume เพิ่มได้จากส่วนนี้และคิดค่า Volume แบบ Pay Per Use ใช้เท่าไหร่จ่ายค่าบริการตามการใช้งานจริงเท่านั้น โดยสามารถดูค่าบริการจาก Summary 
เลือก Server Package แบบ Annual Plan สามารถสร้าง Volume เพิ่มได้จากส่วนนี้และคิดค่า Volume แบบค่าบริการรายปี (Annual Plan) โดยสามารถดูค่าบริการจาก Summary

กรณีไม่ต้องการสร้าง Volume เพิ่ม ไม่ต้องกดเลือกช่องเครื่องหมายถูก Enable Attach Volume

- ตั้ง Hostname คือ ตั้งชื่อของ Instance หรือ VM

### 1.3 ตรวจสอบข้อมูลที่ช่อง Summary

หลังจากที่ผู้ใช้บริการเลือกและกรอกข้อมูลครบถ้วนแล้ว ให้ทำการตรวจสอบข้อมูลอีกครั้งที่ช่อง Summary ระบบจะแสดงรายละเอียดต่าง ๆ ที่ได้มีการสร้าง Instance ไว้ทั้งหมด รวมทั้งราคา เมื่อตรวจสอบเสร็จเรียบร้อยแล้วให้กด ปุ่ม Create Instance เพื่อทำการสร้าง Instance

- ผู้ใช้บริการเลือกสร้าง Instance แบบ Annual Plan
ระบบจะมีเเจ้งข้อกำหนดและเงื่อนไขการชำระค่าบริการแบบ Annual Plan โดยผู้ใช้บริการสามารถอ่านรายละเอียดเงื่อนไขฉบับย่อและฉบับเต็มเพิ่มเติมได้ที่ "Link"

และสามารถอ่านรายละเอียด Price Summary per Year โดยจะบอกรายละเอียดเกี่ยวกับสรุปราคารายปี จาก Package, License Windows และ Volume ที่ผู้ใช้บริการได้เลือก

หากผู้ใช้บริการไม่ต้องการใช้แบบมี Volume และ License Windows จะไม่มีรายละเอียดดังกล่าวแจ้งให้ทราบ เมื่อตรวจสอบรายละเอียดเรียบร้อยแล้ว กดเลือกช่องเครื่องหมายถูกเพื่อยืนยันยอมรับข้อกำหนดและเงื่อนไขการชำระเงินแบบรายปี (Annual Plan) และกด Confirm เพื่อสร้าง Instance แบบ Annual Plan ดังตัวอย่างภาพด้านล่าง

### 1.4 เข้าสู่หน้า Instances

หลังจากทำการสร้างสำเร็จแล้วจะกลับเข้าสู่หน้า Instances แสดงข้อมูล Instances ทั้งหมดที่ทำการสร้างไว้

- ถ้าต้องการสร้าง Instance แบบ Pay Per Use จะอยู่ในแถบ "Pay Per Use"

- สร้าง Instance แบบ Annual Plan ระบบจะแจ้งรายละเอียดอยู่ในแถบ "Annual Plan"
มีวันสร้าง Instance และวันสิ้นสุดในการใช้งาน Instance

### 1.5  รายละเอียด Instance ที่ได้ทำการสร้าง

เมื่อทำการกด Instance เข้ามาจะพบรายละเอียดต่าง ๆ ภายใน Instance ที่ผู้ใช้ทำการสร้างไว้ โดยมีรายละเอียดดังนี้

- สร้าง Instance แบบ Annual Plan จะมีแถบสีฟ้าแสดง Annual Plan

- ชื่อ Instance จะแสดงรายละเอียดที่ผู้ใช้ได้ทำการสร้างไว้ตั้งแต่ตอนต้น
- ปุ่ม Action จะประกอบไปด้วย Edit name, Shut off, Soft reboot, Hard reboot และ Delete ตามลำดับ
- แถบแสดงข้อมูลต่าง ๆ ของ Instance จะประกอบไปด้วย Overview, Resize, Security Group, Volume, History Log, Action Log และ Console

### 1.6 ระบบแจ้งเตือน Notifications

หลังจากสร้าง Instance เสร็จเรียบร้อยแล้ว ระบบแจ้งเตือน Notifications จะแจ้งเตือนว่า Instance สร้างเสร็จเรียบร้อยแล้ว โดยตอนสร้าง Instance ผู้ใช้บริการสามารถดู User และ Password ได้ผ่านทางอีเมลและระบบแจ้งเตือน โดยรายละเอียดดังภาพด้านล่าง

ในส่วนของระบบแจ้งเตือน Notifications หรือ ภาพสัญลักษณ์กระดิ่งจะแจ้งเตือนให้ผู้ใช้บริการทราบว่า ผู้ใช้บริการสร้าง Instance เสร็จเรียบร้อยแล้ว
ผู้ใช้บริการสามารถดูวิธีการใช้งานระบบแจ้งเตือนได้ที่
> Link: https://blog.openlandscape.cloud/notification-feature

### 1.7 รายละเอียดในส่วนของ Network ฝั่ง Public IP

แบบ Annual Plan
ไม่สามารถทำการ Action ได้ เนื่องจากเป็นการ Fix Public IP กับ Instance เรียบร้อยแล้ว

แบบ Pay Per Use

สามารถ Action กับ Public IP ได้ หากผู้ใช้บริการไม่ใช้งานกับ Instance ดังกล่าวแล้ว สามารถ Detach Public IP ไปใช้กับ Instance อื่นได้

ผู้ใช้บริการสามารถดูวิธีการสร้าง Network, IP บน OpenLandscape Cloudได้ที่
> Link: https://blog.openlandscape.cloud/network-ip

---

## 2. วิธีการใส่ Security Group ใน Instance

ผู้ใช้บริการสามารถเลือกคลิกในหัวข้อของ Security Group หน้าจอจะแสดงขึ้นมาให้ผู้ใช้ทำการเลือก Manage Security Group ที่จะทำการใช้เลือกจากทางด้านขวา โดยการกดที่เครื่องหมาย + หลังจากทำการเลือกเสร็จแล้วให้ทำการกด Save เป็นการเสร็จในขั้นตอนนี้

หากผู้ใช้บริการไม่มี Security Group ผู้ใช้บริการสามารถดูวิธีการสร้างได้ที่
> Link: https://blog.openlandscape.cloud/create-security-group

และหากต้องการเพิ่ม Port อื่น ๆ ใน Security Group ผู้ใช้บริการสามารถดูวิธีการเพิ่ม Port ได้ที่

> Link: https://blog.openlandscape.cloud/add-port

---

## 3. วิธีการสร้าง Volume, การ Extend Volume และการลบ Volume

Volume คือ Virtual Hard Disk ทำหน้าที่เป็นที่เก็บข้อมูลของ VM โดยใน VM จะมีที่เก็บข้อมูลอยู่เรียกว่า Root Disk หาก Root Disk เก็บข้อมูลจนเต็มหรือเกือบเต็ม การสร้าง Volume เป็นทางเลือกที่ดี เพื่อช่วยลดข้อมูลที่อยู่ใน Root Disk โดยการย้ายข้อมูลจาก Root Disk ไปยัง Volume ที่ Add เข้ามาตอนที่ผู้ใช้บริการทำการสร้าง Volume โดยวิธีการสร้างมีดังนี้

- ระบบจะแสดงรายละเอียด Volume ที่ทำการ Attach ใน Instance ก่อนหน้านี้ เนื่องจากสร้าง Volume สามารถเลือกได้ตั้งแต่หน้า Create Instance

### 3.1 วิธีการสร้าง Volume

- ให้กดเลือก Volume จากเมนูทางขวา หลังจากนั้นให้ทำการกดไปที่ Create Volume

- กดที่ Create Volume จะได้ Pop-Up ที่แสดงรายละเอียดในการสร้าง Volume ขึ้นมา เมื่อทำการกรอกข้อมูลครบตามที่ผู้ใช้ต้องการสร้าง หรือหากมีการสร้าง Snapshot ไว้แล้ว ให้ทำการเพิ่มที่ช่อง "Create From Snapshot" แล้วทำการกรอกข้อมูลให้ครบ จากนั้นกดที่ Create เป็นการสร้างเสร็จสิ้น

- เมื่อสร้าง Volume เสร็จเรียบร้อยแล้ว ข้อมูล Volume ที่ผู้ใช้บริการทำการสร้างจะแสดงดังภาพด้านล่าง

### 3.2 วิธีการ Extend Volume

วิธีนี้สามารถทำได้ถ้า Volume เป็นแบบ Pay Per Use หากผู้ใช้บริการสร้าง Volume แบบรายปี (Annual Plan) จะไม่สามารถทำการ Extend Volume ได้ ซึ่งผู้ใช้บริการสามารถดูรายละเอียดประเภทของ Volume ได้ที่ Description ดังตัวอย่างภาพด้านล่างจะมีบอกว่าเป็น Volume แบบ Annual Plan

- เลือก Volume ที่ต้องการ Extend Volume และกดเลือก Kebab Menu Icon ที่หัวข้อ  Action

- หาก Status ของ Volume เป็น IN-USE ให้ดำเนินการ Detach เป็นการถอดออกจาก Instance ก่อน ถึงจะ Extend Volume ได้

กรณีไม่ดำเนินการ Detach Volume ออกจะขึ้นแจ้งเตือน ตามดังภาพด้านล่าง

- กดที่ Attach/Detach จะแสดงหน้าต่างดังภาพด้านล่าง แล้วกดที่ DETACH

- Status จะเปลี่ยนจาก IN-USE เป็น AVAILABLE

- เลือกที่ Action แล้วกดที่ Extend Size

- จะแสดงหน้าต่าง Entend Volume ขึ้นมา จากนั้นผู้ใช้บริการสามารถใส่ New Size ของ Volume โดยระบบจะมีแจ้งค่าบริการที่ต้องชำระ ซึ่งการคิดราคาจะเป็นแบบ Pay Per Use เมื่อเสร็จเรียบร้อยแล้วกด Save

- หน้าต่างจะแสดง Size ใหม่เรียบร้อยแล้ว จากนั้นก็เข้าที่ Action > กดที่ Attach/Detach เพื่อนำเข้าสู่ Instance

- ระบบจะแสดงหน้าต่างให้ผู้ใช้บริการเลือก Volume เข้า Instance นั้น เมื่อเลือกเสร็จแล้วกด ATTACH

หลังจากกด ATTACH แล้วจะขึ้นแจ้งเตือน ดังภาพด้านล่าง

- โดยวิธีการสร้าง Volume และวิธี Extend Volume หากทำการ Add Volume เข้า Instance อย่าลืมทำการ Mount Volume
แบบ OS Linux  ผู้ใช้บริการสามารถดูวิธีการสร้างได้ที่
> Link: https://blog.openlandscape.cloud/mount-volume

แบบ OS Windows Server ผู้ใช้บริการสามารถดูวิธีการสร้างได้ที่
> Link: https://blog.openlandscape.cloud/mount-new-volume

### 3.3 วิธีการลบ Volume

วิธีลบ Volume Instance หากผู้ใช้บริการไม่ต้องการใช้งาน Volume Instance มีวิธีดังนี้

- เข้าที่แถบเครื่องมือ Volume เลือก Volume ที่ต้องการลบ ถ้า Status เป็น IN-USE ผู้ใช้บริการต้องดำเนินการ Detach Volume ตัวนั้นออกก่อน โดยเข้าที่ Action > กด Attach/Detach

- ระบบจะแสดงหน้าต่าง Do you want to detach? กดที่ DETACH

เมื่อ Detach เสร็จแล้วจะแสดงข้อความ "Detach Volume สำเร็จ"

- เมื่อ Satus ของ Volume เป็น AVAILABLE แล้วให้เลือกที่ Action > Delete Volume

- ระบบจะแสดงหน้าต่าง Do you want to delete? ดังภาพด้านล่าง หากผู้ใช้บริการต้องการลบให้กดคำว่า "DELETE"

- แบบ Annual Plan ระบบจะแสดงหน้าต่างข้อความ
"คุณต้องการลบ Volume แบบรายปี (Annual Plan) ใช่ หรือ ไม่ ?" ซึ่งจะมีรายละเอียดให้ผู้ใช้บริการได้อ่าน ดังภาพด้านล่าง

เมื่อกด Delete เสร็จแล้วระบบจะแสดงข้อความ "ลบ Volume สำเร็จ"

---

## 4. วิธีการลบ Instance

วิธีลบ Instance กรณีผู้ใช้บริการไม่ต้องการใช้งาน Instance ทั้ง 2 แบบ มีวิธีดังนี้

- ลบ Instance แบบ Pay Per Use
ต้องการลบ Instance ออกจาก Account ของผู้ใช้บริการ ทำได้โดยเข้าที่ปุ่ม Action > Destroy Instance

จากนั้นระบบจะแสดงหน้าต่าง "Do you want to destroy your instance?"
ซึ่งผู้ใช้บริการต้อง Copy Name Instance ใส่ในช่องว่าง จะมีข้อความ
หมายเหตุ: สามารถเลือกที่จะเก็บ Public IP ไว้ได้ โดยระบบจะคิดค่าบริการของ Public IP เพิ่มเติม (125 THB/Month)

- ถ้าผู้ใช้บริการไม่ต้องการเก็บ Public IP ไว้ให้กดเลือกช่องเครื่องหมายถูก และกด "DESTROY"

ระบบจะทำการลบ Instance และแสดงข้อความ "ระบบทำการลบเครื่องของคุณสำเร็จ"

- ลบ Instance แบบ Annual Plan
ต้องการลบ Instance ออกจาก Account ของผู้ใช้บริการ สามารถทำได้โดยคลิกที่สัญลักษณ์  > Destroy Instance

จากนั้นระบบจะแสดงหน้าต่าง "คุณแน่ใจหรือไม่ว่าต้องการลบ Instance แบบรายปี (Annual Plan) นี้ ? "

โดยมีรายละเอียดเเจ้งผู้ใช้บริการ ตามตัวอย่างภาพด้านล่างและสามารถอ่านรายละเอียดและเงื่อนไขฉบับเต็มได้ที่ "Link"  ผู้ใช้บริการสามารถกดยอมรับข้อกำหนดและเงื่อนไข > CONFIRM

ระบบจะแสดงหน้าต่าง "Do you want to destroy your instance?"
ซึ่งผู้ใช้บริการต้อง Copy Name Instance ใส่ในช่องว่าง จะมีข้อความ
หมายเหตุ: สามารถเลือกที่จะเก็บ Public IP ไว้ได้ โดยระบบจะคิดค่าบริการของ Public IP เพิ่มเติม (125 THB/Month) 
– ถ้าผู้ใช้บริการไม่ต้องการเก็บ Public IP ไว้ให้กดเลือกช่องเครื่องหมายถูก และกด "DESTROY"

ระบบจะทำการลบ Instance และขึ้นแจ้งเตือนว่า "ระบบทำการลบเครื่องของคุณสำเร็จ"

---

## 5. วิธีการ Resize Instance

Resize Instance เป็นการปรับขนาดของ CPU, RAM, Disk ในการใช้งานของ Instance

โดย *Resize Instance สามารถปรับเพิ่มได้ แต่ไม่สามารถปรับให้ลดลงได้*

ถ้าผู้ใช้บริการพบว่า Instance ที่กำลังใช้งานอยู่ มีการทำงานที่ช้าลง สามารถทำตามขั้นตอนดังต่อไปนี้

### 5.1 กด Shutoff Instance

ผู้ใช้บริการต้องดำเนินการ Shutoff Instance เป็นอันดับแรกก่อนเสมอ
ทั้งแบบ Pay Per Use

และแบบ Annual Plan

### 5.2 ตรวจสอบ Detail ของ Instance

เมื่อผู้ใช้บริการดำเนินการ Shutoff Instance เรียบร้อยแล้ว ผู้ใช้บริการไปส่วนหน้า Detail ของ Instance ที่ผู้ใช้บริการได้ดำเนินการ Shutoff Instance ไว้

ทั้งแบบ Pay Per Use

และแบบ Annual Plan

### 5.3 ทำการ Resize

จากนั้นให้เลือกไปที่แถบ Resize

เมื่อผู้ใช้บริการเข้ามาที่แถบ Resize เรียบร้อยแล้ว จะพบตัวเลือก 2 ฝั่ง ให้เลือก คือ

(1) ผู้ใช้บริการสามารถเลือก Package ที่ผู้ใช้บริการต้องการปรับจาก Spec เดิม

(2) ผู้ใช้บริการกด Comfirm เพื่อยืนยัน Spec ที่ผู้ใช้บริการต้องการให้เรียบร้อย

- แบบ Annual Plan จะมีรายละเอียดให้ผู้ใช้บริการตรวจสอบข้อกำหนดการใช้งานก่อนกดยืนยันการสร้าง

### 5.4 กด Comfirm

เมื่อผู้ใช้บริการกด Comfirm เรียบร้อยแล้ว กรุณารอ 5-10 นาที เมื่อระบบประมวลผล และดำเนินการตามที่ผู้ใช้บริการเลือกเรียบร้อยแล้ว ผู้ใช้บริการจะได้ Instance ที่มี Spec ตามที่ผู้ใช้บริการเลือกและสามารถใช้งานได้ทันที

- แบบ Pay Per Use

- แบบ Annual Plan

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

ที่มา: [https://blog.openlandscape.cloud/how-to-use-the-new-gate](https://blog.openlandscape.cloud/how-to-use-the-new-gate)
