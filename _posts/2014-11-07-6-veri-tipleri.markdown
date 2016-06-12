---
author: akursat
comments: true
date: 2014-11-07 20:46:37+00:00
layout: post
link: http://akursat.com/?p=45
slug: 6-veri-tipleri
title: 6- Veri Tipleri
wordpress_id: 45
categories:
- Java
- Java Se
tags:
- byte
- int
- integer
- primitif
- primitive
- referans
- referans veri tipleri
- short
- veri tipleri
- wrapper
- wrapper class
---

Java programlama dilinde iki tür veri tipi vardır.Bunlar Primitive(primitif,ilkel) ve Referans dır.

**1. Primitif Veri Tipleri**



	
  * Javada tanımlı 8 primitif tip vardır.

	
  * Bu tipler Java dilinde önceden tanımlanmıştır.

	
  * Önceden tanımlanan kelimeler ayrılmıştır(reserved keyword) dolayısıyla değişken ismi olarak kullanamayız.


Sınır değerler dahildir.Yani byte max. 127 değerini alır.
<table cellpadding="3" width="100%" cellspacing="0" > 
<tbody >
<tr valign="TOP" >

<td width="23%" >**Veri Tipi**
</td>

<td width="77%" >**Açıklaması **
</td>
</tr>
<tr valign="TOP" >

<td width="23%" >byte
</td>

<td width="77%" >8 bit, -128 ile 127 arası değer alır.
</td>
</tr>
<tr valign="TOP" >

<td width="23%" >short
</td>

<td width="77%" >16 bit, -32.768 ile 32.767 arası değer alır.
</td>
</tr>
<tr valign="TOP" >

<td width="23%" >int
</td>

<td width="77%" >32 bit, -2.147.483.648 ile 2.147.483.647 arası değer alır.
</td>
</tr>
<tr valign="TOP" >

<td width="23%" >long
</td>

<td width="77%" >64 bit, -9.223.372.036.854.775.808 ile 9.223.372.036.854.775.808 arası değer alır.
</td>
</tr>
<tr valign="TOP" >

<td width="23%" >float
</td>

<td width="77%" >32 bit, kayan noktalı(floating point) değer
</td>
</tr>
<tr valign="TOP" >

<td width="23%" >double
</td>

<td width="77%" >64 bit, kayan noktalı değer
</td>
</tr>
<tr valign="TOP" >

<td width="23%" >boolean
</td>

<td width="77%" >Sadece iki değer alır true veya false. (1 bit bilgi içeriyor ama boyutu Jvm bağlı olarak değişebiliyor Jvm derslerine saklıyorum bu konuyu :)
</td>
</tr>
<tr valign="TOP" >

<td width="23%" >char
</td>

<td width="77%" >16 bit ,Unicode karekter
</td>
</tr>
</tbody>
</table>
Bunlar primitif tiplerimizdi şimdi bu kısımda karıştırılan birşey var **byte != Byte** benzer şekilde **int != Integer** vb. Javaya yeni başlayanlar bunların benzer şey olduğunu sanıyor oysa değil.Burayı düzeltelim, bunun adı Wrapper Class.

**2. Referans Veri Tipleri**



	
  * Sınıflar,Interface ler ve Dizileri içerir.

	
  * Herhangi bir referans tipinin default değeri null dir.

	
  * `String, Scanner, Random,int[], String[] ``vb. ``sınıflar.`

	
  * Primitif değişkenlerin değerleri saklanırken, referans değişkenlerin adresleri saklanır.


Wrapper sınıflar, primitif tiplerin nesne tipine dönüşmüş halleridir.Buna Collection sınıflarında ihtiyaç duyuyoruz.(ArrayList,Hashset,HashMap vb.) Ek olarak binary , octal ve hexadecimal dönüşümler içinde kullanılıyor.
Nesnelerden oluşan tiplerin başharfleri büyük harfle başlıyor.Bu şekilde ayırt edebiliriz.

Java'daki Wrapper Sınıfları:
<table cellpadding="3" width="100%" cellspacing="0" > 
<tbody >
<tr valign="TOP" >

<td width="23%" >**Veri Tipi**
</td>

<td width="77%" >**Constructor Parametleri **
</td>
</tr>
<tr valign="TOP" >

<td width="23%" >Byte
</td>

<td width="77%" >byte veya String
</td>
</tr>
<tr valign="TOP" >

<td width="23%" >Short
</td>

<td width="77%" >short veya String
</td>
</tr>
<tr valign="TOP" >

<td width="23%" >Integer
</td>

<td width="77%" >int veya String
</td>
</tr>
<tr valign="TOP" >

<td width="23%" >Long
</td>

<td width="77%" >long veya String
</td>
</tr>
<tr valign="TOP" >

<td width="23%" >Float
</td>

<td width="77%" >float,double veya String
</td>
</tr>
<tr valign="TOP" >

<td width="23%" >Double
</td>

<td width="77%" >double veya String
</td>
</tr>
<tr valign="TOP" >

<td width="23%" >Boolean
</td>

<td width="77%" >boolean veya String
</td>
</tr>
<tr valign="TOP" >

<td width="23%" >Character
</td>

<td width="77%" >char
</td>
</tr>
</tbody>
</table>

    
    Integer intObj = new Integer (25); // int parametreli
    
    Integer intObj2 = new Integer ("25"); // String parametreli




_**Not:**Eğer Constructor ne olduğunu bilmiyorsanız ve tam olarak wrapper sınıfları anlamadıysanız atlayabilirsiniz.Sadece ikisinin farklı olduğunun bilinmesi yeterli._
