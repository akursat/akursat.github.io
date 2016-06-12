---
author: akursat
comments: true
date: 2016-01-30 14:38:28+00:00
layout: post
link: http://akursat.com/?p=271
slug: 13-6-static-metotlar-ve-sabitler
title: 13.6 - static metotlar ve sabitler
wordpress_id: 271
categories:
- Java
- Java Se
tags:
- constant
- final
- java
- java dersleri
- metot
- sabitler
- static
---

public class Bisiklet {   
        private int kadans;
        private int vites;
        private int hiz;
        private int id;
        private static int bisikletSayisi = 0;      
       public Bisiklet(int kadansBaslat, int vitesiBaslat, int hiziBaslat) {
          vites = vitesiBaslat;
          kadans = kadansBaslat;
          hiz = hiziBaslat;
            // önce bisiklet sayısını artır sonra id’ye ata.
            id = ++bisikletSayisi;
        }
        // id’yi dönder
        public int getID() {
            return id;
        }
            ...
    }




## Static metotlar


Java programlama dili static değişkenlerin yanında static metotları da destekler. Static metotlar çoğunlukla static değişkenleri çağırmak için kullanılır. Yukarıdaki Bisiklet sınıfı için şu metodu yazabiliriz.

    
    public static int bisikletSayisiniGetir( {
    return bisikletSayisi;      
    }


<!-- more -->

Static metotlar sınıf adıyla doğrudan çağrılabilir.

    
    Bisiklet.bisikletSayisiniGetir()


static metotlar yine static değişkenler gibi nesneyle de çağırabilirsiniz ama bu yöntem tavsiye edilmez.

    
    bisiklet1.bisikletSayisiniGetir()





	
  * static olmayan metotlar static olmayan değişkenlere ve metotlara doğrudan erişebilir.

	
  * static olmayan metotlar static değişkenlere ve static metotlara da doğrudan erişebilir.

	
  * static metotlar static değişkenlere ve static metotlara doğrudan erişebilir.

	
  * static metotlar static olmayan metotlara ve static olmayan değişkenlere doğrudan erişemez. Erişebilmesi için referans kullanması gerekir.(bisiklet1.bisikletSayisiniGetir() olduğu gibi)

	
  * Ayrıca this’i static metot içerisinde kullanamayız.




## Sabitler


Static ile final kelimelerinin birleşimi sabit tanımlamak için kullanılır. final, değişkenin değerinin değişmeyeceğini belirtir.
Aşağıdaki örnekte PI adli bir sabit oluşturduk.Bu değişkenin değeri yaklaşık pi değerini almıştır.

    
    static final double PI = 3.14159265358;


Bu şekilde tanımlanan sabitler tekrar atanamaz. Eğer bunu yapmayı denerseniz derleyici hatası alırsınız. Derleyici sabitin isminin geçtiği her yeri girdiğiniz sabit değerinizle değiştirir.
