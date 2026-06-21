# วิธีการจดทะเบียน SSL Certificate บน gate.openlandscape.cloud

17/8/2022

---

## ทำความรู้จักกับ SSL Certificate

SSL Certificate คือ ใบรับรองความปลอดภัยทางอิเล็กทรอนิกส์ ที่ใช้ในการรับรองมาตรฐาน SSL (Security Socket Layer) เทคโนโลยีความปลอดภัยพื้นฐานที่ช่วยให้การสื่อสาร หรือส่งข้อมูลระหว่างเครื่องเซิร์ฟเวอร์กับเว็บบราวน์เซอร์ แอปพลิเคชันบนเครือข่ายอินเทอร์เน็ต หรือเครือข่ายส่วนตัว

สำหรับ SSL Certificates ของที่เราให้บริการ ออกให้โดย Sectigo หรือที่รู้จักในนามของ Comodo (ชื่อเก่า) ผู้ให้บริการชั้นนำในด้านการรักษาความปลอดภัยออนไลน์ และเป็นผู้ออกใบรับรอง SSL ของธุรกิจที่ผ่านการตรวจสอบระดับสากล

### บทความนี้มีหัวข้ออะไรบ้าง

แพ็กเกจ SSL Certificate ที่เราให้บริการ

วิธีการซื้อ SSL บน gate.openlandscape.cloud

วิธีการ Activate SSL บน gate.openlandscape.cloud

วิธีการ Confirm Activation บน gate.openlandscape.cloud

วิธีการนำไฟล์ Validate ไปไว้ใน Server

วิธีการติดตั้ง SSL Cert ลงบน Server

วิธีการดูรายการ SSL บน gate.openlandscape.cloud

วิธีการดูรายละเอียด SSL บน gate.openlandscape.cloud

วิธีการต่ออายุ SSL บน gate.openlandscape.cloud

วิธีการ Reissue SSL บน gate.openlandscape.cloud

---

## แพ็กเกจ SSL Certificate ที่เราให้บริการ

### Positive Single Domain

ใบรับรองความปลอดภัยทางอิเล็กทรอนิกส์โดเมนเดียว เหมาะสำหรับใช้งานทั่วไป อาทิ บล็อก เว็บไซต์ส่วนตัว หรือเว็บไซต์ทั่วไปที่ไม่ต้องทรานแซคชันในการโหลดข้อมูลจำนวนมาก

– ใบรับรอง (Domain Validation)

– ใช้สำหรับ 1 โดเมน

– เข้ารหัสข้อมูล (Encryption) ได้สูงสุด 256-bit

---

### Positive Multiple Domain

ใบรับรองความปลอดภัยทางอิเล็กทรอนิกส์สำหรับหลายโดเมน เหมาะสำหรับใช้เพิ่มความปลอดภัยให้กับหลายเว็บไซต์ โดยรองรับได้สูงสุดถึง 8 โดเมน ภายในใบรับรองเดียว ยกตัวอย่างเช่น หากคุณมีโดเมน secure.mydomain.com, secure.mydomain.co.uk, และ secure.mydomain.net โดเมนเหล่านี้จะถูกจดภายใต้ใบรับรองเดียวกัน

– ใบรับรอง (Domain Validation)

– ใช้สำหรับ 3 โดเมน

– สามารถซื้อเพิ่มรวมกันได้สูงสุด 8 โดเมน

– เข้ารหัสข้อมูล (Encryption) ได้สูงสุด 256-bit

---

### Positive Wildcard Domain

ใบรับรองความปลอดภัยทางอิเล็กทรอนิกส์สำหรับทุกโดเมนย่อย (Sub Domain) ของ 1 โดเมน ยกตัวอย่างเช่น หากคุณซื้อ PositiveSSL Wildcard SSL Certificate สำหรับโดเมน .yourdomain.com คุณสามารถเพิ่มความปลอดภัยให้กับ www.yourdomain.com, secure.yourdomain.com, mail.yourdomain.com ได้ด้วย เป็นต้น

นอกจากนี้ยังมีบริการ PCI Scanning เพื่อให้สามารถมั่นใจว่าข้อมูลบัตรเครดิตจะไม่รั่วไหล และช่วยลดความเสี่ยงในการเกิดการโจรกรรมอัตลักษณ์และข้อมูลทางการเงิน การชำระเงินโดยทุจริต และการทำรายการโดยไม่ได้รับอนุญาต

– ใบรับรอง (Domain Validation)

– ใช้ได้สำหรับทุกโดเมนย่อยของ 1 โดเมน

– เข้ารหัสข้อมูล (Encryption) ได้สูงสุด 256-bit

---

### Essential Single Domain

ใบรับรองความปลอดภัยทางอิเล็กทรอนิกส์สำหรับธุรกิจออนไลน์ขนาดเล็ก ถึงขนาดกลาง ช่วยเพิ่มความน่าเชื่อถือให้โดเมนของคุณให้มากยิ่งขึ้น ด้วยระดับการประกันที่สูงระดับ Essential SSL Certificate ที่ช่วยเพิ่มประสิทธิภาพ และโอกาสติดอักดับบนหน้า Search Engine

– ใบรับรอง (Domain Validation)

– ใช้สำหรับ 1 โดเมน

– เข้ารหัสข้อมูล (Encryption) ได้สูงสุด 256-bit

---

### Essential Wildcard Domain

ใบรับรองความปลอดภัยทางอิเล็กทรอนิกส์สำหรับธุรกิจออนไลน์ขนาดเล็ก ถึงขนาดกลางที่ต้องการเพิ่มความปลอดภัยให้กับทุกโดเมนย่อยของ 1 โดเมน ด้วยระดับการประกันที่สูงระดับ EssentialSSL Certificate  ยกตัวอย่างเช่น หากคุณมีโดเมน.yourdomain.com โดเมนย่อยอย่าง www.yourdomain.com, secure.yourdomain.com, mail.yourdomain.com  โดเมนเหล่านี้จะถูกจดภายใต้ใบรับรองเดียวกัน

– ใบรับรอง (Domain Validation)

– ใช้ได้สำหรับทุกโดเมนย่อยของ 1 โดเมน

– เข้ารหัสข้อมูล (Encryption) ได้สูงสุด 256-bit

---

## วิธีการซื้อ SSL บน gate.openlandscape.cloud

1. หลังจากเข้าสู่ระบบแล้ว ให้คุณไปที่แถบเมนูด้านข้างแล้วเลือก "SSL" ระบบจะพาคุณเข้าสู่หน้าดังกล่าว

** กรณีที่มี SSL ในระบบแล้วจะมีปุ่ม Create SSL อยู่มุมขวาบน

2. กดปุ่ม  เพื่อทำการสร้าง SSL

3. ระบบจะแสดงหน้าต่างโดยมีรายละเอียดดังต่อไปนี้

3.1. ประเภทของ SSL

3.2. ราคาต่อปี

3.3. รายละเอียดของ SSL แบบย่อ ซึ่งสามารถดูแบบเต็มได้โดยกด Show More

** สามารถกรองประเภทของ SSL และ Domain ที่ต้องการได้จากมุมขวาบน

4. ให้คุณทำการเลือกประเภท SSL ที่ต้องการ จากนั้นกดปุ่ม "Buy Now" เพื่อดำเนินการซื้อ

5. เมื่อเข้ามาแล้วจะพบกับหน้าสรุปข้อมูลการซื้อ SSL ซึ่งประกอบไปด้วย

5.1. Order Detail: รายละเอียดของ SSL

- SSL: ประเภทของ SSL

- Validation Type: ประเภทการตรวจสอบ
- Domain Coverage: ประเภทของ Domain
- Duration (Year): อายุการใช้งานของ SSL

** หากประเภทของ SSL เป็น Positive Mutliple Domain จะมีรายละเอียดเพิ่มเข้ามาดังนี้

- Default Domains: จำนวน Domain เริ่มต้นที่สามารถใช้กับ SSL
- Additional Domain: จำนวน Domain ที่เพิ่มเข้ามา

5.2. Summary: รายละเอียดสรุปค่าใช้จ่ายทั้งหมดในการซื้อ

- Duration (Year): อายุการใช้งานของ SSL
- Total (Baht): จำนวนเงินทั้งหมด

** หากประเภทของ SSL เป็น Positive Mutliple Domain จะมีรายละเอียดเพิ่มเข้ามาดังนี้

- Quantity Additional Domain: จำนวนของ Domain ที่เพิ่มเข้ามา
- Additional Domain Price: ราคาของ Domain ที่เพิ่มเข้า

6. กด Confirm Order ระบบจะนำคุณเข้าสู่หน้า Detail

---

## วิธีการ Activate SSL บน gate.openlandscape.cloud

Activate SSL คือ การเปิดการใช้งาน SSL ของคุณให้สามารถใช้งานได้ โดยจะต้องระบุบ CSR และวิธีการที่จะใช้ในการ Activate

1.ไปที่แถบเมนูด้านข้างแล้วเลือก "SSL" ระบบจะพาคุณเข้าสู่หน้าดังกล่าว

2.ในหน้านี้ระบบจะแสดงรายการที่คุณได้ดำเนินการซื้อ SSL ไว้ ให้คุณเลือก SSL ที่แสดงสถานะ "NEED ACTIVATION"

3.กดที่ปุ่ม Action Menu ()

แล้วเลือก "Activate SSL Certificate"

หรือเลือก "Detail"

แล้วกดที่ปุ่ม "Activate SSL Certificate"

4.ระบบจะแสดงหน้าต่าง Activate SSL Certificate ซึ่งแบ่งเป็น 4 ส่วนดังนี้

4.1. Details: จะแสดงรายละเอียดของ SSL ประกอบด้วย

- SSL ID: แสดงเลขที่ใช้ในการอ้างอิง SSL
- Status: แสดงสถานะของ SSL
- SSL Type: แสดงประเภทของ SSL
- Validation Type: แสดงประเภทการตรวจสอบของ SSL
- Domain Coverage: แสดงประเภทของ Domain
- Created Date: แสดงวันที่สร้าง SSL

4.2. CSR & Contact: Certificate Signing Request ใช้ในการออกใบรับรอง SSL ใหม่

4.3. Domain Name: ข้อมูลของ Domain ที่เกี่ยวข้องกับ SSL ที่ต้องการออกใบรับรอง SSL ใหม่

4.4. Select your service type: เลือกรูปแบบของ Server

4.4.1.หากคุณมี CSR แล้วให้เลือก "Existing CSR" แล้ววาง CSR ในช่องด้านล่าง

แต่ถ้าไม่มี CSR ให้เลือก CSR แล้ว กด "Generate CSR"

4.4.2.เมื่อต้องการสร้าง CSR ใหม่ กดที่ "Generate CSR" จะมีหน้าต่าง Create CSR และมีรายละเอียด คุณสามารถตั้งค่าเพิ่มเติมได้ โดยการเลือก "Show advanced settings"

***หากเป็น Wildcard Domain ต้องเติม *. หน้า Domain Name  ดังตัวอย่าง

***หากเป็น Multiple Domain สามารถกรอก Domain เพิ่มได้ โดยการเลือก "Show advanced settings"

(1).หลังตั้งค่าเรียบร้อยแล้ว ให้คุณกดปุ่ม "CREATE"

(2).ระบบจะทำแสดงหน้าต่างแสดง CSR, Private Key, Certificate และดาวน์โหลดไฟล์ .zip

(3).ปิดหน้าต่างเพื่อดำเนินการกรอกรายละเอียดต่อไป โดยคลิกที่ปุ่ม "I have copied the private key close this window"

4.2.1.หลังจากกรอก CSR เสร็จ ระบบจะทำการเพิ่ม Domain Name ให้อัตโนมัติ

***ถ้าเป็น Mutliple Domain จะต้องกรอก Domain เพิ่ม หากกรอก Domain ในขั้นตอน Create CSR ระบบจะเพิ่ม Domain Name ให้อัตโนมัติ

4.3.1.เลือกรูปแบบ Server ของคุณ

5.กดปุ่ม "NEXT" เพื่อดำเนินการต่อไป

6.หน้าต่างถัดมาจะรายละเอียด แบ่งเป็น 2 ส่วนดังนี้

6.1.Admin Email For Receive SSL Certificate:  Admin Email สำหรับรับข้อมูล Certificate SSL

6.2.Select DCV Method

6.2.1.คุณต้องเลือก "DCV Method" โดยจะมี 2 Method คือ

- HTTP คือ การ Upload File ไปยัง Server เพื่อ Validate
- Email คือ ส่ง Email Validate ไปยัง Email ที่เลือกไว้

หากคุณเลือก Email คุณต้องเลือก "Approval Email"

7.กดปุ่ม "NEXT" เพื่อดำเนินการต่อไป

8.หน้าต่างนี้จะแสดงรายละเอียด ซึ่งแบ่งเป็น 3 ส่วนดังนี้

8.1.Summary Detail: จะแสดงรายละเอียดของ SSL ประกอบด้วย

- SSL ID: แสดงเลขที่ใช้ในการอ้างอิง SSL
- Status: แสดงสถานะของ SSL
- SSL Type: แสดงประเภทของ SSL
- Validation Type: แสดงประเภทการตรวจสอบของ SSL
- Domain Coverage: แสดงประเภทของ Domain
- Created Date: แสดงวันที่สร้าง SSL

8.2.Email Receive SSL: อีเมลสำหรับรับข้อมูล Certificate SSL

8.3.Domains Secured & DCV Method: จะแสดงรายละเอียดต่าง ๆ ประกอบด้วย

- Domain Name (DNS): กรณีที่เลือก Email จะแสดง Email ที่เลือกไว้
- Upload The Validation File To: กรณีที่เลือก HTTP จะแสดง {domain name}/.well-known/pki-validation/

9.เมื่อคุณตรวจรายละเอียดเสร็จ กดปุ่ม "ACTIVATE"

10.ในหน้าต่าง SSL  เมื่อ Activate สำเร็จแล้วจะแสดงสถานะ "NEED CONFIRMATION"

---

## วิธีการ Confirm Activation บน gate.openlandscape.cloud

Confirm Activate คือ การยืนยันขั้นตอนการ Activate ว่าได้ทำตามขั้นตอนเรียบร้อยแล้ว เพื่อให้ดำเนินการตรวจสอบ

1.ไปที่แถบเมนูด้านข้างแล้วเลือก "SSL" ระบบจะพาคุณเข้าสู่หน้าดังกล่าว

2.ในหน้านี้ระบบจะแสดงรายการที่คุณได้ดำเนินการซื้อ SSL ไว้ ให้คุณเลือก SSL ที่แสดงสถานะ "NEED CONFIRMATION"

3.กดที่ปุ่ม Kebab Menu () แล้วเลือก "Detail"

4.ระบบจะแสดงรายละเอียดของ SSL ซึ่งแบ่งเป็น 2 ส่วนดังนี้

4.1. Domain: จะแสดงชื่อโดเมนที่ต้องการจดทะเบียน SSL

4.2. Details: จะแสดงรายละเอียดของ SSL ประกอบด้วย

- SSL ID: แสดงเลขที่ใช้ในการอ้างอิง SSL
- Status: แสดงสถานะของ SSL
- SSL Type: แสดงประเภทของ SSL
- Validation Type: แสดงประเภทการตรวจสอบของ SSL
- Domain Coverage: แสดงประเภทของ Domain
- Date Created: แสดงวันที่สร้าง SSL
- Email Receive SSL: อีเมลสำหรับรับข้อมูล Certificate SSL
- CSR Code: CSR
- ปุ่ม Edit Activation Type: ปุ่มสำหรับการแก้ไข DCV Method

5. กดที่ปุ่ม ()

***หากเลือก DCV Method เป็น HTTP ต้อง Download File ก่อนจึงจะ Confirm Activation ได้ โดยเลือก "Download File" แล้วกดปุ่ม "Download"

เมื่อ Download เสร็จกดปุ่ม DONE

***หากเลือก DCV Method เป็น Email ให้เลือก "Confirm Activation"

5. ระบบจะทำแสดงหน้าต่าง Confirm Activation กดปุ่ม "CONFIRM"

***การกด Confirm Activate ควรกดเมื่อทำการอัพโหลดไฟล์ หรือยืนยัน Email เรียบร้อยแล้ว เนื่องจากการกด Confirm จะไม่สามารถเปลี่ยน วิธีการ Validate ได้อีกแล้ว

6.ในหน้าต่าง SSL เมื่อ Confirm Activation แล้วจะแสดงสถานะ "PENDING"

---

## วิธีการนำไฟล์ Validate ไปไว้ใน Server

กรณีเลือก DCV Method เป็น HTTP ในขั้นตอน Activate SSL ต้องทำการ Download File ในขั้นตอน Confirm Activation แล้วค่อยกลับไปกด Confirm

ในกรณีนี้ จะสาธิตวิธีการติดตั้งไฟล์เพื่อ Validate Domain ลงบน Nginx Server

หลังจากที่ทำการ Download File สำเร็จแล้ว จะต้องนำไฟล์ไปไว้ ที่ ๆ สามารถเข้าถึงได้โดย

{your_domain}/.well-known/pki-validation/{file_name}

ยกตัวอย่างการนำไฟล์ไปวางไว้ บน Nginx Server ใน OS Ubuntu

- ขั้นตอนแรก SSH เข้าสู่ Server ที่ต้องการทำ File ไปวางไว้ โดย Server ที่ใช้จะต้องเข้าถึงผ่าน Domain ของคุณได้ และทำการติดตั้ง Apache / Nginx สำหรับ Webserver (สามารถดูวิธีติดตั้ง Apache ได้ที่ วิธีติดตั้ง WordPress ด้วยเซอร์วิส LAMP บน Ubuntu 16.04 ขั้นตอนที่ 1)

- หลังจากทำการติดตั้งเรียบร้อยแล้ว ใช้คำสั่ง

```
# cd /var/www/html
```

- ทำการสร้าง Directory .well-known  และ Pki-validation ที่อยู่ใน .well-known โดย และ Change directory เข้าใน Directory ที่สร้าง ใช้คำสั่ง

```
# mkdir .well-known
# mkdir .well-known/pki-validation
# cd .well-known/pki-validation
```

- สร้างไฟล์ ตามชื่อไฟล์ที่ Download มา

```
# touch FFB251EA02D60DFFE18478AE66EA0C0A.txt
```

- ใส่เนื้อหาใน ไฟล์ที่ Download มาลงในไฟล์ที่พึ่งทำการสร้าง

```
# echo "{เนื้อหาในไฟล์ที่ download มา}" > FFB251EA02D60DFFE18478AE66EA0C0A.txt
```

- ตรวจสอบการเข้าถึงไฟล์ว่า สามารถทำได้โดยใช้ Web browser {your_domain}/.well-known/pki-validation/{file_name}

หลังจากตรวจสอบแล้วว่า สามารถเข้าถึงไฟล์ได้ ให้ทำการกด Confirm Activate ในหน้า Detail

---

## วิธีการติดตั้ง SSL Cert ลงบน Server

ในกรณีนี้ จะสาธิตวิธีการติดตั้ง SSL Cert ลงบน Nginx Server

1. เข้าไปที่หน้า SSL และคลิก Action Detail ของ SSL ที่ต้องการ

2.ดาวน์โหลด ไฟล์ SSL Cert จากหน้าเว็บ Gate โดยคลิกที่ปุ่ม

3.จะได้ SSL Cert ดังภาพ ซึ่งจะได้รับ 2 ไฟล์ด้วยกัน คือ Cert ของ Domain  และ ไฟล์ CA Bundle

4.ดำเนินการรวมไฟล์ Cert และ ไฟล์ CA Bundle ให้เป็นไฟล์เดียว โดยใช้คำสั่ง

```
# cat <file cert domain> <file CA bundle> > <new file>
```

5.ทำการคัดลอกไฟล์ Key ที่ได้จากการ Generate CSR และ ไฟล์ SSL Cert จากข้อที่ (4) มาไว้ใน Nginx Server โดยใช้คำสั่ง

```
scp <file_to_copy> <username>@<ip_address>:<path>
```

6. สร้างโฟลเดอร์ SSL ใน path: /etc/nginx/

7.นำไฟล์ทั้งสองไปวางไว้ที่ path: /etc/nginx/ssl/

8.แก้ไขไฟล์คอนฟิคของ Nginx โดย ใช้คำสั่ง

```
# vi /etc/nginx/sites-available/default
```

9.ดำเนินการ Comment Config ของ Port 80 ที่ไม่ได้ใช้ (1) และใส่ Config (2) สำหรับ SSL ดังนี้

10.ดำเนินการ Save File และ Restart Service Nginx ด้วยคำสั่ง

```
# service nginx restart
```

11.เว็บไซต์ที่ติดตั้ง SSL Cert เรียบร้อยแล้ว จะมีไอคอนรูป  ที่ Domain Name หากคลิกที่ไอคอนดังกล่าวระบบจะแสดงรายการดังภาพ

---

## วิธีการดูรายการ SSL บน gate.openlandscape.cloud

หลังจากเข้าสู่ระบบแล้ว ให้คุณไปที่แถบเมนูด้านข้างแล้วเลือก "SSL" ระบบจะพาคุณเข้าสู่หน้าดังกล่าว

ส่วนประกอบของหน้ารายการ SSL มีดังนี้

1. ปุ่ม Create SSL คือ ปุ่มที่จะทำนำไปสู่หน้าการเลือกซื้อประเภท SSL
2. ID แสดงหมายเลขอ้างอิงของ SSL
3. Domain Name แสดงชื่อของ Domain ที่จดทะเบียนกับ SSL
4. SSL Type แสดงประเภทของ SSL
5. Purchase Date แสดงวันที่ทำการซื้อ SSL
6. Expiraton Date แสดงวันหมดอายุของ SSL นั้น (จะแสดงเมื่อ SSL มีสถานะ Active แล้วเท่านั้น)
7. Status แสดงสถานะ SSL โดยมีสถานะดังนี้

- Active : SSL พร้อมใช้งาน
- Needs Activation : SSL ทำการซื้อสำเร็จแล้ว แต่ยังไม่ได้ทำการ Activate
- Needs Confirmation : สถานะที่แสดงว่าคุณได้ทำการ Activate SSL แล้วแต่ยังไม่ได้ทำการ Confirm Active SSL
- Pending : สถานะที่แสดงว่าคุณได้ทำการ Confirm Active SSL แล้ว แต่ SSL ยังอยู่ระหว่างกระบวนการ Active SSL ตาม DCV method ที่คุณได้ทำการเลือกไว้
- Expried : สถานะที่แสดงว่า SSL ของคุณนั้นหมดอายุแล้ว

** หากหมดอายุเกิน 180 วันแล้ว จะไม่แสดงในระบบ

1. Action แสดงรายการที่สามารถกระทำได้กับ SSL ที่สถานะต่าง ๆ ดังนี้

- สถานะ Active : 
Detail : Action แสดงรายละเอียดของ SSL
Renew : Action การต่ออายุ SSL (จะแสดงในกรณีอีก 90 วันก่อนที่ SSL จะหมดอายุ) 
Reissue : Action การสร้างใบรับรองของ SSL ใหม่
Download : Action การ Download SSL Certificate
- สถานะ Needs Activation
Detail : Action แสดงรายละเอียดของ SSL
Activate SSL Certificate : Action การ Activate SSL
- สถานะ Needs Confirmation
Detail : Action แสดงรายละเอียดของ SSL
- สถานะ Pending
Detail : Action แสดงรายละเอียดของ SSL
- สถานะ Expired
Detail : Action แสดงรายละเอียดของ SSL
Renew : Action การต่ออายุ SSL

---

## วิธีการดูรายละเอียด SSL บน gate.openlandscape.cloud

1. หลังจากเข้าสู่ระบบแล้ว ให้คุณไปที่แถบเมนูด้านข้างแล้วเลือก "SSL" ระบบจะพาคุณเข้าสู่หน้าดังกล่าว

2. กดปุ่ม Action Manu ( ) ที่อยู่ทางขวาสุดของ SSL ที่ต้องการดูรายละเอียด

เลือก Detail

3. ระบบจะแสดงรายละเอียดของ SSL ซึ่งแบ่งเป็น 2 ส่วนดังนี้

3.1. Domain: จะแสดงชื่อโดเมนที่ต้องการจดทะเบียน SSL ประกอบด้วย

- Domain Name: แสดงชื่อของโดเมน

** Domain Name จะแสดงรายละเอียดกรณีที่ทำการ Activate แล้วเท่านั้น

** ถ้ามี (Primary Domain) จะเป็น Domain หลัก

** กรณีที่เป็น SSL ประเภท Positive Multiple Domain  ถ้าไม่มี  (Primary Domain) ตามหลังชื่อ Domain จะเป็นโดเมนรอง

3.2. Details: จะแสดงรายละเอียดของ SSL ประกอบด้วย

- SSL ID: แสดงเลขที่ใช้ในการอ้างอิง SSL
- Status: แสดงสถานะของ SSL
- SSL Type: แสดงประเภทของ SSL
- Validation Type: แสดงประเภทการตรวจสอบของ SSL
- Domain Coverage: แสดงประเภทของ Domain
- Date Created: แสดงวันที่ทำการซื้อ SSL
- ปุ่ม Activate SSL Certificate: สำหรับทำการ Activate SSL จะเเสดงในกรณีที่ Status เป็น Needs Activation เท่านั้น

** หากทำการ Activate SSL แล้วจะแสดงรายละเอียดเพิ่มเติมคือ

- Email Receive SSL: อีเมลสำหรับรับข้อมูล Certificate SSL
- CSR Code: CSR
- ปุ่ม Edit Activation Type: ปุ่มสำหรับการแก้ไข DCV Method

** หากทำการ Confirm Activation สำเร็จแล้ว SSL มีสถานะ Active จะแสดงรายละเอียดและสัญลักษณ์เพิ่มเติมคือ

- Expiration Date: วันที่ SSL หมดอายุ

- : สัญลักษณ์สำหรับ Reissue เป็นการสร้างใบรับรองของ SSL ที่ถูกใช้อยู่ใหม่
- : สัญลักษณ์สำหรับ Download Certificate
- : สัญลักษณ์สำหรับ Renew เป็นการต่อวันหมดอายุของ SSL (จะแสดงในกรณี SSL จะหมดอายุในอีก 90 วันและหลังจากหมดอายุ 180 วัน )

---

## วิธีการต่ออายุ SSL บน gate.openlandscape.cloud

การต่ออายุ SSL คือการขยายระยะเวลาหมดอายุของ SSL ที่ถูกใช้อยู่ออกไป

เงื่อนไขในการต่ออายุของ SSL มีดังนี้

- SSL ที่ต้องการต่ออายุจะต้องถูกเปิดใช้งานแล้ว โดยมีการแสดงผลสถานะเป็น Active

- SSL ที่ต้องการต่ออายุสามารถทำการต่ออายุได้ในระยะเวลานับตั้งแต่ก่อน SSL หมดอายุ 90 วัน และ หลัง SSL หมดอายุไปแล้ว 180 วัน เท่านั้น
- SSL ที่ต้องการต่ออายุได้หมดอายุไปแล้วมีสถานะเป็น Expired สามารถทำการต่ออายุได้ภายใน 180 วันนับจากวันหมดอายุ

1. หลังจากเช้าสู่ระบบแล้ว ที่แถบเมนูด้านข้างเลือกตัวเลือก "SSL" ระบบจะเข้าสู่หน้าดังกล่าว

2. กดปุ่ม Action Menu () ของ SSL ที่ต้องการต่ออายุ

3. เลือก Renew จาก Action Menu

การเลือก Renew สามารถเลือกจากหน้า Detail ได้เช่นกัน

4. เมื่อเข้าสู่หน้า Renewal จะพบกับข้อมูล 3 ส่วนประกอบด้วย

4.1.Domain: ข้อมูลของ Domain ที่เกี่ยวข้องกับ SSL ที่ต้องการต่ออายุ

- Domain Name: แสดงชื่อของโดเมน

** Domain Name จะแสดงรายละเอียดกรณีที่ทำการ  Activate แล้วเท่านั้น

** ถ้ามี Domain ที่มี  (Primary Domain) จะเป็น Domain หลัก

** กรณีที่เป็น SSL ประเภท Positive Multiple Domain โดย Domain ที่ไม่มี  (Primary Domain) ตามหลังจะเป็นโดเมนรอง

4.2. Details: รายละเอียดข้อมูลของ SSL ที่ต้องการต่ออายุ

- SSL ID: หมายเลขอ้างอิงของ SSL
- Status: สถานะของ SSL
- SSL Type: ประเภทของ SSL
- Validate Type: ประเภทของการรับรองความปลอดภัยของ SSL
- Domain Coverage: ประเภทของ Domain ที่ SSL รับรองความปลอดภัย
- Date Created: วันที่ทำการซื้อ SSL
- Expiry Date: วันหมดอายุของ SSL

4.3. SSL Renewal: ส่วนการต่ออายุ SSL

- Duration (Year): จำนวนปีที่ต้องการต่ออายุ

4.4. Summary: ส่วนสรุปข้อมูลการต่ออายุ

- New Expiry Date: วันหมดอายุใหม่คำนวณจากจำนวนปีต่ออายุที่เลือก
- SSL Package Price / Year: ราคาต่อปีของผลิตภัณฑ์
- Duration (Year): จำนวนปีที่ต้องการต่ออายุ
- Total (Baht): ยอดรวมของราคาที่จะทำการต่ออายุ SSL

* * กรณี SSL ประเภท Positive Multiple Domain จะมีรายละเอียดเพิ่มเติมดังนี้

- Quantity Additional Domain: จำนวน Domain ที่ซื้อเพิ่ม
- Additional Price / Domain: ราคาของ Domain ที่ซื้อเพิ่ม

5. เลือกจำนวนปีที่ต้องการต่ออายุที่หัวข้อ SSL Renewal

6. หลังจากเลือกจำนวนปีที่ต้องการต่ออายุ สามารถตรวจสอบจำนวนปีที่ต้องการต่ออายุ วันหมดอายุใหม่ และยอดรวมของราคาที่ต้องการต่ออายุที่หัวข้อ Summary

7. เมื่อต้องการยืนยันการต่ออายุ กด Submit เพื่อดำเนินการต่ออายุ SSL

---

## วิธีการ Reissue SSL บน gate.openlandscape.cloud

การ Reissue SSL คือการสร้างใบรับรองของ SSL ที่ถูกใช้อยู่ใหม่ เงื่อนไขในการสร้างใบรับรองใหม่ของ SSL คือ SSL ที่ต้องการสร้างใบรับรองใหม่จะต้องถูกเปิดใช้งานแล้ว โดยมีการแสดงผลสถานะเป็น Active

1. หลังจากเช้าสู่ระบบแล้ว ที่แถบเมนูด้านข้างเลือกตัวเลือก "SSL" ระบบจะเข้าสู่หน้าดังกล่าว

2. กดที่ () ของ SSL ที่มีสถานะ Active

3. กด Reissue จาก Action Menu

การเข้าสู่หน้า Reissue สามารถเข้าผ่านหน้า Detail ได้เช่นกัน

4. เมื่อเข้าสู่หน้า Reissue จะพบกับข้อมูล 4 ส่วนประกอบด้วย

4.1. Details: รายละเอียดข้อมูลของ SSL ที่ต้องการออกใบรับรอง SSL ใหม่

- SSL ID: หมายเลข ID ของ SSL
- Status: สถานะของ SSL
- SSL Type: ชื่อผลิตภัณฑ์ของ SSL
- Validation Type: รูปแบบการรองรับของ SSL
- Domain Coverage: รูปแบบการรองรับจำนวน Domain
- Created Date: วันที่ถูกซื้อ SSL
- Expiration Date: วันหมดอายุ SSL

4.2. CSR & Contact: ส่วนของข้อมูล Certificate Signing Request เพื่อใช้ในการออกใบรับรอง SSL ใหม่

- CSR: ตัวเลือกใช้งานการสร้าง CSR ด้วยการกรอกข้อมูลด้วยตนเอง
- Existing CSR: ตัวเลือกใช้งานโดยการคัดลอก CSR ที่ถูกสร้างจากผู้ให้บริการอื่นมาวาง

4.3. Domain Name: ข้อมูลของ Domain ที่เกี่ยวข้องกับ SSL ที่ต้องการออกใบรับรอง SSL ใหม่

- Primary Domain: ชื่อ Domain ที่ต้องการใช้ SSL Certificate นี้ ในกรณีที่เป็น Multi-Domain กล่องข้อความสำหรับกรอก Domain เพิ่มเติมจะปรากฏ หาก Domain เพิ่มเติมถูกใส่ไว้ใน CSR ข้อมูล Domain จะถูกเติมเข้ากล่องข้อความอัตโนมัติ

4.4. Select Your Server Type: เลือกรูปแบบของ Server

- Windows IIS or Java Tomcat:
- Other Types of Servers ( Such as cPanel, Apache, NGINX, etc.)

5. ที่หัวข้อ CSR & Contact ผู่ใช่สามารถเลือกสร้าง CSR ด้วยตัวเองหรือคัดลอกจากผู้ให้บริการอื่นได้

กรณีที่ 1 ผู้ใช้เลือกสร้าง CSR ด้วยตนเอง

1. ผู้ใช้กด Generate CSR เพื่อเริ่มสร้าง CSR ด้วยตัวเอง

2. หน้าต่างสร้าง CSR จะปรากฏขึ้นมาเพื่อกรอกข้อมูลโดยแต่ละหัวข้อจะถูกแบ่งดังนี้

- Basic Information: ข้อมูลทั่วไป

และกรณีกด  จะมีหัวข้อเพิ่มดังนี้

- กรณีที่เป็น Multi-Domain หัวข้อ Subject Alternative Names จะปรากฏขึ้นเพื่อรองรับการกรอก Domain เพิ่มเติม

- Security: รูปแบบการเข้ารหัส CSR ที่ถูกสร้าง

- Extensions: ส่วนเสริมการเข้ารหัส CSR

- Key Usage: ข้อกำหนดการใช้ CSR

- Extended Key Usage: ข้อกำหนดการใช้ CSR เพิ่มเติม

3. เมื่อกรอกข้อมูลเรียบร้อยแล้วกด CREATE

4. หน้าต่าง Collect CSR จะปรากฏขึ้น และดาวน์โหลดไฟล์ csr-generate.zip โดยอัตโนมัติ บนหน้าต่างข้อมูล CSR จะมีหัวข้อทั้งหมด 3 หัวข้อ

- CSR: CSR เพื่อใช้ในการออกใบรับรอง SSL ใหม่

- Private Key: คีย์ที่ใช้ในการยืนยันตัวตนในกรณีจำเป็น **คัดลอกเก็บไว้เอง**

- Certificate: ข้อมูลใบรับรองของ SSL

5. กด I have copied the private key close this window เพื่อปิดหน้าต่าง Collect CSR

6. ข้อมูล CSR จะปรากฏแทนที่ปุ่ม Generate CSR และ Primary Domain จะปรากฏ Domain ที่ต้องการใช้งาน SSL นี้

กรณีที่ 2 ผู้ใช้เลือกคัดลอกจากผู้ให้บริการอื่น

1. ผู้ใช้คัดลอก CSR จากที่มีอยู่แล้ววางในกล่องข้อความ

2. เมื่อผู้ใช้วาง CSR แล้ว Primary Domain ในหัวข้อ Domain Name จะปรากฏ

6. เมื่อผู้ใช้ให้ข้อมูล CSR แล้วสามารถเลือก Server Type โดยมีตัวเลือกดังนี้

6.1. Windows IIS or Java Tomcat

6.2. Other Type of Server ( Such as cPanel, Apache, NGINX, etc.)

และมีค่าเริ่มต้นเป็น Other Type of Server

7. เมื่อผู้ใช้ให้ข้อมูลในหน้าเรียบร้อยแล้วสามารถกด Next เพื่อไปยังขั้นตอนต่อไปได้

8. กรอก Admin Email สำหรับรับ SSL Certificate และเลือกวิธีการ Activate รูปแบบ DCV โดย DCV เป็นขั้นตอนที่ใช้ในการยีนยันว่าผู้ใช้เป็นผู้ถือครอง Domain ที่ถูกนำขอใช้ SSL จริงหรือไม่ โดยวิธีในการยืนยันมี 2 วิธีคือ

8.1. Email: จำเป็นต้องมีการเลือก Approver Email เพื่อทำการยืนยันตัวตน วิธีการนี้จะเป็นการส่งอีเมลยืนยันตัวตนไปยัง Approver Email ที่ได้เลือกไว้

8.2. HTTP: เมื่อเลือกตัวเลือกนี้ผู้ใช้จำเป็นต้องนำไฟล์ยีนยันตัวตนอัปโหลดไว้บนเว็บไซต์

9. หลังจากเลือก DCV Method แล้วผู้ใช้สามารถกด Next เพื่อไปยังขั้นตอนถัดไปได้

10. ผู้ใช้จะเข้าสู่หน้าสรุปข้อมูลการขอใบรับรอง SSL ใหม่ มีหัวข้อ 3 หัวข้อ ดังนี้

10.1. Summary Detail:

- SSL ID: หมายเลข ID ของ SSL
- Status: สถานะของ SSL
- SSL Type: ชื่อผลิตภัณฑ์ของ SSL
- Validation Type: รูปแบบการรองรับของ SSL
- Domain Coverage: รูปแบบการรองรับจำนวน Domain
- Created Date: วันที่ถูกซื้อ SSL
- Expiration Date: วันหมดอายุ SSL

10.2. Email Receive SSL:

- อีเมลสำหรับรับข้อมูล Certificate SSL

10.3. Domains Secured & DCV Method:

- Domain Name (DNS):
- วิธีการ DCV มีดังนี้

1. กรณี Email: Send a Validation Email To {approver email ที่เลือก}
2. กรณี HTTP: Upload The Validation File To {domain name}/.well-known/pki-validation/

11. เมื่อตรวจสอบเรียบร้อยผู้ใช้สามารถกด Reissue เพื่อยืนยันการ Reissue ได้

หลังการ Reissue สำเร็จ SSL จะมีสถานะเป็น Reissued

---

สนใจสมัครใช้บริการได้ที่ คลิก หรือหากมีข้อสงสัย หรือต้องการสอบถามข้อมูลเพิ่มเติมสามารถติดต่อ OpenLandscape ผ่านทางอีเมล technical-support@ols.co.th หรือ Call Center 02-257-7189 ได้ตลอด 24 ชั่วโมง

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

ที่มา: [https://blog.openlandscape.cloud/ssl-certificate-registration](https://blog.openlandscape.cloud/ssl-certificate-registration)
