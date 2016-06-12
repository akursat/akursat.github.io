---
author: akursat
comments: true
date: 2014-11-08 08:02:34+00:00
layout: post
link: http://akursat.com/?p=70
slug: 9-5-do-while-dongusuyle-iterasyon
title: 9.5 do... while – Döngüsüyle İterasyon
wordpress_id: 70
categories:
- Java
- Java Se
tags:
- do while
- java
- java &gt;&gt;
- java dersleri
---

Do while döngüsü while döngüsüne benzer.Aralarındaki fark do while döngüsünde en az bir defa ifadelerin yürütülmesidir.
Boolean expression true ise kontrol akışı tekrar do'ya döner bu işlem boolean exrepssion false olana kadar sürer.
Birinci örnekte sayac değeri 12 sayac şartı <11 olmasına karşın do while olduğundan println komutu birkez çalıştı.
İkinci örnekte sayac2 değeri 1 sayac2 şartı <11 dir.Örneklerin çıktısı aşağıda verilmiştir.

While ifadesinin yapısı:

    
    do
    {
       //ifadeler
    }while(Boolean_expression);


Birinci Örnek:

    
    int sayac = 12;
    do {
    	System.out.println(sayac);
    	sayac++;
         } while (sayac < 11);



Çıktı :
12

İkinci Örnek:


    
    int sayac2 = 1;
    do {
    	System.out.print(sayac2 + ",");
    	sayac2++;
         } while (sayac2 < 11);


Çıktı :
1,2,3,4,5,6,7,8,9,10,
