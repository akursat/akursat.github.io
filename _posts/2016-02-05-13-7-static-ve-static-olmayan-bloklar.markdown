---
author: akursat
comments: true
date: 2016-02-05 19:48:16+00:00
layout: post
link: http://akursat.com/?p=278
slug: 13-7-static-ve-static-olmayan-bloklar
title: 13.7 - static ve static olmayan bloklar
wordpress_id: 278
categories:
- Java
- Java Se
tags:
- blok
- initialize
- java
- java dersleri
- scope
- static
---

## Blok kullanmadan initialize


Bildiğiniz gibi değişkenleri aşağıdaki örnekteki gibi initialize edebiliriz.

    
    public class Test{
        public int nesneSayisi = 0;
        private boolean  cevap  = true; 
    }


Atanacak değer erişilebilir olduğunda bu yöntem kullanılabilir. Eğer atama işlemi bazı mantık işlemleri içeriyorsa (bir dizinin doldurulması ya da hata yönetimi gibi) constructor içerisinde initialize etmemiz mantıklı olacaktır.

Aynı yeteneği static değişkenlerde sağlamamız için static bloklar vardır. Bildiğiniz gibi static değişkenler için bu işlemi constrator içerisinde initialize etmemiz çok mantıksız olacaktır. Bu durumu kavramadıysanız bir önceki static değişkenler konusuna gözatın.


## static bloklar


static bloklar normal blokların önüne static konulmasıyla oluşan bloklardır.

    
    static {
    
    // kodlar buraya gelecek
    
    }


Bir sınıfta birden fazla static blok bulunabilir. Static bloklar kaynak koddaki yer alan sıralarıyla yürütülürler. static bloklar constructor gibi sınıf oluşturulduğunda yürütülürler. Constructor’lardan önce yürütülür. Bu bloklar static değişkenleri initialize etmek için kullanılabilirler.


## static olmayan bloklar


Bunlar da constructor’lardan önce yürütülür.

Değişkenleri normalde constructor içerisinde veya yukarıdaki gibi blok kullanmadan initialize ederiz. Buna ek olarak iki farklı yol daha vardır.

Birincisi static olmayan bloklar.

    
    {
    
    //kodlar buraya gelecek
    
    }


Java static olmayan blokları her bir constructor’a kopyalar. Static olmayan bu blokları kullanılarak çok sayıdaki constructor için aynı initialize işlemini yapmamıza gerek kalmaz.

Şimdi bu öğrendiklerimizi örnek üzerinde uygulayalım.

    
    public class Test{
        static
        {
            System.out.println("Static Blok");
        }
        
        {
            System.out.println("Static Olmayan Blok");
        }
        
        public Test() {
            System.out.println("Test...");
        }
        public static void main(String[] args) {
            Test t1 = new Test();
            Test t2 = new Test();
        }
      }


Örneğimizin çıktısı şu şekilde:

    
    Static Blok
    Static Olmayan Blok
    Test...
    Static Olmayan Blok
    Test...
