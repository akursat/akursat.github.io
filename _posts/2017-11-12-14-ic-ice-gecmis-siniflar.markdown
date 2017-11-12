---
author: akursat
comments: true
date: 2017-11-12 09:34:01+00:00
layout: post
link: http://akursat.com/?p=281
slug: 14-ic-ice-gecmis-siniflar
title: 14 - İç içe geçmiş sınıflar
wordpress_id: 281
categories:
- Java
- Java Se
tags:
- nested classes
- iç içe geçmiş sınıflar
- shadowing
- serialization
- java
- java dersleri
- scope
- static
---

## Blok kullanmadan initialize


İç içe sınıflar (nested classes) static ve static olmayan olmak üzere ikiye ayrılır.


    
    public class DisSinif {

        class IcSinif {
            
        }
    }

Bir iç sınıf onu kapsayan sınıfın üyesidir. Static olmayan İç sınıflar, private tanımlansalar bile onu kapsayan sınıfın üyelerine erişebilir. Static iç sınıflar ise onu kapsayan sınıfın üyelerine erişemezler. Bir iç sınıf, dış sınıfın bir üyesi olarak private, protected, public veya package private olarak tanımlanabilir. (Dış sınıfların sadece public veya package private tanımlanabileceğini hatırlayalım.)
İç içe sınıfları kullanmamızı gerektiren durumlar şunlardır;
* Bazen bir sınıfı başka bir sınıfa taşımak anlamsızdır. Özellikle bu sınıfa başka bir yerden erişilmeyecekse.
* Okunabilirliği ve kod yönetimini kolaylaştırır.
* Bir dizinde iki sınıf olduğunu düşünelim A ve B. B’nin A’nın üyelerine erişmesi gerekiyor bu olmasaydı A’daki üyeler private olarak tanımlanacaktı. B sınıfını A’nın içerisinde gizleyerek A’nın üyeleri private olarak tanımlanabilir ve B bu üyelere erişebilir. Hem de B kendisini dış dünyandan gizlemiş olur. Dolayısıyla Kapsüllemeyi (encapsulation) güçlendirir.



## Static İç Sınıflar



Aynı static metotlar gibi bir static iç sınıf, onu kapsayan sınıftaki değişken veya metoda doğrudan erişemez. Onlara sadece bir nesne referansıyla erişir.
Static iç sınıflara onu kapsayan sınıfın ismini kullanarak erişilir:


    
    DisSinif.StaticİcSinif



Örneğin bir static iç sınıftan nesne oluşturmak için şu söz dizimini kullanırız:


    
    DisSinif.StaticİcSinif icNesne  = new DisSinif.StaticİcSinif();

İç Sınıflar aynı metotlar ve değişkenler gibi bir iç sınıfta onu kapsayan sınıfın instance’i ile ilişkilendirilir ve nesnenin metot ve alanlarına doğrudan erişebilir. Ayrıca bir iç sınıf instance ile ilişkilendirildiğinden static üye tanımlayamaz.
İç Sınıfın intance’i sadece Dış Sınıfın instance’i ile var olur. İç Sınıftan bir nesne oluşturmak için önce Dış sınıftan bir nesne oluşturmalıyız.
  
    DisSinif disNesne = new DisSinif();
    DisSinif.IcSinif icNesne = disNesne.new IcSinif();



## Gölgeleme (Shadowing)
Eğer bir tip belirli bir scope içerisinde tanımlanırken onu kapsayan scope içerisinde aynı isme sahip bir tanım varsa, kapsayan scope’taki tanım gölgelenir. Örneğin bir iç sınıf ile dış sınıf aynı isme sahip iki değişken barındırıyorsa. Aşağıdaki örnek bu olayı açıklamaya yardımcı olacaktır.

    
    public class GolgeTesti {

    public int x = 0;

    class IcSinif {

        public int x = 1;

        void method(int x) {
            System.out.println("x = " + x);
            System.out.println("this.x = " + this.x);
            System.out.println("GolgeTesti.this.x = " + GolgeTesti.this.x);
        }
    }

    public static void main(String... args) {
    	GolgeTesti gt = new GolgeTesti();
    	GolgeTesti.IcSinif icSinif = gt.new IcSinif();
    	icSinif.method(23);
    }
}


Örneğin çıktısı şu şekilde:

    x = 23
    this.x = 1
    GolgeTesti.this.x = 0



Bu örnekte üç tane x tanımlanmıştır. Parametredeki x, İç Sınıfta bulunan x değişkeni ve Dış Sınıfta bulunan x değişkeni.
Parametre olan x, iç sınıfta bulunan x değişkenini gölgeledi. Sınıfa üye olan değişkeni referans göstermek için this kelimesini kullandık. İç Sınıftaki x değişkeni ise dış sınıftaki x değişkenini gölgeledi. Daha üst bir scope’da bulunan x değişkenine erişmek için ise sınıf isminin ardından this kelimesini kullandık. 
## Serialization
İç sınıfların serileştirilmesi kesinlikle tavsiye edilmez. Java derleyicisi iç sınıflar gibi bazı yapıları derlerken sentetik yapılar (synthetic constructs) oluşturur. Sentetik yapılar farklı Java derleyicilerinde çeşitlilik gösterebilir buda .class dosyalarının değişlik göstereceği anlamına gelir. Bundan dolayı eğer bir iç sınıfı serileştirip edip farklı JRE sürümünde deserialize ederseniz uyumluluk sorunlarıyla karşılaşırsınız.

