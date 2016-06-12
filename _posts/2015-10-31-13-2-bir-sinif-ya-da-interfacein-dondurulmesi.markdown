---
author: akursat
comments: true
date: 2015-10-31 12:55:51+00:00
layout: post
link: http://akursat.com/?p=240
slug: 13-2-bir-sinif-ya-da-interfacein-dondurulmesi
title: 13.2 – Bir Sınıf ya da Interface’ın Döndürülmesi
wordpress_id: 240
categories:
- Java
- Java Se
tags:
- contravariance
- covariance
- interface
- java
- java dersleri
- kalıtım
- metot
- object
- sınıf
---

Eğer bu bölüm kafanızı karıştırırsa atlayın. Interface ve Kalıtım bölümlerini bitirdikten sonra tekrar inceleyin. Bir metot dönüş tipi olarak sınıf ismi kullandığında, [kiminBisikletiDahaHızlı](http://akursat.com/?p=230) metodunda yaptığımız gibi, dönen nesnenin tipinin sınıfı ya  dönüş tipinin bir alt sınıfı (subclass) ya da bir sınıfı olmalıdır.

(Aşağıdaki resimdeki Number sınıfını Sayı olarak, ImaginaryNumber sınıfını da SanalSayı olarak adlandırdım.)

Örneğin SanalSayı adlı bir sınıfın java.lang.Number sınıfının alt sınıfı olduğunu varsayalım ve o da resimde gösterildiği gibi Object sınıfının alt sınıfıdır.(Java’da tüm sınıflar Object sınıfının alt kümesidir.)

[caption id="" align="aligncenter" width="146"]![](http://docs.oracle.com/javase/tutorial/figures/java/classes-hierarchy.gif) SanalSayı için sınıf hiyerarşisi.[/caption]

Şimdi Sayı tipinde bir dönüşe sahip bir metoda sahip olduğumuzu düşünelim.

    
    public Sayi birSayiDondur() {
        ...
    }


birSayiDönder metodu bir sanal sayi döndürebilir ama bir “Object” döndüremez. SanalSayı bir sayidir çünkü Sayının alt sınıfıdır. Buna rağmen Object bir Sayı olmak zorunda değildir - String veya başka bir tip olabilir.

Bir metodu, orijinal metodun bir alt sınıfını döndürecek şekilde tanımlayabiliriz.(override)

    
    public SanalSayi birSayiDondur() {
            ...
        }


Yukarıdaki gibi override edilmiş bir metot için; Bir alt sınıftaki metodun dönüş tipi bir üst sınıftaki metodun dönüş tipinden farklı olabilir. Bu teknik “covariant dönüş tipi” olarak adlandırır.

Interface isimlerini de benzer şekilde dönüş tipi olarak kullanabilirsiniz.

Covariance ve contravariance hakkında detaylı bilgi : [https://en.wikipedia.org/wiki/Covariance_and_contravariance_%28computer_science%29](https://en.wikipedia.org/wiki/Covariance_and_contravariance_%28computer_science%29)
