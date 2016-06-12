---
author: akursat
comments: true
date: 2014-11-07 21:05:41+00:00
layout: post
link: http://akursat.com/?p=57
slug: 8-4-instanceof-operatoru
title: 8.4 InstanceOF Operatörü
wordpress_id: 57
categories:
- Java
- Java Se
tags:
- extends
- implement
- instanceof
- java
- java dersleri
- new
---

Öncelikle instance nedir bunu açıklayalım.instance(örnek) kelimesi object (nesne) kelimesiyle eşanlamlı olarak kullanılır.Genel olarak özel bir tür nesne hakkında konuşuyorsak (örneğin Aile) instance kelimesi.Genel olarak konuşuyorsak nesne(object) kelimesi kullanılır.


_Dikkat:Bu yazıda new,extends, implement vb. kavramlar hakkında bilgi verilmedi.Bu konular hakkında bilginiz yoksa ve anlamakta zorluk çekiyorsanız bu konuyu atlayabilirsiniz.oop konusunda bu terimlerden bahsedilecektir._


instaceof operatörü ile nesnelerin(object) bir sınıfın, bir altsınıfın (subclass) veya implement uygulanmış bir sınıfın instance i olup olmadığını öğrenebiliriz.
Bu kısım kafa karıştırıcı olmuş olabilir InstanceOf.java nın çıktısı üzerinden bu durumu daha kolay anlayabiliriz.(InstanceOf.java dosyasının kodlarına bakın.)
**Çıktı:**




true
false
false
true
true
true






	
  * 


Aile aile = **new** Aile(); satırı ile Aile sınıfından aile isminde bir instance oluşturduk.Bundan dolayı aile instaceof Aile satırı True değerini dönderir.




	
  * 


aile instanceof Cocuk satırı False dönderir çünkü Cocuk sınıfından aile adında bir instance oluşturmadık. 




	
  * 


**class** Aile {} sınıfı MyInterface interfaceni implement etmediğinden aile instanceof MyInterface False dönderir.




	
  * 


Cocuk sınıfı Aile sınıfından extend olduğundan cocuk instanceof Aile satırı True dönderir.




	
  * 


Cocuk cocuk = **new** Cocuk(); satırı ile Cocuk sınıfından cocuk isminde bir instance oluştuğundan cocuk instanceof Cocuk satırı True dönderir.




	
  * 


**class** Cocuk **extends** Aile **implements** MyInterface {}  Cocuk sınıfı MyInteface i implement ettiğinden cocuk instanceof MyInterface satırı True döner.






    
    /*
     * www.akursat.com
     * @author   Adem Kürşat Uzun
     */
    public class InstanceOf {
    	public static void main(String[] args) {
    		/*
    		 * Eğer oop konusunda bilginiz varsa aşağıdaki örnekler kafanızı
    		 * karıştırmıyacaktır.Yoksa bu bölümü atlayın. instanceof operatörü ile
    		 * nesnelerin bir sınıfın,bir altsınıfın(subclass) veya implement
    		 * uygulanmış bir sınıfın (belirli bir interface'i) instance'i olup
    		 * olmadığını öğrenebiliriz.
    		 */
    
    		Aile aile = new Aile();
    		Cocuk cocuk = new Cocuk();
    
    		System.out.println(aile instanceof Aile);
    		System.out.println(aile instanceof Cocuk);
    		System.out.println(aile instanceof MyInterface);
    
    		System.out.println(cocuk instanceof Aile);
    		System.out.println(cocuk instanceof Cocuk);
    		System.out.println(cocuk instanceof MyInterface);
    
    	}
    }
    
    /*
     * Bu kısım instanceof örneği için oluşturulmuştur extends,implement gibi
     * kavramları bilmiyorsanız bu kısmı atlayabilirsiniz.
     */
    
    class Aile {
    }
    
    class Cocuk extends Aile implements MyInterface {
    }
    
    interface MyInterface {
    }
