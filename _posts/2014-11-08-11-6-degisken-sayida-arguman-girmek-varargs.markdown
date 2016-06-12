---
author: akursat
comments: true
date: 2014-11-08 08:28:43+00:00
layout: post
link: http://akursat.com/?p=97
slug: 11-6-degisken-sayida-arguman-girmek-varargs
title: 11.6 - Değişken Sayıda Argüman Girmek (Varargs)
wordpress_id: 97
categories:
- Java
- Java Se
tags:
- aşırı yükleme
- java
- java dersleri
- metot signature
- overload
- signature
- varargs
---

Bazen çok sayıda değer içeren argümanları kabul eden metotlar yazmanız gerekebilir.Bu durumda diziler kullanılabilir.


    
    public int topla(int[] list) {
    		 
    	    int toplam = 0;
    	    for (int i=0; i < list.length; i++) {
    	    	toplam += list[i];
    	    }
    	    return toplam;
    	 
    	}


Dizilerin kullanımı yerine,bir değer seçenekte farklı sayıda argüman alan birkaç overloaded metot yazmaktır.

    
    public int topla(int a, int b) {
    	    return a + b;
    	}
    	 
    	public int topla(int a, int b, int c) {
    	    return a + b + c;
    	}
    	 
    	public int topla(int a, int b, int c, int d) {
    	    return a + b + c + d;
    	}
    	 
    	public int topla(int a, int b, int c, int d, int e) {
    	    return a + b + c + d + e;
    	}


Okunuş olarak daha kolay olsada dizi kullanımından daha iyi bir yol değil.Birde bu metotların devam ettiğini düşünün!Java 5 de gelen varargs seçeneği bu dizi işlemini gizliden yaparak işimizi kolaylaştırıyor ve daha okunabilir bir kod elde etmemizi sağlıyor.

    
    public int topla(int...list) {
    		 
    	    int toplam = 0;
    	    for (int item : list) {
    	    	toplam += item;
    	    }
    	    return toplam;
    	 
    	}


Bu üç nokta metot signature'a int tipinde istenilen sayıda değer girilebilir diyor.Sadece bu metotla artık

    
    topla(1,2,3);
    topla(15,23,1,2,3);







şeklinde argümanlar gönderebilirsiniz.



