---
author: akursat
comments: true
date: 2014-11-08 08:27:44+00:00
layout: post
link: http://akursat.com/?p=93
slug: 11-5-metotlara-bilgi-gondermek
title: 11.5 - Metotlara Bilgi Göndermek
wordpress_id: 93
categories:
- Java
- Java Se
tags:
- argüman
- java
- java dersleri
- metot
- parametre
- pass
---

Metotları tanımlarken argümanların sayısını ve tipini bu metotlara belirtiriz.
Bu metotda bir kürenin hacmini pi ve yarıçap(r) parametrelerine göre hesaplayan bir metot hazırladım.Bu metot double pi ve r olmak üzere iki parametreye sahip.Metotlar ve constructorlar primitif (double, int vb.) yada referans tipinde (array, object vb.) parametreler alabilir.

Parametreler metot gövdesi içerisinde kullanılır ve çalışma zamanında argümanların değerlerini alır.
Bu örnekte kureninHacmi metodundaki parametreler, passinfo.kureninHacmi (Math.PI, 5) satırıda Math sınıfından gelen pi değeri ve 5 değeridir.Kısaca pi değeri Math.PI ve r değeride 5 olacaktır.

    
    public class PassingInformation {
    
    	public static void main(String[] args) {
    
    		PassingInformation passinfo = new PassingInformation();
    		System.out.println(passinfo.kureninHacmi(Math.PI, 5));
    
    	}
    
    	public double kureninHacmi(double pi, double r) {
    
    		double hacim = (4 / 3) * pi * Math.pow(r, 3);
    		return hacim;
    	}
    
    }





**Parametrelerin İsimlendirilmesi**




Şimdiye kadar tanımladığımız tüm parametrelere isim vermiştik.Metot gövdesi içerisinde kullanılan parametre, ismi bildirilen argümanı referans alır.

Burada dikkat edilmesi gereken konulardan biri metot içerisinde parametrelerle aynı isimde değişken tanımlanamaz.(yerel değişken) Bir diğer konuysa değişkenin ismi field'deki isimle aynı ise metodaki değişken field'i gölgeler.Yani  metot içerisinde  doğrudan kullanılmaz hale gelir. (Burada private int x,y satırı field alanıdır) Sınıfın field'ine ulaşmak içinse this keywordu kullanılır. (Sonraki yazılarda bu konuya değineceğiz)

    
    private int x, y;
    	
    	public void setSize(int x,int y) {
    		//...int x,y tanımlanamaz
    	}
    
    
