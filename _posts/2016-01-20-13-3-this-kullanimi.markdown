---
author: akursat
comments: true
date: 2016-01-20 14:40:15+00:00
layout: post
link: http://akursat.com/?p=251
slug: 13-3-this-kullanimi
title: 13.3 - this kullanımı
wordpress_id: 251
categories:
- Java
- Java Se
tags:
- constructor
- java
- java dersleri
- nesne
- this
---

Bir metodun veya constructor’ın içerisinde this kelimesi mevcut nesneyi (kendisini) referans eder. Mevcut nesnenin herhangi bir üyesini metot içerisinde veya constructor’da this ile çağırabilirsiniz.
Burada mevcut nesne kavramı tam olarak anlaşılmalı. Burada mevcut nesneden kasıt o sınıfın kendisinden oluşacak nesne. Diğer bir deyişle kendisi. Bunun için pyhthon self ifadesini kullanıyor.


## **this ile Field çağırımı**


Field ile bir metot ya da constructor’ın parametresi çakışdığı durumlarda this kullanılır. Bu yöntem çok sık kullanılır.
Örneğin Point sınıfı aşağıdaki şekilde yazılabilir

    
    public class Point {
        public int x = 0;
        public int y = 0;
            
        //constructor
        public Point(int a, int b) {
            x = a;
            y = b;
        }
    }


<!-- more -->

ama aynı zamanda aşağıdaki şekilde de yazabiliriz

    
    public class Point {
        public int x = 0;
        public int y = 0;
            
        //constructor
        public Point(int x, int y) {
            this.x = x;
            this.y = y;
        }
    }


Constructur içerisindeki x, field içerisindeki x ile çakıştığından bu sorunu this kullanarak çözdük. Field içerisindeki x’e erişmek için this.x kullandık.


## **this ile Constructor kullanma**


Bir constructor içerisinde aynı sınıfın diğer constructor’ını çağırabilirsiniz.
Örneğin;

    
    public class Dikdortgen {
        private int x, y;
        private int genislik, yukseklik;
            
        public Dikdortgen() {
            this(0, 0, 1, 1);
        }
        public Dikdortgen(int genislik, int yukseklik) {
            this(0, 0, genislik, yukseklik);
        }
        public Dikdortgen(int x, int y, int genislik, int yukseklik) {
            this.x = x;
            this.y = y;
            this.genislik = genislik;
            this.yukseklik = yukseklik;
        }
        ...
    }


Bu sınıf birden fazla constructor içeriyor. Her bir constructor Dikdortgen sınıfının değişkenlerini initialize ediyor. Örnekte görüldüğü gibi hiçbir argüman almayan constructor 1x1 boyutlarında ve 0,0 kordinatlarında bir Dikdörtgen oluşturur. İki argüman alan constructor ise dört argüman alan constructor’ı çağırıyor. Bu çağırımı yaparken kordinat değerlerini 0,0 olarak gönderiyor. Daha öncede belirtiğimiz gibi derleyici argüman sayısı ve tipine bakarak hangi constructor’ı çağıracağına karar veriyor.
Eğer bu yapıyı kullanırsanız diğer constructor çağırımı constructor içerisinde ilk satırda olmalı.

Bunların dışında da this’in farklı kullanımları vardır.
