---
layout: post
title:  "โครงสร้างของ application"
date:   2015-07-19 01:46:00
categories: yii2
---

แบบ Basic
=========

{% highlight bash %}
basic/                  โปรเจคของเรา
    composer.json       สำหรับกำหนด package ต่างๆ ที่เราติดตั้งด้วย Composer
    config/             สำหรับเก็บไฟล์สำหรับการตั้งค่า
        console.php     ไฟล์สำหรับตั้งค่า console application
        web.php         ไฟล์สำหรับตั้งค่า web application
    commands/           เก็บ class ที่เป็นคำสั่งใน console
    controllers/        เก็บ class ที่เป็น controller
    models/             เก็บ class ที่เป็น model
    runtime/            สำหรับเก็บไฟล์ที่ถูก Yii สร้างขึ้นในขณะที่เว็บทำงาน
    vendor/             เก็บไฟล์ package ต่างๆ ที่ถูกติดตั้ง
    views/              เก็บไฟล์ view
    web/                Web root ของ app
        assets/         เก็บไฟล์พวก js, css (Yii จะเป็นคนจัดการ)
        index.php       ไฟล์เริ่มต้น app
    yii                 ใช้สำหรับรันคำสั่งต่างๆ ของ Yii ใน console
{% endhighlight %}

<br>

แบบ Advance
===========

Yii แบ่งโปรเจคเป็น 3 application คือ

* `backend/` เว็บฝั่ง backend
* `frontend/` เว็บฝั่ง frontend
* `console/` เป็น application ที่จะถูกสั่งงานผ่าน console

และมี dirctory พิเศษคือ

* `common/` สำหรับเก็บไฟล์ที่ต้องใช้ร่วมกันทั้ง 3 application ด้านบน
* `environments/` เก็บ config สำหรับโปรเจคใน environment ต่างๆ

ไฟล์อื่นๆ ในโปรเจค

{% highlight bash %}
.gitignore          ไฟล์สำหรับระบุไฟล์ที่ไม่ต้องการในระบบ git (version system)  
composer.json       สำหรับกำหนด package ต่างๆ ที่เราติดตั้งด้วย Composer
init                สคริปที่ใช้รันสำหรับการเตรียม application
init.bat            เหมือนไฟล์ init แต่เอาไว้สำหรับ Windows
LICENSE.md          สำหรับเขียน license ของโปรเจคเรา
README.md           สำหรับเขียนข้อมูลที่เกี่ยวกับโปรเจคเรา
requirements.php    ไฟล์สำหรับตรวจสอบความพร้อมการใช้งาน Yii
yii                 ใช้สำหรับรันคำสั่งต่างๆ ของ Yii ใน console
yii.bat             เหมือนไฟล์ yii แต่เอาไว้สำหรับ Windows
{% endhighlight %}
