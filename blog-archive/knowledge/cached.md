# เช็ค Cached แล้วหรือยัง ? ปัญหายอดฮิตที่ทำให้ Linux ช้าลง

###### FAQ

20/3/2023

---

![ปก เช็ค cached แล้วยัง](/_next/image?url=https%3A%2F%2Fblog-wp.openlandscape.cloud%2Fcached%2Fblog_%25e0%25b9%2580%25e0%25b8%258a%25e0%25b9%2587%25e0%25b8%2584_cached_%25e0%25b9%2581%25e0%25b8%25a5%25e0%25b9%2589%25e0%25b8%25a7%25e0%25b8%25ab%25e0%25b8%25a3%25e0%25b8%25b7%25e0%25b8%25ad%25e0%25b8%25a2%25e0%25b8%25b1%25e0%25b8%2587%2F&w=3840&q=75)
<!-- รูปภาพ: ภาพปกบทความ เช็ค Cached แล้วหรือยัง ปัญหาที่ทำให้ Linux ช้าลง -->

ทำไมจู่ ๆ Server ทำงานช้าลง ?  ความคิดเหล่านี้เกิดขึ้นทันทีเมื่อ Server เกิดอาการหน่วง ๆ หรือทำงานผิดปกติ ใครจะไปรู้ว่าสาเหตุสำคัญอีกหนึ่งสาเหตุ ที่มักพบกันบ่อย ๆ เมื่อเกิดปัญหา Server ช้า นั่นก็คือ "Cached" บนระบบ Linux ดังนั้น ขออนุญาตหยิบยกประเด็นนี้มาพูดถึง และอธิบายถึงสาเหตุ รวมไปถึงวิธีการแก้ปัญหากัน

อย่างที่ทุกท่านทราบว่า Linux Server นั้น มีการใช้งาน Performance ที่ต่ำมากกว่า OS อื่น ซึ่งในส่วนนี้ท่านอาจใช้แค่ RAM : 1 GB ก็สามารถใช้งานได้ตามปกติแล้ว (Command Mode) แต่บางทีอาจพบว่า Server มีอาการช้า ๆ หรือ เกิดหน่วงขึ้นเมื่อมีการเรียกใช้ Command แต่เมื่อทำการ Restart เครื่อง อาการเหล่านี้ดันหายไป… หากพบว่าอาการที่เจอ มีลักษณะเป็นแบบนี้ นั่นบ่งบอกได้ว่า RAM มีการถูกใช้งานเยอะ แล้วเกิดการเก็บ Cached เอาไว้

---

# "What is Cached ?"

คือ ความจำประเภทนึงใน OS ที่เก็บการทำงานที่มีการใช้งานบ่อย ๆ เอาไว้ เพื่อเวลามีการใช้งานในรูปแบบเดิมจะสามารถทำงานได้เร็วยิ่งขึ้น

### อ้าว !? แล้วทำไม Cached ถึงทำให้ช้าละ มันควรทำให้เร็วขึ้นสิ

นั่นก็เพราะว่า การที่เครื่องทำงานได้อย่าง Smooth นั้น ปกติมันก็ต้องใช้ RAM ในการทำงานครับ แต่ RAM ที่มีดันถูกใช้เก็บ Cached ไปหมดแล้ว จนทำให้เครื่องไม่มี RAM เหลือเพียงพอต่อการใช้งานนั่นเอง

---

# ประเภทของ Cache

### Clean Cache & Dirty Cache

- Clean Cache คือ  ความจำที่มีการถูกเรียกใช้งานบ่อยหรือเราใช้เป็นประจำ ทำให้เครื่องทำงานได้เร็วยิ่งขึ้น
- Dirty Cache คือ ความจำที่เคยถูกเรียกใช้งานหรือไม่ได้มีการใช้งานสม่ำเสมอ และไม่ได้ใช้งานอีกแล้ว

# อาการที่บ่งบอกว่า RAM ไม่เพียงพอต่อการใช้งาน

1. เมื่อ SSH เข้าเครื่อง แล้วเกิดอาการค้างหรือเข้าไม่ได้ชั่วขณะ
2. เครื่องมีอาการทำงานช้าหรืออาการหน่วง ๆ
3. ใช้ Command พื้นฐานไม่ได้ เช่น Top แล้วค้าง
4. ถ้ามีการใช้งานในรูปแบบ Web ตัว Website จะใช้งานได้ช้ากว่าปกติ

# วิธีตรวจสอบการใช้งาน RAM

### พิมพ์คำสั่งใน Command Line

> free -h

- กรอบสีแดง – > แสดงค่าการใช้งานของ RAM หรือ Memory
- กรอบสีฟ้า – > แสดงค่าการใช้งานของ Disk ที่มาทำงานแทน RAM

อธิบายค่าของแต่ละ Column

- total : แสดงค่าที่มีทั้งหมด (total= used+free+buff/cache)
- used : แสดงค่าที่ถูกใช้งานทั้งหมด
- free : แสดงค่าที่ไม่ถูกใช้งาน หรือยังไม่ถูกใช้
- shared : แสดงค่าที่ถูกใช้งานแทน disk
- buff/cache : แสดงค่าที่ถูกใช้งานโดย buffer และ cache
- available : ค่าเริ่มต้นที่ถูกคาดการณ์ เมื่อapplicationนั้นไม่เคยถูกใช้งานมาก่อน

### หากต้องการแปลงหน่วย หรือ รายละเอียดเพิ่มเติม สามารถใช้ Command ด้านล่างเพื่อเข้าใจได้ง่ายขึ้น

> free –help

# วิธีแก้ไขปัญหา มี 2 วิธีหลักๆ

1.หากต้องการ Clear ทุก Service แนะนำให้ Restart เครื่อง

2.หากไม่สามารถ Restart เครื่องได้ สามารถทำได้ตามขั้นตอนด้านล่าง ดังนี้

- ต้องกำหนดตัวเข้า root ก่อน โดยใช้คำสั่ง

> sudo -s หรือ sudo su

- จากนั้นใช้คำสั่ง Clear Cache จะมี 3 รูปแบบ เลือกใช้อันใดอันนึง ดังนี้

สำหรับ Pagecache: (Recommends)

> sync; echo 1 > /proc/sys/vm/drop_caches

สำหรับ dentries and inodes:

> sync; echo 2 > /proc/sys/vm/drop_caches

สำหรับ pagecache, dentries, and inodes: (not recommends)***

> sync; echo 3 > /proc/sys/vm/drop_caches

***เหมาะสำหรับคนที่เข้าใจโครงสร้างของ pagecache, dentries, and inodes นี้เป็นอย่างดี

---

อธิบายเกี่ยวกับ Command ที่ใช้

- sync : มีหน้าที่เปลี่ยน Clan Cache ให้กลายเป็น Dirty Cache
- command " ; " : มีหน้าที่แยก Command แต่จะทำ Run Command แรกให้เสร็จก่อนถึงจะทำ Command ต่อไป
- echo  <num> :  มีหน้าที่แสดงผลตามหมายเลข
- drop_caches : มีหน้าที่ทิ้ง Clean Cache ให้ RAM ได้มีพื้นที่มากขึ้น

---

เมื่อใช้คำสั่งเสร็จแล้ว ลองใช้ Command ตรวจสอบก่อน เพื่อเช็คความเรียบร้อยหลังทำการลบไปแล้ว ยังมีอาการช้าลงหรือไม่ ถ้ายังพบว่ามีอาการช้าลงอยู่ ให้ลองเช็คว่า Service ไหนที่มีการเรียกใช้ RAM เยอะที่สุด โดยใช้คำสั่งตาม Command ตามข้างล่างนี้ได้เลย

> top

หลังใช้คำสั่ง "top" Command กด "shift+m" เราก็จะเห็น Service ที่มีการเรียกใช้ RAM มากสุด หรือ น้อยที่สุด นั่นเอง

### หากพบว่าทำหมดทุกขั้นตอนนี้แล้ว แต่ Server ยังช้าอยู่ ขอแนะนำให้พิจารณาเพิ่ม RAM เพราะการใช้วิธีนี้จะตอบโจทย์ปัญหาที่ท่านเจอมากที่สุดและง่ายที่สุดด้วย หรืออาจเลือกใช้ Disk มาทำเป็น RAM ได้เช่นกัน

###### Src: https://stackoverflow.com/questions/29870068/what-are-pagecache-dentries-inodes, https://www.tecmint.com/clear-ram-memory-cache-buffer-and-swap-space-on-linux/

![ภาพประกอบ  3  cached](https://blog-wp.openlandscape.cloud/wp-content/uploads/2019/01/%E0%B8%97%E0%B8%B5%E0%B9%88%E0%B8%84%E0%B8%B1%E0%B9%88%E0%B8%99%E0%B8%84%E0%B8%B9%E0%B9%88.png)
<!-- รูปภาพ: ภาพหน้าจอแสดงผลคำสั่ง free -h สำหรับตรวจสอบการใช้งาน RAM -->

**

## ติดตามข่าวสารใหม่ๆ หรือข้อมูลน่ารู้อีกมากมายได้ที่

## OpenLandscape Fanpage | https://www.facebook.com/openlandscapecloud/

## OpenLandscape Twitter | https://www.twitter.com/olscloud/

## OpenLandscape Cloud | https://openlandscape.cloud/

![ภาพประกอบ  4  cached](https://blog-wp.openlandscape.cloud/wp-content/uploads/2019/01/%E0%B8%97%E0%B8%B5%E0%B9%88%E0%B8%84%E0%B8%B1%E0%B9%88%E0%B8%99.png)
<!-- รูปภาพ: ภาพหน้าจอแสดงผลคำสั่ง top สำหรับตรวจสอบการใช้งานทรัพยากร -->

---

Share :

---

[Sethavoot Rerksuriyapant](/author/sethavoot)Simple is the best but everything can change for a reason.

##### สมัครใช้บริการของเรา

ให้ทุกการพัฒนาของคุณมีประสิทธิภาพมากกว่าที่เคย

[Get Started](https://openlandscape.cloud?utm_source=blog&utm_medium=getstarted)##### Related posts

---

![วิธีการยืนยันตัวตน eKYC บน Openlandscape Cloud](https://blog-wp.openlandscape.cloud/ekyc/%e0%b8%a7%e0%b8%b4%e0%b8%98%e0%b8%b5%e0%b8%81%e0%b8%b2%e0%b8%a3%e0%b8%a2%e0%b8%b7%e0%b8%99%e0%b8%a2%e0%b8%b1%e0%b8%99%e0%b8%95%e0%b8%b1%e0%b8%a7%e0%b8%95%e0%b8%99-ekyc/)
<!-- รูปภาพ: ภาพประกอบบทความที่เกี่ยวข้อง: วิธีการยืนยันตัวตน eKYC -->

###### FAQ

29/1/2026

วิธีการยืนยันตัวตน eKYC บน Openlandscape Cloud

![การสมัครสมาชิกและเข้าใช้งานระบบ eKYC](https://blog-wp.openlandscape.cloud/sign-up-and-access-the-ekyc-system/%e0%b8%81%e0%b8%b2%e0%b8%a3%e0%b8%aa%e0%b8%a1%e0%b8%b1%e0%b8%84%e0%b8%a3%e0%b8%aa%e0%b8%a1%e0%b8%b2%e0%b8%8a%e0%b8%b4%e0%b8%81%e0%b9%81%e0%b8%a5%e0%b8%b0%e0%b9%80%e0%b8%82%e0%b9%89%e0%b8%b2%e0%b9%83/)
<!-- รูปภาพ: ภาพประกอบบทความที่เกี่ยวข้อง: การสมัครสมาชิกและเข้าใช้งานระบบ eKYC -->

###### FAQ

29/1/2026

การสมัครสมาชิกและเข้าใช้งานระบบ eKYC

![OLS Package ! ครอบคลุมผู้ใช้ทุกระดับ พร้อมใช้งานแล้ว บน OpenLandscape Cloud](https://blog-wp.openlandscape.cloud/ols-package/cover-blog%e0%b8%84%e0%b8%a3%e0%b8%ad%e0%b8%9a%e0%b8%84%e0%b8%a5%e0%b8%b8%e0%b8%a1%e0%b8%9c%e0%b8%b9%e0%b9%89%e0%b9%83%e0%b8%8a%e0%b9%89%e0%b8%97%e0%b8%b8%e0%b8%81%e0%b8%a3%e0%b8%b0%e0%b8%94%e0%b8%b1/)
<!-- รูปภาพ: ภาพประกอบบทความที่เกี่ยวข้อง: OLS Package -->

###### FAQ

29/1/2026

OLS Package ! ครอบคลุมผู้ใช้ทุกระดับ พร้อมใช้งานแล้ว บน OpenLandscape Cloud



---

ที่มา: [https://blog.openlandscape.cloud/cached](https://blog.openlandscape.cloud/cached)