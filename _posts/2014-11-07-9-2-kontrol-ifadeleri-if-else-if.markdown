---
author: akursat
comments: true
date: 2014-11-07 21:17:50+00:00
layout: post
link: http://akursat.com/?p=63
slug: 9-2-kontrol-ifadeleri-if-else-if
title: 9.2 Kontrol İfadeleri – if -else if
wordpress_id: 63
categories:
- Java
- Java Se
tags:
- boolean
- else if
- if
- if else
- java
- java dersleri
---

If-else if, if-else'in kademeli olarak genişletilmesiyle oluşuyor.İç içe geçmiş if – else ifadeleri hem okunabilirlik hemde programlama açısından zor olabilir.else if çoklu koşulları denerken oldukça kullanışlıdır.
[If-else yazısında](http://www.akursat.com/9-1-kontrol-ifadeleri-if/) blok{} kullanmadan tek bir ifade yazılabileceğini söylemiştik.else if ifadesinin bundan yararlandığını aşağıdaki birinci örnekten görebilirsiniz.
if,else if ifadeleri Switch ifadesine göre çoğunlukla yavaştır ve Switch ifadesinin aksine kompleks expressionlar içerebilir.

    
    if(Boolean_expression 1){
       //Boolean expression 1 true dönerse yürütülecek.
    }else if(Boolean_expression 2){
       //Boolean expression 2 true dönerse yürütülecek.
    }else if(Boolean_expression 3){
       //Boolean expression 3 true dönerse yürütülecek.
    }else {
       //Yukardakilerden hiçbiri true dönmezse yürütülecek.
    }


Son satırdaki else ifadesi en yakındaki(yukarı doğru) if'e aitdir.İkinci örneğe bakarak bu durumu daha kolay anlayabilirsiniz.

    
    int not = 63;
    
    if (not >= 90) {
    	System.out.println("Notunuz A");
    } else if (not >= 80) {
    	System.out.println("Notunuz B");
    } else if (not >= 70) {
    	System.out.println("Notunuz C");
    } else if (not >= 60) {
    	System.out.println("Notunuz D");
    } else {
    	System.out.println("Notunuz F");
    	}


Çıktı;

    
    Notunuz D


else if ifadesinin if else ifadesinin genişletilmişi olduğunu söylemiştik.else if kullanmadan da benzer uygulamayı yapalım.

    
    	if (not >= 90) {
    			System.out.println("Notunuz A");
    		} else {
    			if (not >= 80) {
    				System.out.println("Notunuz B");
    			} else {
    				if (not >= 70) {
    					System.out.println("Notunuz C");
    				} else {
    					if (not >= 60) {
    						System.out.println("Notunuz D");
    					} else {
    						System.out.println("Notunuz F");
    					}
    				}
    			}
    		}


Çıktı;

    
    Notunuz D
