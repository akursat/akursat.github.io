---
author: akursat
comments: true
date: 2014-11-08 08:04:32+00:00
layout: post
link: http://akursat.com/?p=72
slug: 9-6-for-dongusuyle-iterasyon
title: 9.6 for - Döngüsüyle İterasyon
wordpress_id: 72
categories:
- Java
- Java Se
tags:
- buble sort
- döngü
- for
- for each
- java
- java dersleri
- loop
- sonsuz döngü
---

For döngüsü programınızdaki bir dizi işlemi tekrarlamanıza izin verir.

For Döngüsünün Yapısı:


    
    for (initialization; boolean-expression; increment) {
            //ifadeler
        }





	
  * Döngü yürütüldüğünde initialization expression ilk olarak değerlendiririr.Bu expression sıklıkla döngünün kontrol değişkenin başlangıç değeri olarak atanır.(örn: i=0)

	
  * boolean-expression herbir iterasyondan önce test edilir.False olması durumunda sonlandırılır.Çoğunlukla bir karşılaştırmadır.(örn: i <11)

	
  * Her bir iterasyonun sonunda increment expression değerlendirilir.Çoğunlukla kontrol değişkenlerini artırmada kullanılır.(örn: i++)


For Döngüsü Örneği:

    
    for (int i = 0; i < 11; i++) {
    
       System.out.print(i + ",");
    
    }


Çıktı:
0,1,2,3,4,5,6,7,8,9,10,



### **For Döngüsünün Farklı Formları**





	
  * initialization expression boş bırakılarak for döngüsü sağlanabilir.



    
    int i = 0 ;
    for ( ; i < num ; i++ ) // init. boş bırakıldı.
    {
      // kodlarınız
    }





	
  * increment expression boş bırakılarakda for döngüsü sağlanabilir.



    
    for ( int i = 0 ; i < num ; ) // increment boş bırakıldı.
    {
      // kodlarınız
    }





	
  * boolean-expression boş bırakıldığında daima true değeri alır.(false değeri alsaydı döngüye girmezdi dolayısıyla kullanışsız olurdu)Ve sonsuz döngü oluşur.



	
  * Üç expressionda opsiyoneldir.Üçünüde kullanmayarak da sonsuz döngü elde edebilirsiniz.(Sonsuz döngü oluşturmak için bollean-expression boş bırakmak yeterlidir.)



    
    // sonsuz döngü



    
    for ( ; ; ) {
    
        // kodlarınız
    }







