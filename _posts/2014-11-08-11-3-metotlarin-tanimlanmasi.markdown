---
author: akursat
comments: true
date: 2014-11-08 08:22:27+00:00
layout: post
link: http://akursat.com/?p=85
slug: 11-3-metotlarin-tanimlanmasi
title: 11.3 - Metotların Tanımlanması
wordpress_id: 85
categories:
- Java
- Java Se
tags:
- aşırı yükleme
- isimlendirme
- java
- java dersleri
- metot
- overloading
- return
- signature
---

Klasik bir metot tanımı şu şekildedir;





    
    public double ustAl(double taban, int ust) {
    		// hesaplamalar burada
        }




Metot tanımlama sırasıyla aşağıdaki kuralları takip eder;





<blockquote>

> 
> 
	
>   * 

> 
> _Erişim belirleyeciler - public,private gibi._
> 
> 

> 
	
>   * 

> 
> _Dönüş tipi (return) – Değerin veri tipi metot tarafından döndürülür.Veya metot void ise bir değer döndürülmez._
> 
> 

> 
	
>   * 

> 
> _Metot ismi – Bir Metodun İsimlendirilmesi alt başlığındaki kurallları takip eder._
> 
> 

> 
	
>   * 

> 
> _Parametre listesi parentezlerin içindedir – Veri tipi ve parametre ismi tanımlanır.Girilen parametreler virgüllerle(,) ayrılır.Eğer herhangi bir parametreye sahip değilse boş () bırakılır. _
> 
> 

> 
	
>   * 

> 
> _Exception listesi bulundurur – Sonraki konularda değineceğiz._
> 
> 

> 
	
>   * 

> 
> _Metot köşeli parentezlerle { } ile çevrilmelidir._
> 
> 

> 

</blockquote>




### Bir Metodun İsimlendirilmesi




İsimlendirme işlemi İngilizce ve Türkçe dillerinde karışıklık yaratıyor.Metot isimlendirmelerinde fiiler küçük harfle başlar.Eğer birden fazla kelimeyle ifade edilecekse yine fiil küçük harfle başlar sonra gelen isim,sıfat vb. Ifadeler ilk harfi büyük yazılır.Ama bu kurallar dillerin yapısı farklı olmasından dolayı anlamsız isimlendirmeler doğurabilir.Örneğin;




getBackground / getirArkaplan
setX
isEmpty




Buna farkli bir öneri yada düzen getirilmediğinden tavsiye edilen kodların İngilizce yazılmasıdır.Bu durum hemde Türkçe karekter sorununuda çözecektir.Daima İngilizce kelimeler kullanın emin değilseniz sözlüklerden yardım alın.İsimler uzun olabilir ama daima anlamlı olsun.





### Metot Signature




Overloading geçmeden önce Metot Signature tanımlamamız gerekiyor.Metot Signature(imzası) metotun ismi ve parametre tipleri olmak üzere iki bileşenden oluşur.Örneğin;




    
    hesapla (double,int,int)




### 
Overloading (Aşırı Yükleme)




Overloading aynı isimli metodu, farklı parametre tipleri/sayıları ile tanımlama işlemidir.Bu metodu çağırdığınız zaman verdiginiz parametre tipleri veya sayısına göre doğru metot compiler tarafından seçilir.
Java Metodun Signaturena bakarak bu durumu ayırt eder.
Örneğin farklı tiplerdeki sayıları yada farklı sayıdaki sayıları toplamak istiyoruz.





    
    package com.metotlar;
    
    /**
     * @author akursat
     * @site www.akursat.com
     */
    
    public class Overloading {
    
    	public void topla(int sayi1) {
    
    	}
    
    	public void topla(double sayi1) {
    
    	}
    
    	public void topla(int sayi1, int sayi2) {
    
    	}
    
    	public void topla(int sayi1, double sayi2) {
    
    	}
    
    	/*
    	 * Return tiplerini compiler ayırt etmez.Altaki iki metot
           * hata verir.
    	 */
    
    	public float topla(float a) {
    		return a;
    	}
    
    	public long topla(float a) {
    
    		return (long) a;
    	}
    
    }





Örneğin topla (int sayi1) ile topla (double sayi1) metodu farklı parametre tipleri aldığından ayrı iki metotdur.


     Örneğin sonundaki iki metot hakkında önemli bir hatırlatma yapmamız gerek derleyici(compiler) dönüş tipine(return) bakarak farklılıkları ayırt etmez.Dolayısıyla Aynı metot signature una sahip iki metodun dönüş tipleri farklıda olsa tanımlanamazlar.


Overload edilmiş metotlar idareli kullanılmalıdır çünkü kodun okunabilirliğini azalabilir.







