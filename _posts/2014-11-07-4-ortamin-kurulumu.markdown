---
author: akursat
comments: true
date: 2014-11-07 20:40:37+00:00
layout: post
link: http://akursat.com/?p=41
slug: 4-ortamin-kurulumu
title: 4 - Ortamın Kurulumu
wordpress_id: 41
categories:
- Java
- Java Se
tags:
- derleyici
- ide
- java
- java dersleri
- jdk
- jvm
- kurulum
- ubuntu
---

**Bilgisayarıma ne yüklemeliyim ?**

Java programları yazmak için ihtiyaçınız olan üç sey;



	
  * _**Bir derleyiciye ihtiyacınız var.**_



	
  * _**Bir Jvm'e (Java virtual machine) ihtiyacınız var.**_



	
  * _**Bir Ide**__**'**__**ye (Integrated development enviroment) ihtiyacınız var.**_


Ideler Java kodlarınızı yönetmenizi,pratik kod yazmanızı,derlemenizi ve yürütmenizi sağlar.
Jdk kurulumu , derleyici ve jvm ihtiyacımızı karşılıyor.Ide içinse başlıca Eclipse,Netbeans ve IntelliJ kullanılıyor.Çok fazla plugin desteği olan,kolay yapılandırılan ve açık kaynak olan Eclipse'i tercih ediyorum.

[Eclipse.org](http://www.eclipse.org/downloads/) adresinden veya Ubuntu Software Center dan eclipse kurulumunu sisteminize yapabilirsiniz.


## Ubuntu Üzerinde Hızlı Kurulum


webupd8team ppa üzerinden Java 6 ,7 ,8 versiyonlarına erişebilirsiniz.

    
    sudo add-apt-repository ppa:webupd8team/java
    sudo apt-get update
    sudo apt-get install oracle-java7-installer


kurulumun başarıyla sonuçlandığını anlamak için

    
    java -version


komutunu yürütün.buna benzer bir çıktı almalısınız

    
    java version "1.7.0_45" 
    Java(TM) SE Runtime Environment (build 1.7.0_45-b18) 
    Java HotSpot(TM) 64-Bit Server VM (build 24.45-b08, mixed mode)





## Ubuntu Üzerinde Ayrıntılı Kurulum


[Oracle'ın sitesinden](http://www.oracle.com/technetwork/java/javase/downloads/index.html) Jdk'nın son sürümünü , bilgisayarınızın özelliğine göre (32 bit veya 64 bit) indirin.

tar.gz dosyasını çıkarın:

    
    tar -xvf ~/Downloads/jdk-7u45-linux-x64.tar.gz


java yüklemek için dizin oluşturun:

    
    sudo mkdir -p /usr/lib/jvm/jdk1.7.0


çıkarılan dosyaları (home dizini altında) oluşturduğunuz dizine taşıyın:

    
    sudo mv jdk1.7.0_45/* /usr/lib/jvm/jdk1.7.0/


sisteminizin javayı yüklediğinizi bilmesi için:

    
    sudo update-alternatives --install "/usr/bin/java" "java" "/usr/lib/jvm/jdk1.7.0/bin/java" 1 
    sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/lib/jvm/jdk1.7.0/bin/javac" 1 
    sudo update-alternatives --install "/usr/bin/javaws" "javaws" "/usr/lib/jvm/jdk1.7.0/bin/javaws" 1


komutlarını yürütün.Kurulum tamamlandıktan sonra ortamı ayarlamalıyız.
/etc/profile yolundaki dosyayı düzenlemek için:

    
    sudo gedit /etc/profile


komutunu çalıştırın.Açılan dosyanın sonuna

    
    JAVA_HOME=/usr/lib/jvm/jdk1.7.0 
    PATH=$PATH:$HOME/bin:$JAVA_HOME/bin 
    export JAVA_HOME 
    export JRE_HOME 
    export PATH
    


satırlarını ekleyin ve kaydedin. Ortam kurulumu hazır artık Java kodlamaya başlayabiliriz.
