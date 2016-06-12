---
author: akursat
comments: true
date: 2014-11-07 21:30:38+00:00
layout: post
link: http://akursat.com/?p=65
slug: 9-3-kontrol-ifadeleri-switch
title: 9.3 Kontrol İfadeleri – switch
wordpress_id: 65
categories:
- Java
- Java Se
tags:
- java
- java dersleri
- switch
- switch case
---

Switch ifadesi,switch'in aldığı expressiondaki değere bağlı olarak farklı ifadelerin yürütülmesini sağlar.




Switch için şu kurallar geçerlidir;






	
  * expression byte,short,char ve int primitif tiplerini alır.Enum tipleri, String sınıfı ve Charecter,Byte,Short,Integer Wraper sınıflarınıda destekler.(float ve double tiplerini almaz!)

	
  * expression herbir case'deki deger ile karşılaştırılır deger bulunursa o case'deki ifadeler yürütülür bulunmazsa default'daki ifadeler yürütülür.Bu durumu Birinci örnekten daha kolay anlayabilirsiniz.

	
  * break çoğu zaman gereklidir.Örneğin expression degerle karşılaştıktan sonra diğer case'lereki ifadelerin yürütülmemesini istiyorsak break kontrolu kullanmalıyız.İkinci örneğe bakarak break'in önemini daha kolay anlayabilirsiniz.

	
  * Birden fazla case aynı ifadelere sahipse case 1 : case 2 : … şeklinde devam ettirebilirsiniz.Bu durum Üçüncü örnekte gösterilmiştir.

	
  * default seçeneğinde break kullanma nedeni default istenilen case aralığında yazabilmemizdir.(Sonda yazmak için bir zorlama yok).Bundan dolayı case'in akışını bozmamak için default da break kullanılır.




Switch ifadesinin yapısı:




    
    switch(expression){
        case deger :
           //Statements
           break; //isteğe bağlı
        case deger :
           //Statements
           break; //isteğe bağlı
        //İstediğiniz kadar case ekliyebilirsiniz.
        default : //isteğe bağlı
           //Statements
    }




Birinci Örnek:





    
    //Girilen sayının hangi aya karşılık olduğunu bulan örnek.
            int ay = 9;
    		String stringAy;
    		switch (ay) {
    		case 1:
    			stringAy = "Ocak";
    			break;
    		case 2:
    			stringAy = "Şubat";
    			break;
    		case 3:
    			stringAy = "Mart";
    			break;
    		case 4:
    			stringAy = "Nisan";
    			break;
    		case 5:
    			stringAy = "Mayıs";
    			break;
    		case 6:
    			stringAy = "Haziran";
    			break;
    		case 7:
    			stringAy = "Temmuz";
    			break;
    		case 8:
    			stringAy = "Ağustos";
    			break;
    		case 9:
    			stringAy = "Eylül";
    			break;
    		case 10:
    			stringAy = "Ekim";
    			break;
    		case 11:
    			stringAy = "Kasım";
    			break;
    		case 12:
    			stringAy = "Aralık";
    			break;
    		default:
    			stringAy = "Geçersiz Ay";
    			break;
    		}
    		System.out.println(stringAy);




Çıktı;
Eylül


Bu örnekte 2.ayın adı soruluyor case 2 break kontrolüne sahip değil kendinden sonra gelen case'leredeki ifadelerde yürütülüyor.Break kontrolüne sahip case 5'e gelinceye kadar sürüyor.


İkinci Örnek:





    
    //break kontrolünü gösteren örnek
             int ay = 2;
    		String stringAy;
    		switch (ay) {
    		case 1:
    			stringAy = "Ocak";
    			System.out.println(stringAy);
    		case 2:
    			stringAy = "Şubat";
    			System.out.println(stringAy);
    		case 3:
    			stringAy = "Mart";
    			System.out.println(stringAy);
    		case 4:
    			stringAy = "Nisan";
    			System.out.println(stringAy);
    		case 5:
    			stringAy = "Mayıs";
    			System.out.println(stringAy);
    			break;
    		case 6:
    			stringAy = "Haziran";
    			System.out.println(stringAy);
    		case 7:
    			stringAy = "Temmuz";
    			System.out.println(stringAy);
    		case 8:
    			stringAy = "Ağustos";
    			System.out.println(stringAy);
    		case 9:
    			stringAy = "Eylül";
    			System.out.println(stringAy);
    		case 10:
    			stringAy = "Ekim";
    			System.out.println(stringAy);
    		case 11:
    			stringAy = "Kasım";
    			System.out.println(stringAy);
    			break;
    		case 12:
    			stringAy = "Aralık";
    			System.out.println(stringAy);
    			break;
    		default:
    			stringAy = "Geçersiz Ay";
    			break;
    		}


Çıktı;
Şubat
Mart
Nisan
Mayıs


Birden fazla case'de aynı ifadeyi yürütebiliriz.Benzer şekilde case12:case1:case2 .. şeklide de yazabilirsiniz ama bu yazım şekli okunabilirlik açısından daha iyidir.
Üçüncü Örnek:




    
    //Girilen ayın hangi mevsimde yer aldığını gösteren örnek.
            int ay = 12;
    		String stringMevsim;
    		switch (ay) {
    		case 12:
    		case 1:
    		case 2:
    			stringMevsim = "Kış";
    			break;
    		case 3:
    		case 4:
    		case 5:
    			stringMevsim = "İlkbahar";
    			break;
    		case 6:
    		case 7:
    		case 8:
    			stringMevsim = "Yaz";
    			break;
    		case 9:
    		case 10:
    		case 11:
    			stringMevsim = "Sonbahar";
    			break;
    		default:
    			stringMevsim = "Geçersiz Ay";
    			break;
    		}
    		System.out.println(stringMevsim);
    	}


Çıktı;
Kış
