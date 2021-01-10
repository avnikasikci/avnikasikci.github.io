---
title: Bilgisayar Organizasyonu ve Mimarisi - Başlangıç
created: Jan 10, 2021 3:02 AM
modified: Jan 10, 2021 3:02 AM
layout: postByComputer
author: Avni Kaşıkçı
date: '2021-01-10 03:02:00'
thumbnail: "/assets/img/posts/hello.jpg"
summary: BOM
permalink: "/ComputerEngineer/BOM_Introduction2"
category:
- computerStudy
- BOM
- computer
categories:
- computer
- System-Operation
---

## Programlama

∎ Assembly nasıl yapılır ?
 Program şu şekilde yürütülür? Dijital mantık nedir ?
∎ Arada ne olur?
∎ Bir bilgisayar nasıl tasarlanır. Mantık kapılarını ve kabloları kullanarak
belirli hedefleri tatmin ediyor mu?
 
∎ Hesaplama modeli olarak "C" Programcının bir bilgisayar sistemi çalışıyor.
 
∎ Mimar / mikro mimarın görüşü:
 
∎ Bir bilgisayar nasıl tasarlanır ?
 
Sistem tasarım hedeflerini karşılar. Seçimler her ikisini de önemli ölçüde etkiler.
SW programcısı ve HW tasarımcısı
 
∎ HW tasarımcısının bir bilgisayar sistemi çalışıyor
 
∎ Dijital mantık hesaplama modeli
 
 
## Dönüşüm Seviyeleri

"Bilgi işlemin amacı iç görüdür" ( Richard Hamming )Sorunları çözerek içgörü kazanır ve üretirizSorunların elektronlarla çözülmesini nasıl sağlarız?
<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\tempsnip.png">
![](tempsnip.png)

## Soyutlamanın Gücü

∎ Dönüşüm seviyeleri soyutlamalar yaratır

    ❑ Soyutlama: Daha yüksek bir seviyenin yalnızcaalt seviyenin nasıl olduğuna değil, alt seviyeye arayüzuygulandı

    ❑ Örneğin, üst düzey dil programcısının gerçektenISA'nın ne olduğunu ve bir bilgisayarın talimatları nasıl uyguladığını bilmek

∎ Soyutlama üretkenliği artırır

    ❑ Altta yatan seviyelerde alınan kararlar için endişelenmenize gerek yok
    
    ❑ Örneğin, Java, C, derleme, binary ve byher çevrimde her transistörün kontrol sinyallerini belirleme

∎ Öyleyse neden neler olduğunu bilmek isteyesiniz?altında mı yoksa üstünde mi?

## Soyutlama Katmanlarını Geçme

∎ Her şey yolunda gittiği sürece, ne olacağını bilmemekaltta yatan düzeyde (veya üstü) bir sorun değildir.

∎ Eğer

    ❑ Yazdığınız program yavaş mı çalışıyor?

    ❑ Yazdığınız program düzgün çalışmıyor mu?

    ❑ Yazdığınız program çok mu enerji tüketiyor?

∎ Eğer

    ❑ Tasarladığınız donanımın programlanması çok mu zor?

    ❑ Tasarladığınız donanım çok yavaş çünküyazılım için doğru ilkeler?

∎ Eğer 

    ❑ Çok daha verimli ve daha yüksek performans tasarlam
    istiyorsunuz sistemi? 

## Bir Örnek: Çok Çekirdekli Sistemler



### *Çok Çekirdekli Chip*

<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\Ekran-Alintisi.PNG">

![](Ekran-Alintisi.PNG)
Die photo credit: AMD Barcelona

## Çok Çekirdekte Beklenmedik Yavaşlamalar
<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\Ekran-Alintisi1.PNG">
![](Ekran-Alintisi1.PNG)
Moscibroda ve Mutlu, " Bellek performansı saldırıları:

Bellek hizmetinin reddiçok çekirdekli sistemlerde, SENIX Security 2007.


## Bir veya İki Soru

∎ İşlemcinin programları nasıl çalıştırdığını bilmiyorsanız, yavaşlamalarda neden bir eşitsizlik olduğunu anlayabilir misiniz?

∎ *Altında* ne olduğunu bilmeden sorunu çözebilir misiniz?

## Yavaşlamalarda Neden Eşitsizlik Var?


<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\Ekran-Alintisi2.PNG">
![](Ekran-Alintisi2.PNG)

## DRAM Bank Operasyonu

<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\Ekran-Alintisi3.PNG">
![](Ekran-Alintisi3.PNG)

## DRAM Denetleyicileri

∎ Satır çakışması bellek erişimi, satıra ulaşılan erişimden önemli ölçüde daha uzun sürer

∎ Mevcut kontrolörler satır tamponundan yararlanır

∎ Yaygın olarak kullanılan planlama politikası (FR-FCFS) [Rixner 2000] *

    (1) Önce satır vuruşu: Hizmet, satır vuruş belleğine önce erişir

    (2) Önce en eskisi: Daha sonra, önce eski erişimlere hizmet verir

∎ Bu zamanlama politikası DRAM verimini en üst düzeye çıkarmayı amaçlamaktadır

*Rixner et al., “Memory Access Scheduling,”ISCA 2000. *Zuravleff and Robinson, “Controller for a synchronous DRAM …,”US Patent 5,630,096, May 1997.

## Yavaşlamalarda Neden Eşitsizlik Var? 


<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\Ekran-Alintisi4.PNG">
![](Ekran-Alintisi4.png)


## Bir Bellek Performansı Domuzu

<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\Ekran-Alintisi7.PNG">

![](Ekran-Alintisi7.png)
STREAM

- Sıralı bellek erişimi

- Çok yüksek satır arabellek yeri (% 96 isabet oranı)

- Hafıza yoğun


<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\Ekran-Alintisi8.PNG">

![](Ekran-Alintisi8.png)

RANDOM

- Rastgele hafıza erişimi

- Çok düşük satır arabellek yeri (% 3 isabet oranı)

- Benzer şekilde yoğun bellek

Moscibroda and Mutlu, “Memory Performance Attacks,”USENIX Security 2007.


## Sorun

∎ Çoklu iş parçacığı DRAM denetleyicisini paylaşır

∎ DRAM verimini en üst düzeye çıkarmak için tasarlanmış DRAM denetleyicileri


∎ DRAM zamanlama politikaları iş parçacığı açısından haksızdır

     Önce satır vurma: haksız bir şekilde önceliklendirir yüksek satır arabellek konumuna sahip iş parçacıkları

         Aynı satıra erişmeye devam eden iplikler

     Eski-önce: bellek yoğun iş parçacıklarına haksız bir şekilde öncelik verir

∎ DRAM denetleyicisi, hizmet reddi saldırılarına karşı savunmasızks 

     Haksızlıktan yararlanmak için programlar yazabilir


 ## Hafıza Hog Do Nasıl Yapılır?


<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\Ekran-Alintisi9.PNG">

![](Ekran-Alintisi9.png)
Satır boyutu: 8KB, önbellek blok boyutu: 64B 128 (8KB / 64B) T1'den önce hizmet verilen T0 istekleri

Moscibroda and Mutlu, “Memory Performance Attacks,”USENIX Security 2007.

## Şimdi Altında Ne Olduğunu Biliyoruz

 ∎ Sorunu nasıl çözersiniz?

 ∎ Sorunu çözmek için doğru yer neresi?
 Programcı? 

 ∎ yazılımı?

 ∎?(derleyici)

 ∎ (Bellek denetleyicisi)? 

 ∎ (DRAM)? 

 ∎ Devreler?



<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\tempsnip.png">
![](tempsnip.png)

∎ Bu kursun diğer iki amacı:

     Eleştirel düşünmenizi sağlar

     Geniş düşünmenizi sağlar

## İlgileniyorsanız… Daha Fazla Okumalar

∎ Mutlu ve Thomas Moscibroda, 40. Uluslararası Mikro

    "Çipli Çok İşlemciler için Stall-Time Fair Memory Access Scheduling" Bildirileri, sayfalar 146-158, Chicago, IL, Aralık 2007. Slaytlar (ppt)

    40. Uluslararası Mikro Mimari Sempozyumu Bildirileri (MICRO), sayfalar 146-158, Chicago, IL, Aralık 2007. Slaytlar (ppt)

∎ Sai Prashanth Muralidhara, Lavanya Subramanian, Onur Mutlu, Mahmut Kandemir, and Thomas Moscibroda, 

    "Uygulamaya Duyarlı Bellek Kanalı Bölümleme Yoluyla Çok Çekirdekli Sistemlerde Bellek Parazitini Azaltma"

    44. Uluslararası Mikromimarlık Sempozyumu (MICRO) Bildirileri, Porto Alegre, Brezilya, Aralık 2011. Slaytlar (pptx)

## Paket servisi

∎ Soyutlama katmanlarını kırmak (bileşenler ve dönüşüm hiyerarşi düzeyleri arasında) ve altında ne olduğunu bilmek sorunları çözmenizi sağlar

## Başka bir örnek

∎ DRAM Yenileme

## Sistemde DRAM
Çok Çekirdekli Çip

<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\Ekran-Alintisi10.png">
![](Ekran-Alintisi10.png)

## DRAM Hücresi


<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\Ekran-Alintisi11.png">

![](Ekran-Alintisi11.png)

∎ DRAM hücresi, bir kapasitör ve bir erişim transistöründen oluşur

∎ Kapasitörde yük açısından verileri depolar

∎ Bir DRAM yongası, bu tür hücrelerin (10'unun 1000'ini) sıralarından oluşur

## DRAM Yenileme

∎ DRAM kapasitör şarjı zamanla sızıyor

∎ Bellek denetleyicisinin şarjı geri yüklemek için her satırı periyodik olarak yenilemesi gerekir

     Her N ms'de bir her satırı etkinleştirin

     Typical N = 64 ms

∎ Yenilemenin alt tarafları

- Enerji tüketimi: Her yenileme enerji tüketir
- Performans bozulması: DRAM sıralaması / bankası yenilenirken kullanılamaz
- QoS/predictability impact: Yenileme sırasında (Uzun) duraklama süreleri
- Yenileme hızı sınırları DRAM kapasite ölçeklendirmesi

## Ek Yük Yenileme: Performans


<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\Ekran-Alintisi12.png">
![](Ekran-Alintisi12.png)

## Ek Yük Yenileme: Enerji

<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\Ekran-Alintisi13.png">

![](Ekran-Alintisi13.png)

## Sorunu Nasıl Çözeriz?

∎ Her 64 ms'de bir tüm satırları yenilememiz gerekiyor mu?

∎ Ya altında ne olduğunu bilseydik ve bu bilgiyi üst katmanlara ifşa etsek

## Altında: DRAM'ın Saklama Süresi Profili


<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\Ekran-Alintisi14.png">
![](Ekran-Alintisi14.png)

## Bu Profilden Yararlanmak

∎ Bu profilin bilgileri nedir?

     bellek denetleyicisi

     İşletim sistemi

     Programcı ?

     Derleyici?

∎ Ne kadar bilgi ifşa edilecek?

     Donanım / yazılım ek yükünü, güç tüketimini, doğrulama karmaşıklığını, maliyeti etkiler
 
∎ Bu profil bilgileri nasıl belirlenir?

     Ayrıca, onu kim belirler?

## Bir Örnek: RAIDR

∎ Gözlem: Çoğu DRAM satırı çok daha az sıklıkta yenilenebilirveri kaybetmeden [Kim +, EDL'09] [Liu + ISCA'13]

∎ Zayıf hücreler içeren satırları daha sık yenileyin, diğer satırları daha seyrek yenileyin


<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\Ekran-Alintisi15.png">
![](Ekran-Alintisi15.png)

1. Profil oluşturma: Tüm satırların profil saklama süresi

2. Bölme: Satırları bellek denetleyicisindeki tutma süresine göre bölmelerde saklayın Bloom Filtreleriyle verimli depolama (32 GB bellek için yalnızca 1,25 KB)

3. Yenileme: Bellek denetleyicisi farklı bölmelerdeki satırları şu saatte yeniler: farklı oranlar

∎ Sonuçlar: 8 çekirdekli, 32 GB, SPEC, TPC-C, TPC-H
    ❑ 1,25 KB depolamada% 74,6 yenileme azalması

    ❑ ~% 16 /% 20 DRAM dinamik / boşta güç azaltma

    ❑ ~% 9 performans artışı❑ DRAM kapasitesi ile avantajlar artar



<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\Ekran-Alintisi15.png">
![](Ekran-Alintisi15.png)

## İlgileniyorsanız… Daha Fazla Okumalar

∎Jamie Liu, Ben Jaiyen, Richard Veras ve Onur Mutlu,"RAIDR: Tutmaya Duyarlı Akıllı DRAM Yenileme"39. Uluslararası Bilgisayar Mimarisi Sempozyumu Bildirileri( ISCA ) , Portland, OR, Haziran 2012. Slaytlar (pdf)

∎Onur Mutlu,"Bellek Ölçeklendirme: Sistem Mimarisi Perspektifi"MemCon 2013'te ( MEMCON ) teknik konuşma , Santa Clara, CA, Ağustos 2013


## Paket servisi

∎ Soyutlama katmanlarının kırılması (bileşenler arasında vedönüşüm hiyerarşi seviyeleri) ve ne olduğunu bilmekaltında problemleri çözmenizi ve tasarımı sağlardaha iyi gelecek sistemleri

∎ Birden çok bileşen ve katman arasındaki işbirliği,daha etkili çözümler ve sistemler sağlar

## Ne öğreneceksin

∎ Bilgisayar Mimarisi: Bilim ve sanatdonanım tasarlama, seçme ve birbirine bağlamabileşenler ve donanım / yazılım arayüzünü tasarlamaişlevselliği karşılayan bir bilgi işlem sistemi oluşturmak,performans, enerji tüketimi, maliyet ve diğer belirlihedefler.

∎ Geleneksel tanım: " Mimari terimi kullanılırburada, bir sistemin özelliklerini,programcı, yani kavramsal yapı ve işlevselveri akışının organizasyonundan farklı davranışve kontroller, mantık tasarımı ve fizikseluygulama. " Gene Amdahl , IBM Journal of R&D, Nisan1964


<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\Ekran-Alintisi17.png">
![](Ekran-Alintisi17.png)

## Dönüşüm Düzeylerinde Bilgisayar Mimarisi


<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\tempsnip.png">
![](tempsnip.png)

∎ Okuyun: Patt, " Requirements, Darboğazlar ve Good Fortune: Agents forMikroişlemci Evrimi , ”Proceedings of the IEEE 2001

## Dönüşüm Seviyeleri, Yeniden Ziyaret Edildi

∎ Kullanıcı merkezli bir görünüm: kullanıcılar için tasarlanmış bilgisayar
<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Introduction2\tempsnip1.png">
![](tempsnip1.png)

∎ Yığının tamamı kullanıcı için optimize edilmelidir

## Kursun Hedefleri

∎ Hedef 1: Bilgisayar sistemiyle ilgilenenleri tanıtmakhem temel çalışma prensipleri hem de tasarım ile tasarımkarşılaştırılması ve işlemci, bellek ve bir platform mimarileri debugünün sistemleri.

    ❑ Temellere ve tasarım değiş tokuşlarına güçlü vurgu.

∎ Hedef 2: Gerekli arka plan ve deneyimi sağlamaktasarlamak, uygulamak ve modern bir işlemci değerlendirmek tarafındanuygulamalı RTL ve C düzeyinde uygulama gerçekleştirme .

    ❑ İşlevselliğe ve uygulamalı tasarıma güçlü vurgu.

∎ Hedef 3: Eleştirel düşünün (problemleri çözerken) ve geniş anlamdadönüşüm seviyelerinde

## Bir Sonraki Sefer için Okumalar

∎Patt, " Gereksinimler, Darboğazlar ve İyi Şans:Agents for Microprocessor Evolution , ”Proceedings of theIEEE 2001.
 
∎ Mutlu ve Moscibroda, “ Bellek Performansı Saldırıları:Çok Çekirdekli Sistemlerde Bellek Hizmeti Reddi , ”USENIXGüvenlik Sempozyumu 2007.
 
∎ P&P Bölüm 1 (Temel Bilgiler)
 
∎ P&H Bölüm 1 ve 2 (Giriş, Soyutlamalar, ISA, MIPS)
 
∎ Kurs boyunca referans materyal
 
    ❑ ARM Referans Kılavuzu
    
    ❑ (daha az) x86 Referans Kılavuzu  