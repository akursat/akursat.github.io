---
author: akursat
comments: true
date: 2014-11-07 21:09:49+00:00
layout: post
link: http://akursat.com/?p=61
slug: 9-1-kontrol-ifadeleri-if
title: 9.1 Kontrol İfadelerİ – if
wordpress_id: 61
categories:
- Java
- Java Se
tags:
- if
- if else
- java
- java dersleri
---

### **If Statement**




If ifadesinde, boolean değeri true değerlendirirse yani koşul sağlanırsa bloklar ({}) içindeki ifadeler yürütülecektir.




    
    if(Boolean_expression)
    {
       //True dönerse statement yürütülecek.
    }


**_Örneğin;_**

    
    int sayi1=100;
    int sayi2=200;
    if(sayi1<sayi2){
    System.out.println(“sayi1 sayi2'den küçük.”)
    }




_Çıktı;_




    
    sayi1 sayi2'den küçük.




Eğer tek bir ifadeye sahipseniz blokları kullanmak zorunda değilsiniz.Yinede blokları kullanmak çoğu zaman tercih edilir.




    
    if(sayi1<sayi2)
    	System.out.println(“sayi1 sayi2'den küçük.”)




### **If – else Statement**




If – else ifadesinde, boolean değerinin false dönmesi durumunda yani koşul sağlanmadığında da bloklar içindeki ifadeler yürütülmesi için oluşturulmuştur.




    
    if(Boolean_expression)
    {
       //True dönerse statement yürütülecek.
    }else{
       //False dönerse statement yürütülecek.
    }


_Örneğin;_

    
    int sayi1=100;
    int sayi2=200;
    if(sayi1>sayi2){
    
     	System.out.println(“sayi1 sayi2'den büyük.”)
    
    } else{
    
    	System.out.println(“sayi1 sayi2'den küçük.”)
    
    }




_Çıktı;_




    
    sayi1 sayi2'den küçük.
