---
title: Lojik Kapılar
created: '2020-10-28T16:33:42.376Z'
modified: '2020-10-28T16:39:37.142Z'
layout: postByComputer
author: Avni Kaşıkçı
date: '2020-10-22 03:02:32'
thumbnail: "/assets/img/posts/hello.jpg"
summary: Logic Circuits
keywords: using Logic gates
permalink: "/ComputerEngineer/logic-gates"
category: [computer, logic-circuits]
categoryByComputer: [computer, logic-circuits]
categories: [computer, logic-circuits]
categoriesByComputer: [computer, logic-circuits]
---

# Lojik Devreler
**Digital Desing**

## Logic Kapılar ve Logic Devreler

# 1.Karşılaştırıcı ve Aritmetik İşlem Devreleri

* **1.1.Giriş** <br>
Karşılaştırıcı ve aritmetik işlem devreleri ‘Kıyaslama Devreleri’ veya ‘Aritmetik Mantık Birimi’ olarak da bilinirler..
İki sayıyı karşılaştıran ve sayısal değerlerini belirleyen bileşik devrelerdir.Belli başlı komutları vardır.Örneğin ikili sayıları toplayıp çıkarabildiğimiz birlikte bunlarla hangi sayının büyük veya küçük olduğunu belirlediğimiz veya eşit olup olmadıklarını sorguladığımız bunları sorgularkende Boole Cebiri ilkelerinden faydalandığımız And Nor vb. kapıları kullandığımız devrelerden bahsedeceğiz.Sektörde de çeşitli yapılar bulunmaktadır.Bunlara örnek verecek olursak bilgisayar sistemlerindeki CPU’lar mikrocontrol (MCU’LAR) cmos 4063 entegreleri 4585 entegreleri karşılaştırıcı ve aritmetik işlemler yapabilecek devrelerdir.

![](/assets/img/study/Lojik-Devreler/Logic-Gates-And-Logic-Circutius.png)

**1.2.Kimlik Karşılaştırıcı** <br>
Tek çıkış terminaline sahip olan karşıcılardır.A=B yada A=B=1(Buna kaynaklarda yüksek çıkış değeri deniliyor.)A=B=0 terminal çıkışlarına sahiptirler.



![](/assets/img/study/Lojik-Devreler/Devre_1.png)

Görüldüğü üzere A ve B girişleri olmak üzere iki girişin 1 olması durumunda A=B ifadesini temsil eden ledimiz yanmaktadır.İlgili devre ile ilgili bir doğruluk tablosu oluşturacak olursak.
![](/assets/img/study/Lojik-Devreler/table_1.png)

Digital karşılaştırıcılar Devre_1.circ‘ dede görüldüğü gibi tasarımları gereği NOR kapılarını kullanmaktadırlar.Bu durumun çeşitlerini artırabilir ve 2 bitlik bir büyüklük karşılaştırıcısı yapabiliriz bunun örneğini SN https://www.ti.com/product/SN54S85 entegre devresinden esinlenerek logisimde çaşıştaralım.


![](/assets/img/study/Lojik-Devreler/Devre_2.png)
**Devre_2.circ**
Devre_2.circ dede görüldüğü üzere A0,A1,B0,B1 giriş değerlerinin 4 ününde 0 olması konumunda A=B eşit olduğu bir durum söz konusudur. 
Soru1:İlgili Devre_2.circ devresindeki giriş değerlerini kullanarak bir doğruluk tablosu hazırlayın ve tabloyu karnaugh haritalarından faydanalarak sadeleştirip çıkış değerlerinin sadeleşmiş denklemlerini yazın.

![](/assets/img/study/Lojik-Devreler/table_2.png)

Bunun için logisim programına benzer bir yapı kullanacağım

![](/assets/img/study/Lojik-Devreler/Devre_3.png)

Bu durumda Sadeleştirme işlemlerini gerçekleştirecek olursak;<br>
A>B:A1B1’ + A0B1’B0’ + A1A0B0’
A=B: A1’A0’B1’B0’ + A1’A0B1’B0 + A1A0B1B0 + A1A0’B1B0’
   : A1’B1’ (A0’B0’ + A0B0) + A1B1 (A0B0 + A0’B0’)
   : (A0B0 + A0’B0’) (A1B1 + A1’B1’)
   : (A0 Ex-Nor B0) (A1 Ex-Nor B1)
A<B:A1’B1 + A0’B1B0 + A1’A0’B0
Şeklinde bolean fonksiyonları elde edebiliriz.

**1.4.Yarım Karşılaştırıcı**


Devreye uygun şekilde birer bitlik verileri(sayıları) karşılaştıran ve sadece eşit olup olmadıklarını gösteren devrelere denir.
2 Giriş ve 2 çıkıştan oluşan devrelerdir.
(D.N aşağıdaki çizimler google docs çizim programından faydalanarak yapılmıştır.)

![](/assets/img/study/Lojik-Devreler/Devre_4.png)


Boolean matematiği olarak ifade ediliş biçimlerine gösterecek olursak.
1.Denklem=>(A=B İÇİN)=A’B’+AB=A’+B’ 
2.Denklem=>(A!=B İÇİN)=A’B+AB’=A+B
![](/assets/img/study/Lojik-Devreler/Devre_5.png)

**1.5.Tam Karşılaştırıcılar**
Giriş değerlerini etkileyen birer bitlik 2 tane 2’lik sistemde veri değerlerini karşılaştıran ve değerlerin eşit olup olmadığını şayet eşit değilse hangisinin büyük veya küçük olduğunu belirleyen devrelerdir.
![](/assets/img/study/Lojik-Devreler/Devre_7.png)

Üstteki şekilde de görüldüğü üzere 3 çıkışı 2 girişi mevcuttur.Çıkışların boolean fonksiyonu olarak ifade ediliş biçimleri aşağıdaki görselde yer almaktadır.

![](/assets/img/study/Lojik-Devreler/Devre_8.png)

İlgili fonksiyonları logisim.exe programı ile ifade edelim.Lojik devreleri belirleyelim.


![](/assets/img/study/Lojik-Devreler/Devre_6.png)

Doğruluk tablosu yazılımsal olarak algoritmayı ifade eder.
Girişler arasında ilişki bizim çıkışlarımızı temsil eder. Bu şekilde doğruluk tablosu ifade eder.



![](/assets/img/study/Lojik-Devreler/Devre_10.png)

**Boolean Kuralları ve Lojik ifadelerin Sadeleştirilmesi**

1854 yılında George Boole tarafından özellikle lojik devrelerde kullanılmak üzere ortaya konulmuş bir matematiksel sistemdir. • 1938’li yıllarda da ilk defa Claude Shannon tarafından Boole’un çalışması,lojik devrelerin tasarımı ve analizinde kullanılmıştır. Boole cebri AND, OR ve NOT temel mantıksal işlemlerinden oluşan sembolik bir sistem olarak düşünülebilir.
	 BooleCebri,İkilisistemincebridir. • Tüm Bilgisayarlar Boole Cebrini kullanarak (1 ve 0 dönüşümü)çalışırlar.
BooleanAlgebra–George Boole(1815-1864)
Bilgisayarlarda, Voltaj seviyesine bağlı olarak iki tür mantık kullanılır.
1. “Positive logic” 1 için + voltage (örneğin 5 V) ve 0 için 0 V.
2. “negative logic” 1 = 0V, 0 = +V (örneğin 5V)
Temel olarak 7 kapı vardır bunlar; 
‘VE’ (AND) ‘VEYA’ (OR) ‘DEĞİL’ (NOT) ‘VE DEĞİL’ (NAND) ‘VEYA DEĞİL’ (NOR) ‘ÖZEL VEYA’ (EXOR) ‘ÖZEL VEYA DEĞİL’ (EXNOR)

![](/assets/img/study/Lojik-Devreler/Devre_11.png)

Mantık devrelerinin çalışmasını matematiksel olarak ifade etmek için Boolean Kuralları kullanılmaktadır.

Boolean Değişkeni: İki adet Boolean değişkeni vardır. 0-1, DY, H-L, ON-OFF boolean değişkenleri olarak kullanılmaktadır.

**Boolean İşlemleri** <br>
Boolean değişkenlerinin dönüşümünde kullanılan işlemlerdir. Bu işlemler VE, VEYA, DEĞİL işlemleridir


**Değil İşlemi** <br>
A değişkeninin DEĞİL’i A’ veya Āile gösterilir ve A’nın tersine Eşittir. 
DEĞİL, Tümleyenya da Tersi de denir.
![](/assets/img/study/Lojik-Devreler/Degil_Gate.png)



  "Ve" ,"Veya" işlemlerinden farklı olmak üzere tek giriş ve tek çıkışı vardır.
  Örneğin a değişkeni ile işlem yapıcak olursak."Not" işlemi sonucu Q=A' oolarak tanımlanır ve A değişkeni üzerinde ki çizgi değili ifade eder.

**VE İŞLEMİ**
Elektrik devresinde seri bağlı anahtarlar ile gösterilir.
Matematikte çarpma işlemine karşılık gelir.
Boolean çarpma VE fonksiyonu ile ifade edilir ve ‘‘.’’ ile gösterilir.
Boolean  çarpmada herhangi bir değer 0 ise sonuç 0 çıkacaktır.
- 0 . 0 = 0 
- 0 . 1 = 0
- 1 . 0 = 0
- 1 . 1 = 1


![](/assets/img/study/Lojik-Devreler/and_gates.png)

**DOĞRULUK TABLOSU**


![](/assets/img/study/Lojik-Devreler/dogruluk_tablosu.png)

**VEYA İŞLEMİ**

 Boolean toplama VEYA işlemine eşittir.
 Toplamanın kuralı:
- 0+0=0 
- 0+1=1 
- 1+0=1 
- 1+1=1 
 Boolean aritmetiğinde toplama toplama dahil olan literallerin toplamıdır. Sadece VEYA işlemidir. 
- A+B
- A+B' 
- A+B+C’ 
- A’+B+C+D’ 
- Toplam giriş literallerinden en az biri 1 olduğunda 1, aksi halde 0’dır. 

- VEYA İşlemi matematikteki toplama işlemine karşılık gelmektedir.  
- Elektrik devresi olarak birbirine paralel bağlı anahtarlar ile gösterilebilir.
0+0=0,	0+1=1
1+0=1,	1+1=1


**Özel Veya Kapısı** <br>
Bir çıkış, iki veya daha fazla giriş hattı bulunur. Tek bir özellik dışında "VEYA" kapısı ile birebir aynıdır. Bu özellik de; girişlerin hepsi "1" olursa çıkış değeri "1" yerine "0" olur.**" Y= A' . B + A . B' "** ile ifade edilebilir.

**ÖZEL VEYADEĞİL(EXOR)KAPISI** <br> 

	Bir çıkış, iki veya daha fazla giriş hattı bulunur. "ÖZELVEYA" fonksiyonunun tam tersi çıkış verir. "VEYA" kapısıdan tek bir özellik ile ayrılır ve bu özellik de; girişlerin hepsi "0" olursa çıkış değeri "0" yerine "1" olur. " Y= A' . B' + A . B " ile ifade edilebilir. 


![](/assets/img/study/Lojik-Devreler/Special_Or_NotGates.png)


![](/assets/img/study/Lojik-Devreler/Devre_12.png)

Giriş değerimiz 1 olunca çıkış değerimiz olan led yanmamaktadır yani 0 değerini almaktadır.
Giriş değerimiz 0 olunca çıkış değerimiz olan led yanmaktadır yani 1 değerini almaktadır.

