---
author: akursat
comments: true
date: 2016-01-30 14:25:04+00:00
layout: post
link: http://akursat.com/?p=264
slug: 13-5-static-kullanimi
title: 13.5 - static kullanımı
wordpress_id: 264
categories:
- Java
- Java Se
tags:
- class field
- field
- java
- java dersleri
- static
- static field
---

Bu bölümde static ile oluşturulmuş değişken ve metotları inceleyeceğiz.
Bir sınıftan birden fazla nesne oluşturduğunuzda bu her nesneye ait değişkenlerin birer kopyası oluşur. Her biri için bellekte ayrı yer oluşturulur. Örneğin daha önce kullandığımız Bisiklet sınıfından bisiklet1 ve bisiklet2 adında iki nesne oluşturursak bu iki nesnede kendisine ait hiz ve vites gibi değişkenlere sahip olacaktır. Yani bellekte iki tane hiz ve vites değişkeni yer alacaktır.
Bazen bir değişkenin tüm nesneler için ortak olmasını isteyebilirsiniz. İşte bu durum static ile sağlanır. static kullanan field’ler static field veya class field olarak adlandırılır.  static olmayan field’ler nesneyle ilişkiliyken static field’ler sınıfla ilişkilidir.

<!-- more -->

Bellekte sabit yeri olan static değişkenini, bir sınıfın her bir nesnesi paylaşır. Herhangi bir nesne bu değişkenin değerini değiştirebilir. Ayrıca static değişkenlerin değerleri nesne oluşturmadan da değiştirilebilir.
Örneğin birden fazla Bisiklet nesnesi oluşturmak ve her birine bir seri numarası atamak istediğimizi düşünelim. Bu id numarası her bir nesne için eşsiz olsun. Aynı zamanda kaç tane Bisiklet nesnesi oluşturulduğunu tutalım ki bunu kullanarak bir sonraki id belirleyelim.

    
    public class Bisiklet {
            
        private int kadans;
        private int vites;
        private int bisiklet;
            
        // nesnenin id’sini tutan değişken
        private int id;
        
        // oluşturulan her bir bisiklet nesnesini tutan static değişken
        private static int bisikletSayisi = 0;
            ...
    }


static değişkenler sınıfın kendi ismiyle çağrılabilirler

    
    Bisiklet.bisikletSayisi


static değişkenleri aşağıdaki şekilde de çağırabilirsiniz

    
    Bisiklet bisiklet1 = new Bisiklet()
    bisiklet1.bisikletSayisi


Bu yöntem tavsiye edilmez çünkü static değişkenler ile static olmayan değişkenler arasında görülebilir fark bırakmak programcıların işini kolaylaştırır.

Daha önce kullandığımız Bisiklet sınıfını güncelleyelim. Bisikletin constructor’ını id artırmak için kullanalım.

    
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


Bir sonraki ders static metotlarla bu konuyu devam edeceğiz.
