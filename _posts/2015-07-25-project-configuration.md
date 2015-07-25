---
layout: post
title:  "ไฟล์สำหรับตั้งค่าโปรเจค"
date:   2015-07-25 23:00:00
categories: yii2
---

การตั้งค่าของโปรเจคที่เราต้องรู้ในเบื้องต้น<br>
สำหรับแบบโปรเจคแบบ Advance จะซับซ้อนกว่าแบบ <br>
Basic อยู่พอประมาณ แต่ก็เข้าใจไม่ยากครับ 


<br>

โปรเจคแบบ Basic
==============
ไฟล์สำหรับตั้งค่าอยู่ในโฟลเดอร์ `config` ซึ่งมี 4 ไฟล์

* `console.php` - ไฟล์ตั้งค่าสำหรับ console application
* `db.php` - ไฟล์ตั้งค่าการเชื่อมต่อฐานข้อมูล
* `params.php` - ไฟล์กำหนด parameter ที่ต้องการ
* `web.php` - ไฟล์ตังค่าหลักของเว็บ

<br>

โปรเจคแบบ Advance
================
ไฟล์สำหรับตั้งค่านั้นมีทั้งหมด 20 ไฟล์ที่ Yii จัดเตรียมไว้ให้ ประกอบด้วย <br>
config ของ 3 application ย่อย

* `frontend/config`
* `backend/config`
* `console/config`

และ 1 config ส่วนกลางที่ทุก application ใช้ร่วมกัน

* `common/config`

ซึ่งทั้ง 4 โฟลเดอร์มีไฟล์สำหรับ config อยู่ 5 ไฟล์ดังนี้ครับ

1. `bootstrap.php`
    - ไฟล์นี้จะถูกเรียกใช้ตอน app เริ่มทำงาน <br>
    โดยปกติแล้วก็จะเป็นพวก alias ของ path ต่างๆ ในโปรเจค
2. `main-local.php`
    - ไฟล์ตั้งค่าหลักของ app <br>
    ไฟล์นี้จะไม่เหมือนกันในแต่ละเครื่อง (กรณีที่พัฒนาเว็บร่วมกันหลายคน)
3. `main.php`
    - ไฟล์ตั้งค่าหลักของ app
4. `params-local.php`
    - ไฟล์กำหนด parameter ที่ต้องการ <br>
    ไฟล์นี้จะไม่เหมือนกันในแต่ละเครื่อง (กรณีที่พัฒนาเว็บร่วมกันหลายคน)
5. `params.php`
    - ไฟล์กำหนด parameter ที่ต้องการ

<br>

เราอาจจะงงว่า บร๊ะเจ้า!! แล้วไฟล์เยอะขนาดนี้เราจะต้องตั้งค่าในไฟล์ไหนกันล่ะเนี่ย <br>
ง่ายๆ เลยครับ สังเกตจากชื่อไฟล์จะมี 2 กลุ่ม คือ main กับ params ครับ

ซึ่งลำดับความสำคัญก็เรียงจาก "น้อยไปมาก" ดังนี้ครับ

กลุ่ม main ของ frontend

* `common/config/main.php`
* `common/config/main-local.php`
* `frontend/config/main.php`
* `frontend/config/main-local.php`

แปลว่าถ้าเราตั้งค่าบางอย่างใน `common/config/main.php` <br>
และก็ตั้งค่าสิ่งเดียวกันใน `frontend/config/main-local.php` <br>
ระบบจะถือการตั้งค่าของไฟล์ใน frontend เป็นหลักนั่นเอง

กลุ่ม params ของ frontend

* `common/config/params.php`
* `common/config/params-local.php`
* `frontend/config/params.php`
* `frontend/config/params-local.php`

สำหรับ config ใน app อื่นๆ (`console`, `backend`) ลำดับความสำคัญก็เป็นเช่นเดียวกันครับ

ง่ายๆ แค่นี้เองครับ อิอิ :P