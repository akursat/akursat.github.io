---
author: akursat
comments: true
date: 2015-10-26 17:37:18+00:00
layout: post
link: http://akursat.com/?p=230
slug: 13-1-metottan-bir-degerin-dondurulmesi
title: 13.1 - Metottan Bir Değerin Döndürülmesi
wordpress_id: 230
categories:
- Java
- Java Se
tags:
- java
- java dersleri
- metot
- return
- void
---

Bir metot



	
  * metottaki tüm kod satırlarını tamamladığında,

	
  * return satırına ulaştığında veya

	
  * bir hata fırlattığında


çağrıldığı kod satırına döner.

Metodun return (dönüş) tipini metodu tanımlanırken belirtiliriz. Metot içerisinde return satırı bir değeri döndürmek için kullanılır.
<!-- more -->
void olarak tanımlamış bir metot bir değer döndürmez. return satırını bulundurma zorunluluğu yoktur ama istenirse bu yapılabilir. Örneğin, bir kontrol yapısında (if-else) metottan çıkış yaparak geri kalan kodun yürütülmesini durdurmak için kullanılır. Basitçe

    
    return;


şeklinde kullanılır.

Eğer void tanımladığınız bir metotta değer döndürmeye çalışırsanız derleyici hatası alırsınız.
void tanımlanmayan her metot, bir değer döndüren dönüş tipi barındırmalıdır.

    
        return donenDeger;


Dönen veri tipi metotta tanımlanan dönüş tipiyle uyumlu olmalıdır. Örneğin geri dönüş tipi boolean tanımlanmış bir metotta integer döndüremezsiniz.

Daha önceki konularda gördüğümüz bir metot olan getArea() metodu bir integer döndürüyordu.

    
      // dikdörtgenin alanının hesaplayan metot
       public int getArea() {
           return genislik * yukseklik;
       }


Bu metot genislik * yukseklik hesaplayarak bir integer döndürür.
getArea metodu bir primitif tip döndürür. Bir metot ayrıca bir referans tipide döndürebilir. Daha önce yazdığımız Bisiklet sınıfı kullanan referan tipi döndüren bir metot yazalım;

    
    public Bisiklet kiminBisikletiDahaHızlı(Bisiklet bisikletim, Bisiklet bisikletin,
                                 Cevre cevre) {
       Bisiklet enHizlisi;
       // girilen bisikletlerden çevre şartlarına
       // ve bisikletin donanımına göre
       // en hızlı olanı hesaplayan satırlar
       return enHizlisi;
    }
