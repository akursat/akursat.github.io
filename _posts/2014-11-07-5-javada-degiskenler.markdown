---
author: akursat
comments: true
date: 2014-11-07 20:44:04+00:00
layout: post
link: http://akursat.com/?p=43
slug: 5-javada-degiskenler
title: 5- Java'da Değişkenler
wordpress_id: 43
categories:
- Java
- Java Se
tags:
- atama
- değişken
- field
- java
- java dersleri
- non-static
- parametre
- static
---

Bir değişken hafıza parçasınından oluşur buda veriyi içerir. Değişkenin veri tipi olmalıdır. Veri tiplerine daha sonra değineceğim.


_Edit: Java programlama dilinde,"field" ve "variable"(değişken) terimlerinin her ikisi de kullanılır ikiside çoğu zaman aynı şeyi ifade eder. Kısaca field bir sınıfın içersinde bulunan değişkendir. Java Field yazısında arasındaki farkı net bir şekilde anlayacaksınız yazıyı uzatmamak adına örnek vermiyorum._


**Değişken Tipleri**

  * **Non-static fields/Instance fields (Static olmayan alanlar):** Static kelimesiyle başlamayan değişkenlerdir.Her nesnenin(object) değeri kendine aittir._

  * **Static fields/Class Variebles (Static alanlar):** Static kelimesiyle tanımlanan alanlardır.Bu ifade “bu değişken varolduğu süre boyunca sadece bir kopyası olsun” anlamına gelir.Tüm nesneler aynı değere erişir.Java Field ile ilgili yazıda bu durumu örnekle açıklayacağım._

	
  * _**Yerel Değişkenler:** Bir metotun içinde tanımlanan değişkenlerdir.Sadece tanımlandığı metotdun içinde erişilebilir._


	
  * _**Parametreler:** Parametre bir metoda bildirilen değişkendir.Metotlar konusunda açıklayacağım._


**Değişken Tanımlama**




Değişken tanımlarken değişkenin tipini belirlememiz gerekir.
Javada değişkeni şuna benzer şekilde tanımlarız;




    
    tipi ismi;




tipi yerine değişkenin veri tipini yazmalıyız.ismi yerine değişkenimize istediğimiz adı verebiliriz.(Değişken isimlendirme kuralları dahilinde)
örneğin int tipinde,sayi adında bir değişken ve String tipinde,yazi adında bir değişken;




    
    int sayi;
    String yazi;




**
Değişken Atama**


Değişkenleri şu şekilde atayabiliriz;

    
    sayi = 45;
    
    yazi= “Değişken atama örneği”;




Değişkenleri tanımladığımız zamanda atayabiliriz;




    
    int kalem = 5;
    
    float pi_sayisi = 3.14;
    
    String ulke = ”İsviçre”;





**Değişken Okuma**




Değişkenler farklı durumlarda bulunabilir.Bir değişken başka bir değişkene atanabilir,bir değişken aritmetik işlemin öğesi olabilir,bir değişken parametre gibi bir metoda çağrılabilir.




    
    int sayi1 = 13;
    
    int sayi2 = sayi1; // sayi2 değişkenine sayi1 değişkeni atanıyor.
    
    int sayi3 = sayi1 + 14; //sayi1 değişkeni bir aritmetik işleme dahil ediliyor.
    
    System.out.println(sayi1); //sayi1 değişkeni bir metot tarafından çağrılıyor.





**Değiken İsimlendirme Kuralları**




Değişkenleri isimlendirirken dikkat etmemiz gereken kurallar var.Bunlar şöyle;






	
  1. Java büyük-küçük harfe duyarlıdır.(case sensitive)Yani kalem değişkeni, KALEM değişkeninden veya Kalem değişkeninden farklıdır.

  2. Değişken isimleri bir harf, veya $ , veya _ ile başlamalıdır.

  3. Değişken, isminin ilk harfinden(veya $,_) sonra rakam içerebilir.

	
  4. Değişken ismi ayrılmış kelimelerle(keyword) aynı olamaz.Mesela int , String adlı bir değişken tanımlayamayız.Bu kelimelerin listesine [şuradan](http://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html) ulaşabilirsiniz.







Değiken isimlendirirken dikkat edeceklerimiz bunlardı.İyi görünümlü kod sayfaları oluşturmak için uymamız gereken bir kaç kural var.Java bu kurallara uymamız için bizi zorlamıyor.






	
  * Değişken isimleri küçük harfle yazılır. Örneğin String kalem;




	
  * Eğer değişken birden fazla kelime içeriyorsa ikinci kelimeye büyük harfle başlanır.Örneğin String kursunKalem;




	
  * İzin verdiği halde değişkenleri isimlendirken $ yada _ ile başlamayız.




	
  * Geçici int değişkenler için i,j,k,m,n.Geçici karekter değişkenleri içinse c,d,e kullanırız. 




	
  * Adlandıracağımız kelimeler kısa ve anlamlı olmalıdır.




Değişkenler için bilmemiz gereken kurallar bunlar benzer kurallar sınıflar,sabitler (constants) ve metodlar içinde bulunuyor.İsimlendirme kurallarını içeren bir yazıda bunlara değineceğim.
