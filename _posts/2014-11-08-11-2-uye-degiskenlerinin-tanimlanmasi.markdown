---
author: akursat
comments: true
date: 2014-11-08 08:22:03+00:00
layout: post
link: http://akursat.com/?p=86
slug: 11-2-uye-degiskenlerinin-tanimlanmasi
title: 11.2 - Üye Değişkenlerinin Tanımlanması
wordpress_id: 86
categories:
- Java
- Java Se
tags:
- değişken
- encapsulation
- field
- java
- java dersleri
- kapsülleme
- parametre
---

Sınıflar içersinde kullanılan bazı değişken türleri şunlardı:
**     Field:**Bir sınıfa üye olan değişkenler.
**     Local Variables(Yerel Değişkenler):**Bir metot yada kod bloğunda bulunan değişkenler.
**     Parametreler:**Metot tanımlamalarında kullanılan değişkenler.


## 





## 




## Field




[11-Sınıflar](http://www.akursat.com/11-siniflar/) adlı yazıda Bisiklet adlı sınıfta üç field tanımlamıştık.





    
    // Bisiklet sınıfı üç fielde sahip.
    	private int kadans;
    	private int vites;
    	private int hiz;




Örnektende anlaşıldığı üzere Field üç kısımdan oluşuyor:






	
  * 


Modifier(Erişim belirleyiciler) örneğin public private vb.




	
  * 


Fieldin tipi




	
  * 


Fieldin adi







Bu üç field de kadans,vites ve hiz adında integer tipinde private olarak tanımlamıştık.Private fieldin sadece bu sınıftan erişebileceğini belirtir.**  **






_**Kapsüllemenin(encapsulation)**_ yapısı gereği, genellikle fieldler private tanımlanır.Bunun anlamı bu değişkenlere doğrudan sadece Bisiklet sınıfının erişilebileceğidir.Yinede bizim bu değerlere erişmemiz gerekebilir.Bunlardan dolayı bu üç değişkenin değerine dolaylı olarak yönettiğimiz public tipinde dört metot tanımlamıştık.





    
    // Bisiklet sınıfı dört metoda sahip.
    	public void setKadans(int kadans) {
    		this.kadans = kadans;
    	}
    
    	public void setVites(int vites) {
    		this.vites = vites;
    	}
    
    	public void frenUygula(int azalt) {
    		hiz -= azalt;
    	}
    
    	public void hizArtir(int artir) {
    		hiz += artir;
    	}





    Üye değişkenlerinin isimlendirilmesinde genel kurallar geçerli.Bu konuya[ 5-Değişkenler ](http://www.akursat.com/5-javada-degiskenler/)yazısının Değişken İsimlendirme Kuralları başlıklı kısmına bakabilirisiniz.
Metotların parametre alması bir sonraki Metotların tanımlanması yazısında değineceğim.Private ne olduğunu veya bu dört metotdaki yapıları ve işlevini anlamak için acele etmeyin.İlerki yazılarda bu konulara değineceğim.
