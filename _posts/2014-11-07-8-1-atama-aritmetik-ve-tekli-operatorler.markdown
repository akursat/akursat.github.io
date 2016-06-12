---
author: akursat
comments: true
date: 2014-11-07 20:54:36+00:00
layout: post
link: http://akursat.com/?p=51
slug: 8-1-atama-aritmetik-ve-tekli-operatorler
title: 8.1 - Atama, Aritmetik ve Tekli Operatörler
wordpress_id: 51
categories:
- Java
- Java Se
tags:
- java
- java dersleri
- operatör
- operatörler
- unary
---


<table cellpadding="3" width="100%" cellspacing="0" > 
<tbody >
<tr valign="TOP" >

<td width="37%" >


Atama Operatörleri



</td>

<td width="63%" >


= += -= *= /= %= >>= <<= &= ^= |=



</td>
</tr>
<tr valign="TOP" >

<td width="37%" >


Aritmetik Operatörler



</td>

<td width="63%" >


+ - * / % 



</td>
</tr>
<tr valign="TOP" >

<td width="37%" >


Unary (Tekli) Operatörler



</td>

<td width="63%" >


+ - ++ - - ! 



</td>
</tr>
</tbody>
</table>


**
**Atama, Aritmetik ve Tekli Operatörler bunlar nasıl kullanıldıklarını bilmiyorsanız kodları inceleyebilirsiniz.





    
    /*
     * www.akursat.com
     * @author   Adem Kürşat Uzun
     */
    
    public class AritmetikVeTekli {
    	public static void main(String[] args) {
    
    		// Atama operatörü = ,Sağdaki 60 hız değişkenine atandı.
    		int hız = 60;
    
    		/*+= işlemi hız = hız + 5 gibi düşünülebilir.Diğer tüm genişletiliş atama operatörleride benzer açılıma sahiptir.
    		*(-= *= /= %= >>= <<= &= ^= |=) bu operatörlerde benzer şekilde kullanılır.
    		* >> << ^ | gibi operatörleri bilmiyorsanız diğer yazıdan öğrenebilirsiniz. 
    		*/
    
    		hız+=5;
    		System.out.println("+= :"+hız);
    
    		int sonuc = 0;
    		int a = 10;
    
    		// Aritmetik + operatörü ile a ve 1 sayılarının toplamı
    		sonuc = a + 1;
    		System.out.println("a+1: " + sonuc);
    
    		// Aritmetik - operatörü ile a ve 1 sayılarının çıkarımı
    		sonuc = a - 1;
    		System.out.println("a-1: " + sonuc);
    
    		// Aritmetik * operatörü ile a ve 5 sayılarının çarpımı
    		sonuc = a * 5;
    		System.out.println("a*5: " + sonuc);
    
    		// Aritmetik / operatörü ile a sayısının 10 na bölümü
    		sonuc = a / 10;
    		System.out.println("a/10: " + sonuc);
    
    		// Aritmetik % operatörü ile a sayısının 6 bölümünden kalan
    		sonuc = a % 6;
    		System.out.println("a%6: " + sonuc);
    
    		/*
    		 * expr. expression(ifade) kısaltması prefix operatörden önce postfix
    		 * operatörden sonra işleme sokulur.
    		 */
    
    		// +expr Tekli operatörü
    		sonuc = +14;
    		System.out.println("+expr: " + sonuc);
    
    		// -expr Tekli operatörü
    		sonuc = -14;
    		System.out.println("-expr: " + sonuc);
    
    		// ++expr Tekli operatörü postfix gösterimde, sonuc değerini bir artır.
    		sonuc = 14;
    		sonuc++;
    		System.out.println("sonuc++: " + sonuc);
    
    		// --expr Tekli operatörü postfix gösterimde, sonuc değerini bir azalt.
    		sonuc = 14;
    		sonuc--;
    		System.out.println("sonuc--: " + sonuc);
    
    		// bollean afk(away from keyboard) adlı değişkenin değerini false
    		// atadım.
    		boolean afk = false;
    		System.out.println("afk: " + afk);
    
    		// afk değerini artık ! operatörü ile tersini aldık ve bunu tekrar afk
    		// değişkenine atadık.
    		afk = !afk;
    		System.out.println("!afk: " + afk);
    
    	}
    }


Çıktı:

    
    +=65
    a+1: 11
    a-1: 9
    a*5: 50
    a/10: 1
    a%6: 4
    +expr: 14
    -expr: -14
    sonuc++: 15
    sonuc--: 13
    afk: false
    !afk: true




#### Bir sonraki yazı [8.2 - İlişkisel ve Koşul Operatörleri](http://www.akursat.com/8-2-iliskisel-ve-kosul-operatorleri/)
