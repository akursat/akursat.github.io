---
author: akursat
comments: true
date: 2014-11-07 20:56:57+00:00
layout: post
link: http://akursat.com/?p=53
slug: 8-2-iliskisel-ve-kosul-operatorleri
title: 8.2 - İlişkisel ve Koşul Operatörleri
wordpress_id: 53
categories:
- Java
- Java Se
tags:
- and
- eşit değildir
- eşittir
- if
- if else
- java
- java dersleri
- operatör
- or
---

İlişkisel operatörler, bir operandın diğer operanddan büyük mü, küçük mü, büyük eşit mi, küçük eşit mi,eşit mi ve eşit değil mi olup olmadığına cevap verir.




&& ve | | operatörleri sırayla koşullu ve,koşullu veyayı ifade eder.Bu operatörler kısa devre oluştururlar eğer ikinci operand (örneğin (deger1 == 3) && (deger2 == 6) && sonra gelen kısım) gerekiyorsa işleme sokulur. IliskiselVeKosul.java dosyası üzerinden bu durumu daha iyi anlayabilirsiniz.
?: operatörü ternary (üçlü) operatörü olarakta bilinir.Üç operand kullanır.if-else yapısının kısaltılmış hali gibi düşünülebilir.



<table cellpadding="3" width="100%" cellspacing="0" >
<tbody >
<tr valign="TOP" >

<td width="50%" >


İlişkisel (Relational) Operatörler



</td>

<td width="50%" >> < >= <= == !=
</td>
</tr>
<tr valign="TOP" >

<td width="50%" >


Koşullu Operatörler



</td>

<td width="50%" >&& || ?:
</td>
</tr>
</tbody>
</table>

    
    /*
     * www.akursat.com
     * @author   Adem Kürşat Uzun
     */
    public class IliskiselVeKosul {
    
    	public static void main(String[] args) {
    
    		/*if yapısını bilmenize gerek yok yorum satırlarında ne iş yaptığını
    		 * açıkladım.
    		 */
    
    		int sayi1 = 5;
    		int sayi2 = 10;
    
    		// sayi1 değişkeni sayi2 değişkenine eşitse ekrana sayi1 == sayi2 yaz.
    		if (sayi1 == sayi2) {
    			System.out.println("sayı1 == sayi2");
    		}
    
    		// sayi1 değişkeni sayi2 değişkenine eşit değilse ekrana sayi1 != sayi2
    		// yaz.
    		if (sayi1 != sayi2) {
    			System.out.println("sayı1 != sayi2");
    		}
    
    		// sayi1 değişkeni sayi2 değişkeninden küçükse ekrana sayi1 < sayi2 yaz.
    		if (sayi1 < sayi2) {
    			System.out.println("sayı1 < sayi2");
    		}
    
    		// sayi1 değişkeni sayi2 değişkeninden büyükse ekrana sayi1 > sayi2 yaz.
    		if (sayi1 > sayi2) {
    			System.out.println("sayı1 > sayi2");
    		}
    
    		// sayi1 değişkeni sayi2 değişkeninden küçük eşitse ekrana sayi1 <=
    		// sayi2 yaz.
    		if (sayi1 <= sayi2) {
    			System.out.println("sayı1 <= sayi2");
    		}
    		// sayi1 değişkeni sayi2 değişkeninden büyük eşitse ekrana sayi1 >=
    		// sayi2 yaz.
    		if (sayi1 >= sayi2) {
    			System.out.println("sayı1 >= sayi2");
    		}
    
    		int deger1 = 3;
    		int deger2 = 6;
    
    		// deger1=3 ve deger2=6 ise ekrana 'deger1 =3 ve deger2 =6' yaz.
    		if ((deger1 == 3) && (deger2 == 6)) {
    			System.out.println("deger1 =3 ve deger2 =6");
    		}
    
    		// deger1=3 veya deger2=5 ise ekrana 'deger1=3 veya deger2=5' yaz.
    		if ((deger1 == 3) || (deger2 == 5)) {
    			System.out.println("deger1=3 veya deger2=5");
    		}
    
    		/*
    		 * ?: Koşul operatörüdür. if-else yapısının kısa hali gibi
    		 * düşünülebilir. ternary(üçlü) operatörü olarakta bilinir çünkü üç
    		 * operand kullanır.(örnekte:kosul,x ve y bu üç operandtır.)
    		 */
    		int x = 5;
    		int y = 10;
    		int kordinat;
    		boolean kosul = false;
    
    		// Kosul true ise kordinat = x değilse kordinat = y olsun.
    		kordinat = kosul ? x : y;
    		System.out.println(kordinat);
    
    	}
    
    }




#### Bir sonraki yazı [8.3 Bitwise ve Bit Shift Operatörleri](http://www.akursat.com/8-3-bitwise-ve-bit-shift-operatorleri/)
