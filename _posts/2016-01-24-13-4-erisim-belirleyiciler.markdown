---
author: akursat
comments: true
date: 2016-01-24 09:34:01+00:00
layout: post
link: http://akursat.com/?p=255
slug: 13-4-erisim-belirleyiciler
title: 13.4 - Erişim Belirleyiciler
wordpress_id: 255
categories:
- Java
- Java Se
tags:
- default
- erişim belirleyici
- java
- java dersleri
- modifier
- package-private
- private
- protected
- public
---

Erişim kontrolü için iki seviye vardır;
Sınıf seviyesinde - public veya package-private (doğrudan belirtilmez)
Üye seviyesinde - public, private, protected veya package-private (doğrudan belirtilmez)

Bir sınıf public ile tanımlanabilir. Bu durumda sınıf  her yerdeki tüm diğer sınıflardan erişebilir. Eğer bir sınıfın belirleyicisi yoksa (default, diğer bir adıyla package-private) sadece kendi içerisindeki paketi içerisinde erişilebilir. (paketler benzer işleri yürüten sınıfların bulunduğu gruplardır daha sonraki derse bundan bahsedilecek)

Üye seviyesi sınıfın içerisindeki değişken ve metotlar için yapılan bir adlandırmadır.
Üye seviyesinde public ve package-private yine aynı amaçlar için kullanabilirsiniz. Bunların dışında private ve protected olmak üzere iki erişim belirleyici daha vardır. private üyeye sadece kendi sınıfında erişebileceğini belirtir. protected ise üyenin sadece kendi paketinden erişebileceğini (package-private gibi) ve ayrıca başka bir pakette bu sınıfın bir alt sınıfının erişebileceğini belirtir.

Aşağıdaki tabloda her bir erişim belirleyiciye hangi seviyeden erişebileceği gösterilmiştir.
<table width="325" style="height: 235px;" border="1" >
<tbody >
<tr >

<td >Erişim Belirleyici
</td>

<td >Sınıf
</td>

<td >Paket
</td>

<td >Alt-Sınıf
</td>

<td >Her yer
</td>
</tr>
<tr >

<td >public
</td>

<td >E
</td>

<td >E
</td>

<td >E
</td>

<td >E
</td>
</tr>
<tr >

<td >protected
</td>

<td >E
</td>

<td >E
</td>

<td >E
</td>

<td >H
</td>
</tr>
<tr >

<td >-
</td>

<td >E
</td>

<td >E
</td>

<td >H
</td>

<td >H
</td>
</tr>
<tr >

<td >private
</td>

<td >E
</td>

<td >H
</td>

<td >H
</td>

<td >H
</td>
</tr>
</tbody>
</table>
_                Boş kısım package-private’ı temsil ediyor._

<!-- more -->

Tablodan şunları çıkarabiliriz



	
  * Bir sınıf kendi üyelerine hangi erişim belirleyicisi kullanırsa kullansın her zaman erişebilme yetkisine sahiptir.

	
  * private haricindeki erişim belirleyiciler aynı paket içerisindeki sınıflar tarafından erişilebilir.

	
  * public ve protected’a sahip olan üyelerin bulunduğu sınıfın bir alt sınıfı bu üyelere erişebilir.

	
  * public üyesine sahip her bir üye her yerden erişime açıktır.


Erişim belirleyiciler iki yoldan sizi etkiler. Birincisi, başka kaynaktan gelen sınıfları kullanırken (Java platformundaki sınıflar gibi) erişim belirleyiciler bu sınıfların hangi üyelerine erişebileceğinize karar verir. İkincisi, bir sınıf yazdığınızda her bir değişkenin ve her bir metodun hangi erişim seviyesine sahip olacağını belirlemeniz gerekir.

Erişim Belirleyici Seçerken;

	
  * Oluşturduğunuz üye için kullanabileceğiniz en kısıtlayıcı erişim belirleyiciyi kullanın.

	
  * private kullanmamak için bir nedeniz olmadığı sürece private kullanın.

	
  * Sabitler(constant) için public kullanmayın.


