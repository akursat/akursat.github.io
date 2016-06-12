---
author: akursat
comments: true
date: 2014-11-07 20:52:29+00:00
layout: post
link: http://akursat.com/?p=49
slug: 8-operatorler
title: 8 - Operatörler
wordpress_id: 49
categories:
- Java
- Java Se
tags:
- infix
- java
- java dersleri
- new
- operatör
- operatörler
- postfix
- prefix
- ternary
---

Operatörler özel sembollerden oluşur bunlarla özel işlemler yapabilirsiniz.(Örneğin toplama, çıkarma vb.) Operatörler bir,iki veya üç operand alır ve sonuç dönderir.(operand işleme sokulan ifade örneğin 3+5 de 3 ve 5 operanddır.)


Tablodaki operatörler öncelik sırasına göre yerleştirilmiştir.Öncelik sırası aynı olan operatörlerden ilk sırada yer alan önce işletilir.Bildiğimiz matematik öncelik sırası gibi düşünülebilir.Infix, postfix ve prefix kavramlarına bu konuda değinmedim.++ - - operatörlerinin bir ifadenin solunda yada sağında olmasının ne gibi farklılıklar oluşturduğunu PrefixPostfix.java adlı örnekte kısaca acıklayacağım.
<table cellpadding="3" width="100%" cellspacing="0" > 
<tbody >
<tr >

<td colspan="2" width="100%" valign="TOP" >


**Öncelik Sırasına Göre Operatörler**



</td>
</tr>
<tr valign="TOP" >

<td width="10%" >


1



</td>

<td width="90%" >


`[] () . `



</td>
</tr>
<tr valign="TOP" >

<td width="10%" >


2



</td>

<td width="90%" >


++ - - ! ~ (type) new



</td>
</tr>
<tr valign="TOP" >

<td width="10%" >


3



</td>

<td width="90%" >


* / %



</td>
</tr>
<tr valign="TOP" >

<td width="10%" >


4



</td>

<td width="90%" >


+ -



</td>
</tr>
<tr valign="TOP" >

<td width="10%" >


5



</td>

<td width="90%" >


`>> >>> << `



</td>
</tr>
<tr valign="TOP" >

<td width="10%" >


6



</td>

<td width="90%" >


**> >= < <= **`instanceof`



</td>
</tr>
<tr valign="TOP" >

<td width="10%" >


7



</td>

<td width="90%" >


== !=



</td>
</tr>
<tr valign="TOP" >

<td width="10%" >


8



</td>

<td width="90%" >


&



</td>
</tr>
<tr valign="TOP" >

<td width="10%" >


9



</td>

<td width="90%" >


`^`



</td>
</tr>
<tr valign="TOP" >

<td width="10%" >


10



</td>

<td width="90%" >


|



</td>
</tr>
<tr valign="TOP" >

<td width="10%" >


11



</td>

<td width="90%" >


&&



</td>
</tr>
<tr valign="TOP" >

<td width="10%" >


12



</td>

<td width="90%" >


| |



</td>
</tr>
<tr valign="TOP" >

<td width="10%" >


13



</td>

<td width="90%" >


?:



</td>
</tr>
<tr valign="TOP" >

<td width="10%" >


14



</td>

<td width="90%" >


`= += -= *= /= %= &= ^= |= <<= >>= >>>=`



</td>
</tr>
</tbody>
</table>


_Tabloda;_






	
  * (type) tip dönüşümünü



	
  * ' . ' üye elemanlarına erişmek için kullanılan operatörü




belirtmektedir.






	
  * Tekli operatörler sadece bir adet operand alır.




	
  * Atama operatörlerleri,tekli operatörler, new, (type) ve ?: operatörü sağdan sola işleme sokulurken diğer operatörler soldan sağa işlenir.




	
  * ?: operatörü ternary(üçlü) operatörü olarakda bilinir.Üç operand kullanır.







Tüm örnekleri tek sayfada toplayınca çok karışık bir görünüm oluştu bende konuyu bölümlendirme kararına vardım.Herbir operatörün örnekler üzerinden gösterimlerine:





#### **[8.1 Atama, Aritmetik ve Tekli Operatörler](http://www.akursat.com/8-1-atama-aritmetik-ve-tekli-operatorler/)**

** [8.2 İlişkisel ve Koşul Operatörleri](http://www.akursat.com/8-2-iliskisel-ve-kosul-operatorleri/)**

** [8.3 Bitwise ve Bit Shift Operatörleri](http://www.akursat.com/8-3-bitwise-ve-bit-shift-operatorleri/)**

[** 8.4 instanceof Operatörü**](http://www.akursat.com/8-4-instanceof-operatoru/)


yazılarından ulaşabilirsiniz.
