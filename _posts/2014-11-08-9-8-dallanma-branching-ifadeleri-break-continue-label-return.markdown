---
author: akursat
comments: true
date: 2014-11-08 08:07:40+00:00
layout: post
link: http://akursat.com/?p=77
slug: 9-8-dallanma-branching-ifadeleri-break-continue-label-return
title: 9.8 Dallanma (Branching) İfadeleri – break, continue, label, return
wordpress_id: 77
categories:
- Java
- Java Se
tags:
- break
- continue
- etiket
- go to
- java
- java dersleri
- label
- return
---

Şuana kadar gördüğümüz ifadeler belirli bir akış içerisindeydi peki onları bu akıştan çıkarmak için ne yapmamız gerek.İşte burda devreye dallanma ifadeleri giriyor.




**break** kontrol akışının döngüden çıkmasına neden olur(döngü koşulunun false olması gibi)
**continue** kontrol akışışının döngü koşuluna atlamasına neden olur.Bu kontrol akışının bir sonraki iterasyona atlamasına sebeb olur.
**label** break ve continue ifadeleri ile kullanılır.İç içe döngülerde istenilen döngünün dışına çıkabilmek için kullanılır.break için örnek Label Kullanımı başlığında verildi.
**return** bulunduğu metotdan çıkarır ve kontrol akışını metodun çağrıldığı yere geri döndürür.





## **Break Kullanımı**




Break koşul sağlandığından bulunduğu döngünün dışına çıkacaktır.break bir döngüde(for,while,do while) yada switchde kullanılmalıdır.Örnek 1.1 de görüldüğü üzere;




    
    for (int i = 0; i < 25; i++) {
    			System.out.println(i);
    			if (i == 3) {
    				break;
    			}
    		}
    		// koşul sağlandığından break bu satıra atlayacak.
    	}


Çıktı:

    
    0,1,2,3,




## **Continue Kullanımı**




continue “döngüdeki bir sonraki iterasyona git” diye yorumlanabilir. Örnek 2.1 bu durumu çıktıdan kolayca anlayabiliriz.




    
    for (int i = 0; i < 5; i++) {
    
    			if (i == 3) {
    				continue;// bir sonraki iterasyona gidecek.
    			}
    			System.out.print(i + ",");
    		}


Çıktı:

    
    0,1,2,4,




Çıktıda görüldüğü gibi i, üçe eşit olduğunda bir sonraki iterasyona atladı ve dördü ekrana yazdı.
Breakde olduğu gibi labeli continue ilede benzer şekilde kullanabiliriz.





## **
Label Kullanımı**


break ve continue ifadeleri ile kullanılır demiştik.Peki break bir iç içe döngüde bulunuyorsa ve bizim bu iç içe döngüden çıkmamız gerekiyorsa.İşte bu durumda **Label(etiket)** kullanılır Örnek 1.2 de görüldüğü üzere;

    
    dongunun_disi: for (int i = 0; i < 25; i++) {
    
    			for (int j = 0; j < 3; j++) {
    
    				System.out.print(i + "," + j + "-");
    				if (i == 0 && j == 0) {
    					break dongunun_disi;
    				}
    			}
    
    		}// koşul sağlandığından break bu satıra atlayacak.




Labeli döngünün başladığı yere koyun.Labeli break ile tanımlayın.İç içe döngülerden bu şekilde çıkabilirsiniz.





## **Return Kullanımı**




**return** bulunduğu metotdan çıkarır ve kontrol akışını metodun çağrıldığı yere geri döndürür demiştik.return iki farklı türe sahiptir.Biri değer alır ve diğeri almaz.
Örneğin değer alan bir return ifadesi;




    
    int sayi1;
    int ornekmetot2() {
          return sayi1;
    }




Aynı zamanda değer dönderecek şekilde bir expressionda yazılabilir.




    
    return sayi1*sayi2;




Geri dönen değerin(örneğin üsteki satır) veri tipi metodun veri tipi ile uyuşmalıdır.
void bir metot tanımlandığında return nun değer almayan türü kullanılır.Bu bir değer döndürmez.Örneğin




    
    void ornekmetot() {
    
    		return;
    	}




_Not:Bu metotlarla ilgili tüm bilgiyi Sınıflar yazısında paylaşacağım._
