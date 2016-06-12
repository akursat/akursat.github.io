---
author: akursat
comments: true
date: 2015-10-21 16:27:31+00:00
layout: post
link: http://akursat.com/?p=164
slug: 12-2-nesnelerin-kullanimi
title: 12-2 Nesnelerin Kullanımı
wordpress_id: 164
categories:
- Java
- Java Se
tags:
- java
- metot
- new operatörü
---

Bir nesneyi oluşturduğunuzda onu bir şeyler için kullanmak istersiniz. Field’lerinden birini kullanmak yada değiştirmek isteyebilirsiniz. Yada metotlarından birini belirli işlemleri yerine getirmesi için çağırmak isteyebilirsiniz.


### **Nesnenin Field’lerine erişme**


Nesnelerin field’lerine isimleriyle ulaşılır. Dolayısıyla belirsiz isimler kullanmamalısınız. İsimlendirme kurallarıyla ilgi konuya göz atabilirsiniz.
Örneğin Dikdortgen sınıfında “genislik” ve “yukseklik” olmak üzere iki değişken tanımlamıştık. Bunları o sınıf içerisinde şu şekilde ekrana yazdırabilirdik.
<!-- more -->

    
    System.out.println(“Genişlik ve Yükseklik: " + genislik + ", " + yukseklik);


Bu sınıfın dışındaki bir kodda bir nesne referansı kullanarak bu field’lere erişebiliriz. Bu nesne referansını nokta (.) operatörü takip etmelidir.

nesneninRefaransı.fieldAdı
Örneğin daha önce kullandığımız [NesneOrnek](http://akursat.com/?p=99) adli sınıfta Dıkdortgen adli sınıfın field’lerine erişmiştik.

    
    System.out.println("dikdortgenBir genişliği: " + dikdortgen1.genislik);




### **Nesnenin metotlarına erişme**


Nesne referasını ayrıca bir nesnesin metodunu çağırmak için kullanabilirsiniz. Nesnenin referansına nokta (.) operatörü ekleyerek metotların ismini çağırabilirisiniz. Metodunuza argünmanları parentez içersinde sağlayabilirsiniz. Metodunuz argüman gerektirmiyorsa boş parentez kullanın.

nesneninReferansı.MetotAdı(Argümanlar);
veya:
nesneninReferansı.MetotAdı();

Örneğin daha önce kullandığımız [NesneOrnek](http://akursat.com/?p=99) adli sınıfta Dıkdortgen adli sınıfın metotlarına erişmiştik.

    
    System.out.println("dikdortgenBir alanı: " + dikdortgen1.getArea());
    dikdortgen2.move(40, 72);


İlk metot argünman gerektirmediği için boş parentez kullanıldı. İkinci metot dikdörtgenin x ve y değerlerini değiştiren yani dikdörtgeni hareket ettiren bir metot. Metot iki argüman alıyor bunun için (40, 72) şeklinde yazıldı.


### **new Operatörüyle Field ve metot kullanımı**


Bir nesnenin field veya metodunu çağırmadan önce onu önceden referansını oluşturmuştuk.

    
     Dikdortgen dikdortgen1 = new Dikdortgen(100, 200);


Yukarıda bu dıkdortgen1  referansını kullanarak getArea() metoduna erişmiştik.

Bu referansı değişkende tutmadanda erişebiliriz.

    
    int dikdortgeninAlani = new Dikdortgen(100,200).getArea();


Burada new Dikdortgen(100,200) Dikdortgen nesnesinin referansını dönderir. Nokta (.) operatörü kullanarak da getArea() metodunu çağırdık. Dönen hesaplamayı da  dikdortgeninAlani değişkenine atadık. Bunu field’ler içinde yapabilirsiniz.

Burada unutmamanız gereken şey bu satır yürütüldükten sonra Dikdortgen bir referansa sahip olmayacaktır. Çünkü program referansı herhangi bir yere kaydetmedi.
