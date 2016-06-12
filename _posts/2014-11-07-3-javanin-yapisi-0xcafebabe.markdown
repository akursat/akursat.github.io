---
author: akursat
comments: true
date: 2014-11-07 20:28:10+00:00
layout: post
link: http://akursat.com/?p=39
slug: 3-javanin-yapisi-0xcafebabe
title: 3 - Java'nın Yapısı 0xCAFEBABE
wordpress_id: 39
categories:
- Java
- Java Se
tags:
- bytecode
- derleyici
- java
- java dersleri
- jvm
- linux
- mac
- magic
- op kod
- windows
---

**Derleme ve JVM Hakkında**

[![getStarted-compiler](http://www.akursat.com/wp-content/uploads/2013/10/getStarted-compiler.gif)](http://www.akursat.com/wp-content/uploads/2013/10/getStarted-compiler.gif)

Java programlama dilinde tüm java kodları .java uzantısıyla biten düz text dosyaları şeklindedir. Bu kaynak dosyaları javac compiler ile .class uzantılı dosyalara çevrilir. Bir .class dosyası asla kod içermez; bytecode içerir.
Bytecode, Java Virtual Machine’in makine dilidir.JVM birçok platform (Mac Os, Linux, Windows…) için erişebilir durumdadır.JVM anlatmanın en kolay yolu sanırım bu örnek.

Bir konferansta Mac, Windows ve Linux sahnedeki Java’nın sunumunu izlemektedir. Java bytecode dilinde konuşmaktadır. Dinleyiciler ise sadece kendi dillerini bilmektedir. Bu durumda devreye JVM ekibi girer.JVM ekibindeki her bir JVM, bytecode dilini ve kendi sistemini bilmektedir. JVM ekibi bytecodeları dinleyerek kendi platformlarına aktarır.
[![jvmekip](http://www.akursat.com/wp-content/uploads/2013/10/jvmekip.jpg)](http://www.akursat.com/wp-content/uploads/2013/10/jvmekip.jpg)


Açık kaynak geliştirilen JVM’lerin listesi:
[http://en.wikipedia.org/wiki/List_of_Java_virtual_machines](http://en.wikipedia.org/wiki/List_of_Java_virtual_machines)

JVM uyarlanan dillerin listesi:
[http://en.wikipedia.org/wiki/List_of_JVM_languages#JVM_implementations_of_existing_languages](http://en.wikipedia.org/wiki/List_of_JVM_languages#JVM_implementations_of_existing_languages)

**Java Dosya Formatı
**Tüm java classları aynı 4 byte ile başlar.HelloWorld.java dosyasını javac ile derledim.Derlenme sonunda HelloWorld.class dosyasına bakalım
[![r22](http://www.akursat.com/wp-content/uploads/2013/10/r22.jpg)](http://www.akursat.com/wp-content/uploads/2013/10/r22.jpg)
Java class dosyası 10 bölümden oluşuyor.



	
  * **Magic Number**: 0xCAFEBABE
James Gosling bu ismin nerden geldiğini anlatmış.Öğle yemeği için gittikleri lokantada Grateful Dead adlı müzik grubunun ünlü olmadan önce performans yaptığı söyleniyormuş. Jerry Garcia ölünce kafenin adını Cafe Dead olarak adlandırmışlar.Bu olaylar üzerine persistent nesne dosyaları için CAFE DEAD class dosyaları içinse CAFE BABE tercih edilmiş.

	
  * **Version of Class File Format**: class dosyasının versiyon bilgileri

	
  * **Constant Pool**: classdaki sabitlerin listesi

	
  * **Access Flags**: classa erişim şekli nedir(static,public,final…)

	
  * **This Class**: classın adı.

	
  * **Super Class**: super class’ın adı

	
  * **Interfaces**: classdaki interfaceler

	
  * **Fields**: classdaki field’ler.(bir classın üyesi olan veriye javada field ile ifade ediliyor.örn. String isim;)

	
  * **Methods**: classın sahip olduğu methodlar

	
  * **Attributes**: classın sahip olduğu öznitelikler(örn HelloWorld.class dosyası için kaynak dosyanın adı HelloWorld.java )




**Java ByteCode Editor ile bu bölümleri görüntülebilirsiniz.
**

    
    //HelloWorld.java
    public class HelloWorld {
    
    	public static void main(String[] args) {
    		System.out.println("Hello World!");
    	}
    }


Java ByteCode Editor ile Bytecode karşılığına bakalım

    
    getstatic java/lang/System/out Ljava/io/PrintStream;
    ldc "Hello World!"
    invokevirtual java/io/PrintStream/println(Ljava/lang/String;)V
    return



