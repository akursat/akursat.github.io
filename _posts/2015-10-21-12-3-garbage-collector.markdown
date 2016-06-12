---
author: akursat
comments: true
date: 2015-10-21 16:37:28+00:00
layout: post
link: http://akursat.com/?p=169
slug: 12-3-garbage-collector
title: 12-3 Garbage Collector
wordpress_id: 169
categories:
- Java
- Java Se
tags:
- garbage collector
- java
- jvm
- nesne
---

![](http://384uqqh5pka2ma24ild282mv.wpengine.netdna-cdn.com/wp-content/uploads/2015/04/GCDuke.png)Bazı nesneye dayalı diller tüm oluşturduğunuz nesneleri takip etmenizi ve ihtiyacınız olmadığında yok etmenizi gerektirir. Hafızayı kendi başınıza yönetmek tedirginlik ve hataya düşmeye sebep oluşturabilir. Java platformu istediğiniz kadar nesne oluşturmanıza izin verir (elbette sisteminizin üstesinden gelebileceği kadar), ve onları yok etmeniz için endişelenmenize gerek yok. JRE nesneleri daha fazla kullanılmayacağına karar verdiğinde onları siler. Bu sürecin adına “garbage collection” denir.
<!-- more -->
Bir nesne referans barındırmadığında garbage collection için uygun hale gelir. Referanslar genellikle değişken scope’ın dışına çıktığında sonlanır. Bazen bir değişkene null değerini atayarak da nesnenin referansını sonlandırabilirsiniz.  Bir programda aynı nesneye birden fazla referans olabileceğini hatırlayın; bu nesnenin garbage collection’a uygun olabilmesi  tüm bu referanslarının sonlanması gerekir.

JRE, referansa sahip olmayan nesnelerce kullanılan hafızayı belirli aralıklarla boşaltan bir garbage collector’a sahiptir. Garbage collector işini doğru zaman olduğuna karar verdiğinde otomatik olarak yapar.
