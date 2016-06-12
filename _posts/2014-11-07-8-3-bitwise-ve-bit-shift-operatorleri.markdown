---
author: akursat
comments: true
date: 2014-11-07 21:00:34+00:00
layout: post
link: http://akursat.com/?p=55
slug: 8-3-bitwise-ve-bit-shift-operatorleri
title: 8.3 - Bitwise ve Bit Shift Operatörleri
wordpress_id: 55
categories:
- Java
- Java Se
tags:
- bit shift
- bitwise
- java
- java dersleri
- operatör
---

<table cellpadding="3" width="100%" cellspacing="0" > 
<tbody >
<tr valign="TOP" >

<td width="50%" >


Bitwise



</td>

<td width="50%" >


~ & | 



</td>
</tr>
<tr valign="TOP" >

<td width="50%" >


Bit Shift



</td>

<td width="50%" >


<< >> >>>



</td>
</tr>
</tbody>
</table>


Bitwise ve Bit shift operatörleri genellikle az kullanılır.Bu operatörleri BitwiseAndBitShift.java adlı örnek uygulamasından öğrenebilirsiniz.Örneğin çıktısı şöyle;




    
    a :00000000000000000000000010000000
    
    ~a :11111111111111111111111101111111
    
    a :00000000000000000000000010000000
    
    b :00000000000000000000000011001011
    
    -------------------------------------
    
    a&b :00000000000000000000000010000000
    
    a|b :00000000000000000000000011001011
    
    a^b :00000000000000000000000001001011
    
    a<<1 :00000000000000000000000100000000
    
    b>>2 :00000000000000000000000000110010
    
    a>>>3:00000000000000000000000000010000





Bu çıktı üzerinden de işlemler kolayca anlaşılabilir:






	
  * 


~ operatörü bitleri tersine çevirir birler sıfır,sıfırlar bir olur.




	
  * 


& operatörü iki operantı and(ve) işlemine tabi tutar.




	
  * 


| operatörü iki operantı or(veya) işlemine tabi tutar.




	
  * 


^ operatörü iki operantı xor işlemine tabi tutar.a ve b aynı biti taşıyorsa 0 taşımıyorsa 1 atar.




	
  * 


<< operatörü sağındaki operand kadar sola bit kaydırır.Örneğin a<<1 ifadesi a'nın bitlerini 1 bit sola kaydıracaktır.




	
  * 


>> operatörü sağındaki operand kadar sağa bit kaydırır.




	
  * 


>>> operatörü sağındaki operand kadar sağa kaydırır ve soldan kalan yerlere 0 bitini atar.







BitwiseAndBitShift.java dosyası, çıktı formatının anlaşılabilir olması için şuana kadar değinmediğim dönüşüm ve formatlama işlemlerini barındırıyor.Bu kısımları atlayabilirsiniz.





    
    /*
     * www.akursat.com
     * @author   Adem Kürşat Uzun
     */
    
    public class BitwiseAndBitShift {
    
    	public static void main(String[] args) {
    
    		// java se 7 ile gelen 0b literalini kullanarak sayi atama.
    		int a = 0b1000_0000;
    		int a_t = ~a; // 0b0111_1111;
    
    		int b = 0b1100_1011;
    
    		int c = 0;
    
    		/*
    		 * Integer.toString,String.format metotlarını sayı gösteriminde,boşluk
    		 * yerine 0 yazması için kullandım.Bu metotları
    		 * kullanmayabilirsiniz.Çıktının düzenli tutulması ve kolay
    		 * anlaşılabilmesi için yazıldı.
    		 */
    
    		String astr = Integer.toString(a);
    		String a_tstr = Integer.toString(a_t);
    		String bstr = Integer.toString(b);
    
    		String andStr = Integer.toBinaryString(c);
    		String orStr = Integer.toBinaryString(c);
    		String xorStr = Integer.toBinaryString(c);
    		String leftShift = Integer.toBinaryString(c);
    		String rightShift = Integer.toBinaryString(c);
    		String rightZero = Integer.toBinaryString(c);
    
    		astr = astr.format("%32s", Integer.toBinaryString(a)).replace(" ", "0");
    		bstr = bstr.format("%32s", Integer.toBinaryString(b)).replace(" ", "0");
    
    		a_tstr = astr.format("%32s", Integer.toBinaryString(a_t)).replace(" ",
    				"0");
    
    		// a ve b sayılarını mantıktaki and işlemine tabi tutar.
    		c = a & b;
    		andStr = andStr.format("%32s", Integer.toBinaryString(c)).replace(" ",
    				"0");
    
    		// a ve b sayılarını mantıktaki or işlemine tabi tutar.
    		c = a | b;
    		orStr = orStr.format("%32s", Integer.toBinaryString(c)).replace(" ",
    				"0");
    
    		// a ve b sayılarını mantıktaki xor işlemine tabi tutar.
    		c = a ^ b;
    		xorStr = orStr.format("%32s", Integer.toBinaryString(c)).replace(" ",
    				"0");
    
    		// a sayısının bitlerini 1 bit sola kaydırır.(İstediğiniz koşulu
    		// girebilirsiniz örn 2,3 vb)
    		c = a << 1;
    		leftShift = leftShift.format("%32s", Integer.toBinaryString(c))
    				.replace(" ", "0");
    
    		// b sayısın bitlerini 2 bit sağa kaydırır.(İstediğiniz koşulu
    		// girebilirsiniz örn 2,3 vb)
    		c = b >> 2;
    		rightShift = rightShift.format("%32s", Integer.toBinaryString(c))
    				.replace(" ", "0");
    
    		// a sayısının bitlerini 3 sağa kaydırır ve kaydırdığı basamak kadar 0
    		// ekler(soldan)
    		c = a >>> 3;
    		rightZero = rightZero.format("%32s", Integer.toBinaryString(c))
    				.replace(" ", "0");
    
    		System.out.println("a    :" + astr);
    		System.out.println("~a   :" + a_tstr);
    
    		System.out.println("");
    		System.out.println("a    :" + astr);
    		System.out.println("b    :" + bstr);
    		System.out.println("-------------------------------------");
    		System.out.println("a&b  :" + andStr);
    		System.out.println("a|b  :" + orStr);
    		System.out.println("a^b  :" + xorStr);
    		System.out.println("a<<1 :" + leftShift);
    		System.out.println("b>>2 :" + rightShift);
    		System.out.println("a>>>3:" + rightZero);
    
    	}
    }




Bir sonraki yazı [**8.4 instanceof Operatörü**](http://www.akursat.com/8-4-instanceof-operatoru/)

