---
author: akursat
comments: true
date: 2014-11-08 08:21:37+00:00
layout: post
link: http://akursat.com/?p=88
slug: 11-1-siniflarin-tanimlanmasi
title: 11.1 - Sınıfların Tanımlanması
wordpress_id: 88
categories:
- Java
- Java Se
tags:
- extends
- implement
- interface
- java
- java dersleri
- nesne
- sınıf
---

Kısaca sınıfın ne olduğuna değinelim.Sınıf, nesneler için bir şablondur.Basitçe anlatmak gerekirse tanımladığımız her bir nesne tanımladığımız şablona uyarak oluşur.
Sınıflar şu yolla tanımlanır;

    
    class Sinifim {
        // field, constructor,  
        // ve metot tanımlamaları
    }


[
Bir önceki yazıda](http://www.akursat.com/11-siniflar/) bu yolu kullanarak bir sinif tanımlamıştık.
Bir önceki Sinifim adlı oluşturduğumuz sinif yapısı sadece gerekli sınıf yapılarını içeriyordu.Aynı zamanda şu yollada;

    
    class Sinifim extends SuperSinifim implements Interface {
        // field, constructor,  
        // ve metot tanımlamaları
    }




sınıfları tanımlayabiliriz.

Bu tanımlamanın anlamı Sinifim sınıfı, SuperSinifimin bir alt sınıfınıdır(subclass) ve Interface(Arayüz) arayüzünü uyguluyordur(implement) diye yorumlanabilir. 
Cümlede bulunan terimler kafanızı karıştırmış olabilir.Bu terimlerin neler ifade ettiğini  sonraki yazılarda değineceğim.




    Aynı zamanda class Sinifim... ile başlayan kısmın en başına public,private gibi erişim belirleyiciler ekleyebilirsiniz.Erişim belirleyiciler(public ve private gibi), Sinifim sınıfına hangi diğer sınıfların erişebileceğini karar vermek için kullanılır.Bu konuyu Erişim Belirleyeciler yazısında detaylı açıklayacağım.


**İki tanımlama yolundanda anlaşıldığı gibi _Sınıflar sırayla aşağıdaki kuralları takip eder;_**


<blockquote>

> 
> 
	
>   * 

> 
> Erişim belirleyeciler _public_, _private_ gibi.
> 
> 

> 
	
>   * 

> 
> Sınıf ismi (İlk harfi büyük harfle başlamalıdır)
> 
> 

> 
	
>   * 

> 
> Bir sınıfın ana sınıfı yani superclassı(Kısaca temel özelliklerini aldığı sınıfı) varsa öncesinde extends kelimesini gerektirir.Bir sınıf(subclass) sadece bir ana sınıftan miras alabilir. 
> 
> 

> 
	
>   * 

> 
> Interfaceler sınıfa uygulanabilir.Bu durum varsa öncesinde implements kelimesini gerektirir.Bir sınıfa birden fazla interface virgülle ayrılarak uygulanabilir.
> 
> 

> 
	
>   * 

> 
> Sınıfın içeriği parentezlerle {} çevrilmelidir.

> 
> 

> 

</blockquote>




Bu yazıda sınıfların bu iki yolla tanımlanabileceğini öğrendik.Bir sonraki yazıda sınıflara ait olan değişkenlerin(üye değişkenleri) tanımlanmasına değineceğim.







