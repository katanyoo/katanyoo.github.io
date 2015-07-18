---
layout: post
title:  "การติดตั้ง Yii2"
date:   2015-07-17 21:41:00
categories: yii2 installing
---


#### การติดตั้งทำได้ 2 แบบครับ
* ติดตั้งด้วย Composer
* ติดตั้งด้วยการดาวน์โหลดไฟล์มาติดตั้งเอง

#### โปรเจค Yii2 ที่เราจะเลือกติดตั้งมี 2 แบบ
* แบบ basic
* แบบ advance

<br>

ติดตั้งด้วย Composer
===================

* ติดตั้ง composer ก่อนครับ (ถ้าติดตั้งแล้วก็ข้ามไปครับ)

*สำหรับ Linux และ Mac OS X*
{% highlight bash %}
$ curl -sS http://getcomposer.org/installer | php
$ mv composer.phar /usr/local/bin/composer
{% endhighlight %}

*สำหรับ Windows* <br>
    ก็ไปดาวน์โหลดไฟล์นี้มารันครับ [Composer-Setup.exe](https://getcomposer.org/Composer-Setup.exe)

* ติดตั้ง composer asset plugin ครับ <br>
(ตัวนี้จะทำให้ composer สามารถจัดการ package ของ bower และ npm ได้ครับ)

{% highlight bash %}
$ composer global require "fxp/composer-asset-plugin:~1.0.0"
{% endhighlight %}
<br>

* เริ่มสร้าง Yii Project ของเรา

#### แบบ Basic
    {% highlight bash %}
    $ composer create-project --prefer-dist yiisoft/yii2-app-basic app_name
    {% endhighlight %}
หลังจากเสร็จแล้วก็ลองทดสอบความถูกต้องดูครับ 
[http://localhost/app_name/web/index.php](http://localhost/app_name/web/index.php) <br>
ถ้าขึ้นหน้าเว็บ Congratulations! ก็เป็นอันสำเร็จครับ

#### แบบ Advance
{% highlight bash %}
$ composer create-project --prefer-dist yiisoft/yii2-app-advanced app_name
$ php path/to/app_name/init
{% endhighlight %}
แล้วเลือกแบบ dev ครับ <br>
หลังจากเสร็จแล้วก็ลองทดสอบความถูกต้องดูครับ 
[http://localhost/app_name/frontend/web/index.php](http://localhost/app_name/frontend/web/index.php) <br>
ถ้าขึ้นหน้าเว็บ Congratulations! ก็เป็นอันสำเร็จครับ

<br>

ติดตั้งแบบดาวน์โหลดไฟล์มาติดตั้งเอง
================================
* ดาวน์โหลดไฟล์จาก [http://www.yiiframework.com/download/](http://www.yiiframework.com/download/) <br>
(เลือกดาวน์โหลดเอาครับ ว่าเราจะใช้โปรเจคแบบ basic หรือ advance)
* แตกไฟล์แล้วนำไปวางที่ Web root ของเครื่องเราครับ
