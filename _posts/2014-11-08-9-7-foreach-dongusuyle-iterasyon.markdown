---
author: akursat
comments: true
date: 2014-11-08 08:05:49+00:00
layout: post
link: http://akursat.com/?p=75
slug: 9-7-foreach-dongusuyle-iterasyon
title: 9.7 foreach - Döngüsüyle İterasyon
wordpress_id: 75
categories:
- Java
- Java Se
tags:
- collection
- döngü
- for
- for each
- Iterator
- java
- java dersleri
- TimerTask
---

For ifadesinin Collection ve Diziler için tasarlanmış bir halide vardır.Bu Genişletilmiş for yada foreach olarak adlandırılır.
Bu bölümde Collection ve Diziler hakkında bilgi gerekebilir.Sadece birinci örneği anlamanız for each yapısı için yeterli.


### Foreachde Dikkat Edilmesi Gerekenler


Foreach döngüsünde yapısı gereği yapamıyacağınız bazı şeylerde bulunur.Bunlar;



	
  * Collectionlarda gezerek eleman silemezsiniz.

	
  * Dizi veya listede o anki yeri değiştiremezsiniz.

	
  * Çoklu collection yada dizileri itere edemezsiniz.


Diziler için basit bir foreach örneği:

Bu örnekte numaralar adlı dizinin herbir elemanı print ile listelenmiştir.

    
    int[] numaralar = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
    		for (int item : numaralar) {
    			System.out.print(item + ",");
    		}


Çıktı:

1,2,3,4,5,6,7,8,9,10,


Collectionlar için bir foreach örneği:

Bu örnekte gelen Collectiondan bir iteratör oluşturuyoruz(i).Her bir görev zamanlayıcısını iptal ediyoruz.(Bu örnek JavaOne konfreasından alıntılanmıştır.)

    
    void cancelAll (Collection c) {
         for (Iterator i = c.iterator(); i.hasNext(); ){
             TimerTask tt=(TimerTask) i.next();
           tt.cancel();
         }
       }


Aynı metot foreach ile yazılırsa

    
     void cancelAll(Collection c){
         for (TimerTask task : c)
              task.cancel();
    }


_ (TimerTask Timer sınıfıyla ilişkili olarak kullanılır.Bu sınıf hakkında bilginiz yoksa sadece örnekleri syntax açısından karşılaştırmanız yeterli.)_
Görüldüğü gibi foreach iteratöre olan ihtiyaçımızı giderdi.
