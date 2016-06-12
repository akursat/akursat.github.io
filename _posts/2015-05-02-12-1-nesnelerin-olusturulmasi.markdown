---
author: akursat
comments: true
date: 2015-05-02 18:15:24+00:00
layout: post
link: http://akursat.com/?p=134
slug: 12-1-nesnelerin-olusturulmasi
title: 12.1 - Nesnelerin Oluşturulması
wordpress_id: 134
categories:
- Java
- Java Se
tags:
- java
- java dersleri
- java new
- nesne
- new
---

**Point baslangicNoktasi1** = new Point(23, 94);
**Dikdortgen dikdortgen1** = new Dikdortgen(baslangicNoktasi1, 100, 200);
**Dikdortgen dikdortgen2** = new Dikdortgen(50, 100);

Birinci Satır Point sınıfından bir nesne oluştururken. İkinci ve üçüncü satır Dikdortgen sınıfından bir nesne oluşturuyor. Bu üç satırında ortak özellikleri var. Bunlar;



	
  1. **Declaration**: Kalın yazı ile belirtilen tüm değişken tanımlamaları(declaration) bir nesne tipini ve ismini içeriyor.

	
  2. **Instantiation**: new bu nesneyi oluşturan Java operatörüdür.

	
  3. **Initialization**: new operatörünü bir constructor takip eder.(yukarıdaki birinci satırda Point(-,-) ifadesini görebilirsiniz) Bu yeni nesneyi ilklendirecektir. (initialization)


<!-- more -->
Bu üç kavram havada kalmamalıdır bundan dolayı anladığınıza emin olup ilerlemenizi tavsiye ederim. Bu temel üç ifade kısaca Tanımlar, Oluşturur ve İlklendirir.


### **Değişkenin Tanımlanması**



    
    Point baslangicNoktasi1;
    
    


şeklinde tanımlanan bir değişken bir nesneye atanmadığı sürece belirsiz olacaktır. Yani değişken tanımlamak nesneyi oluşturmaz. new operatörü ile baslangicNoktasini bir nesneye atamalısınız. Aksi taktirde derleyici hatasıyla karşılaşırsınız.

Bu durumdaki değişkeni şu şekille ifade edelim;

[![bas1](http://akursat.com/wp-content/uploads/2015/05/bas1.png)](http://akursat.com/wp-content/uploads/2015/05/bas1.png)


### **Nesnenin Oluşturulması**


new operatörü, yeni bir nesne ve o nesnenin bellekteki referansı için bellekte yer ayırarak bir nesne oluşturur. Ayrıca nesnenin constructor’ını çağırır.

new operatörü oluşturulan nesne için bir referans döndürür. Bu referans uygun tipte bir değişkene atanır. Örneğin;

    
    Point baslangicNoktasi1 = new Point(23, 94);


**Point Sınıfı**

    
    public int x;
    public int y;
    
    public Point(int x, int y)
       {
        this.x = x;
        this.y = y;
      }


Sınıfın tamamını [buradan](http://developer.classpath.org/doc/java/awt/Point-source.html) inceleyebilirsiniz.

Burada Point sınıfı benim oluşturduğum bir sınıf değil. Bu sınıf java.awt içerisinde bulunuyor. Bir point (nokta) (x,y) koordinat düzleminde integer olarak bir konumu temsil ediyor. Bir üsteki örneğimizde bu konuma (23,94) argümanları göndermiştik.

    
    Point baslangicNoktasi1 = new Point(23, 94);


Bu satır yürütüldükten sonra sonucu şu şekilde gösterebiliriz;

[![bas2](http://akursat.com/wp-content/uploads/2015/05/bas2.png)](http://akursat.com/wp-content/uploads/2015/05/bas2.png)Dört constructor içeren Dikdortgen sınıfının kodu şöyle;

    
    package com.nesneler;
    
    import java.awt.Point;
    /**
     *
     * @author akursat
     *
     */
    public class Dikdortgen {
        public int genislik = 0;
        public int yukseklik = 0;
        public Point baslangicNoktasi;
    
        // dört constructor
        public Dikdortgen() {
            baslangicNoktasi = new Point(0, 0);
        }
    
        public Dikdortgen(Point p) {
            baslangicNoktasi = p;
        }
    
        public Dikdortgen(int w, int h) {
            baslangicNoktasi = new Point(0, 0);
            genislik = w;
            yukseklik = h;
        }
    
        public Dikdortgen(Point p, int w, int h) {
            baslangicNoktasi = p;
            genislik = w;
            yukseklik = h;
        }
    
        // dikdörtgeni hareket ettiren metot
        public void move(int x, int y) {
            baslangicNoktasi.x = x;
            baslangicNoktasi.y = y;
        }
    
        // dikdörtgenin alanının hesaplayan metot
        public int getArea() {
            return genislik * yukseklik;
        }
    }


Eğer bir sınıfta birden fazla constructor varsa onlar farklı signature’lara sahip olmalıdır. Buna daha önce [burada](http://akursat.com/?p=85) değinmiştik.

    
    Dikdortgen dikdortgen1 = new Dikdortgen(baslangicNoktasi1, 100, 200);


Bu satır Diktortgen sınıfının dördüncü constructor’ını çağırır, baslangicNoktasi1 için baslangicNoktasini ilklendirir. Ayrıca constructor, genisliği 100 ve yüksekliğide 200 olarak ayarlar. Şimdi aynı Point nesnesi için iki referansa sahibiz - bir nesne birden fazla referans alabilir.  [![bas3](http://akursat.com/wp-content/uploads/2015/05/bas3.png)](http://akursat.com/wp-content/uploads/2015/05/bas3.png)
