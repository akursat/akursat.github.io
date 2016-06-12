---
author: akursat
comments: true
date: 2014-11-08 08:28:13+00:00
layout: post
link: http://akursat.com/?p=95
slug: 11-5-metotlara-bilgi-gondermek-2
title: 11.5 – Metotlara Bilgi Göndermek - 2
wordpress_id: 95
categories:
- Java
- Java Se
tags:
- argüman
- java
- java dersleri
- metot
- new
- pass
- primitif
- referans
---

**Primitif Veri Tipli Argümanların Bildirimi**




Double,int gibi primitif argümanlar metotlara değişkenin değeri tarafından bildirilir.Bunun anlamı; parametrelerin değerlerlerinin değişmi sadece metodun kapsamı(scope) boyunca var olur olarak yorumlanabilir. Bunu bir örnekle anlamak çok daha kolay.

    
    public static void main(String[] args) {
    
    		int x = 3;
    		// x argümanı ile passMethod() çağıralım.
    		passMethod(x);
    		// x değişmişmi diye ekrana yazdıralım.
    		System.out.println("passMethod çağrıldıktan sonrası, x = " + x);
    	}
    
    	public static void passMethod(int p) {
    		p = 10;
    	}


Program çalıştırıldıktan sonra çıktı:

    
    passMethod çağrıldıktan sonrası, x = 3





**Referans Veri Tipli Argümanların Bildirimi**




Object gibi referans veri tipli parametreler, metotlara değişkenin değeri tarafından bildirilir.Bunun anlamı metot döndüğünde,bildirilen referans hala aynı önceki nesneyi referans eder.Ancak nesne field'lerinin değerleri metot içerisinde değiştirilebilir.Bu konuda önemli ve örnek üzerinden anlamak çok daha kolay olacak.

    
    public static void main(String[] args) {
    
    		PassingReference pr = new PassingReference();
    		Circle mycircle = new Circle();
    		pr.moveCircle(mycircle, 92, 78);
    		// metot döndükten sonra mycircle nesnesinin x değeri 45 değil hala 92!
    		System.out.println(mycircle.getX());
    	}
    
    	// circle mycircle referans alıyor ve mycirclenın x ve y pozisyonlarını bu
    	// metotda değiştiriyoruz
    	public void moveCircle(Circle circle, int deltaX, int deltaY) {
    		circle.setX(circle.getX() + deltaX);
    		circle.setY(circle.getY() + deltaY);
    		// Değişim sonrası circle(mycircle referans ediyor) x ve y si
    		System.out.println(circle.getX() + "--" + circle.getY());
    
    		// Yeni bir circle oluşturalım.ve x ve y 0 atayalım.
    		circle = new Circle(0, 0);
    		circle.setX(45);
    		circle.setY(45);
    	}


Burada circle sınıfını kod kalabalığı olmamaması açısından paylaşmadım ama yakında tüm yazıların kodlarını github üzerinden paylaşacağım.

Örnektende anlaşılacağı üzere mycircle adında bir nesne oluşturduk.Daha sonra bu nesne moveCircle metoduna 92 ve 78 argümanlarıyla gönderdik.moveCircle metodunda circle adlı parametre artık bu mycircle referans ediyor.circle.setX gibi işlemlerimizde aslında bu nesne üzerinde değişlik yaptık.

circle=new Circle(0,0) ile aynı adda yeni bir nesne oluşturduk ve bunun x ve y değerlerini 45 atadık.Artık moveCircle metodu sonlandı ve metot pr.moveCircle... satırına geri döndü.Buradan sonraki satırda mycircle nesnesinin x değerini ekrana yazdırdığımızda değerin 45 değil hala 92 olduğunu göreceksiniz.Çünkü yukarıdada belirtiğim gibi circle nesnesi hala mycircle referans alıyor.
