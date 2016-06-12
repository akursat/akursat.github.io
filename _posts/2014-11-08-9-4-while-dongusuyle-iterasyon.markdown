---
author: akursat
comments: true
date: 2014-11-08 07:59:09+00:00
layout: post
link: http://akursat.com/?p=68
slug: 9-4-while-dongusuyle-iterasyon
title: 9.4 while –  Döngüsüyle İterasyon
wordpress_id: 68
categories:
- Java
- Java Se
tags:
- döngü
- java
- java dersleri
- loop
- sonsuz döngü
- while
---

Döngüler ifadelerin istenilen sayıda yürütülmesini sağlar.Bir döngüdeki her bir geçişe iterasyon adı verilir.
While döngüsü için boolean expression değerlendirilir, değer true ise ifadeler yürütülür.Bu işlem değer false değerlendirilene kadar tekrarlanır.Bu durumu Birinci örnekteki x<10 olduğu sürece ifadenin değerlendirilmesinden görebilirsiniz.
While ifadesindeki boolean expression her bir iterasyondan önce değerlendirilir(pre-test) do while'da ise iterasyondan sonra değerlendirilir(post-test).

While ifadesinin yapısı:

    
    while (boolean-expression) {
            ifadeler
        }


Bu örnekte x<10 sağlandığı sürece while döngüsü ekrana x'in değerini yazdırıyor.x++ ile x'in değeri her bir iterasyonda bir artılıyor.İşlem tamamlanmadan önceki son iterasyonda x=10 oluyor ama 10<10 sağlamadığından bu ekrana yazdırılmıyor.
Birinci Örnek:

    
    int x = 5;
    while (x < 10) {
    	System.out.println("x'in değeri:" + x);
    	x++; // x=x+1
    }




Çıktı;
x'in değeri:5
x'in değeri:6
x'in değeri:7
x'in değeri:8
x'in değeri:9






### While ile Sonsuz Döngü


Whiledaki boolean-expression değerini true yaparak sonsuz döngü elde edebiliriz.

    
    while (true){
        // kodlarınız
    }



