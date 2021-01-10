---
title: Bilgisayar Organizasyonu ve Mimarisi - Temel Kavramlar ve ISA
created: Jan 6, 2021 3:02 AM
modified: Jan 6, 2021 3:02 AM
layout: postByComputer
author: Avni Kaşıkçı
date: '2021-01-06 10:02:00'
thumbnail: "/assets/img/posts/hello.jpg"
summary: BOM,Temel Kavramlar ve ISA
permalink: "/ComputerEngineer/BOM_Fundamental"
category:
- computerStudy
- BOM
- computer
---

## Temel Kavramlar ve ISA

***Bugünün Ajandası***
* İncele
* Neden bilgisayar mimarisi eğitimi almalı?
* ISA
* Mikro mimari
* Bilgisayar Mimarisi
* Sonraki Ders

## Gözden Geçirme: Dönüşüm Düzeyleri, Yeniden Ziyaret Edildi

* Kullanıcı merkezli bir görünüm: kullanıcılar için tasarlanmış bilgisayar


<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Fundamental/Capture.png">

![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Fundamental/Capture.png)

* Yığının tamamı kullanıcı için optimize edilmelidir

## NEDEN BİLGİSAYAR MİMARİ?

# Neden Bilgisayar Mimarisi eğitimi almalısınız?


* Tasarım, seçme ve tasarım bilimi ve sanatı donanım bileşenlerini birbirine bağlamak ve bir bilgi işlem sistemi oluşturmak için donanım / yazılım arayüzü 
fonksiyonel, performans, enerji tüketimini karşılayan,
maliyet ve diğer özel hedefler.

Yakında mimari terimleri birbirinden ayıracağız,
ve mikro mimari terimlerini yoğunlaşıcaz.

* Bir Destekleyici: Moore Yasası
<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Fundamental/Capture1.png">
![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Fundamental/Capture1.png)

# Bu Transistörleri Ne İçin Kullanıyoruz?

# Günümüz Bilgisayar Mimarisi

* Bugün bilgisayar mimarisini incelemek için çok heyecan verici bir zaman

* Endüstri büyük bir paradigma kayması içindedir (çok çekirdekli ve ötesinde) - birçok farklı potansiyel sistem tasarımı mümkündür

* Motive eden ve vardiyanın neden olduğu birçok zor sorun
    * Güç / enerji kısıtlamaları
    * Tasarımın karmaşıklığı → çok çekirdekli mi?
    * Teknoloji ölçeklendirmedeki zorluklar → yeni  teknolojiler?
        * Bellek duvarı / boşluğu
        * Güvenilirlik duvarı / sorunlar
        * Programlanabilirlik duvarı / sorunu

# Vardiyanın neden olduğu ve motive eden birçok zor problem
* Güç / enerji kısıtlamaları
* Tasarımın karmaşıklığı -> çok çekirdekli?
* Teknoloji ölçeklendirmedeki zorluklar -> yeni teknolojiler?
    * Hafıza duvarı / boşluğu
    * Güvenilirlik duvarı / sorunları
    * Programlanabilirlik duvarı / problem
* Bu sorunlara net, kesin cevaplar yok...

# Günümüz Bilgisayar Mimarisi (II)

* Bu sorunlar, bilgi işlem yığınının tüm bölümlerini etkiler - eğer sistemleri tasarlama şeklimizi değiştirmeyiz.


<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Fundamental/Capture2.png">


![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Fundamental/Capture2.png)


* Hesaplama için yeni paradigmalar icat edebilirsiniz,
iletişim ve depolama

# Hedefler

* Bilgisayar sistemiyle ilgilenenleri tanıtmak
hem temel çalışma prensipleri hem de tasarım ile tasarım işlemci, bellek ve platform mimarilerinin değiş tokuşu bugünün sistemleri.
* Temellere ve tasarım değiş tokuşlarına güçlü vurgu.

* Gerekli arka plan ve deneyimi sağlamak için
modern bir işlemciyi tasarlayın, uygulayın ve değerlendirin uygulamalı RTL ve C düzeyinde uygulama gerçekleştirme.
* İşlevselliğe ve uygulamalı tasarıma güçlü vurgu.


* Eleştirel düşünün (problemleri çözerken) ve geniş anlamda dönüşüm seviyelerinde.

# Fakat Önce...

* Temelleri anlayalım…

* Dünyayı ancak iyi anlarsan değiştirebilirsin
yeter…

* Özellikle geçmiş ve şimdiki egemen paradigmalar
* Avantajları ve eksiklikleri - ödünleşimler

## KOMUT SETİ MİMARLIK (ISA)

* Bilgisayar nedir?

* Üç temel bileşen

* Hesaplama
* İletişim
* Depolama (bellek)


<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Fundamental/Capture3.png">


![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Fundamental/Capture3.png)

# Von Neumann Modeli / Mimarisi

* Depolanan program bilgisayarı olarak da adlandırılır (hafıza). İki temel özellik:

* Kaydedilmiş program
    * Doğrusal bellek dizisinde saklanan talimatlar
    * Bellek, talimatlar ve veriler arasında 
* Kaydedilen bir değerin yorumlanması kontrol ünitesine bağlıdır.
* Bir değer ne zaman bir talimat olarak yorumlanır?
* Sıralı talimat işleme
* Bir talimat bir anda işlendi (getirildi, yürütüldü ve tamamlandı).
* Program sayacı (komut işareti) mevcut enstrümanı tanımlar.
* Program sayacı, kontrol aktarımı dışında sırayla ilerletilir

# Von Neumann Modeli (Bir Bilgisayarın...)


<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Fundamental/Capture4.png">


![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Fundamental/Capture4.png)

# Dataflow Modeli (Bir Bilgisayarın...)

* Von Neumann modeli: Bir talimat getirilir ve
kontrol akış sırasına göre yürütülür
    * Komut işaretçisi tarafından belirtildiği gibi
    * Açık kontrol akışı talimatı olmadıkça sıralı

* Dataflow modeli: Bir talimat alınır ve yürütülür
veri akışı sırası
* işlenenleri hazır olduğunda
* komut gösterici yok


* Veri akışı bağımlılığı ile belirtilen talimat sıralaması
    * Her talimat sonucu "kimin" alması gerektiğini   belirtir.
    * Tüm işlenenler alındığında bir talimat    "ateşleyebilir"
* Potansiyel olarak birçok talimat aynı anda yürütülebilir
* Doğası gereği daha paralel

## Von Neumann ve Dataflow

* Bir von Neumann programını düşünün
    * Program sırasının önemi nedir?
    * Depolama yerlerinin önemi nedir?

<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Fundamental/Capture5.png">

![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Fundamental/Capture5.png)

* Bir programcı olarak sizin için hangi model daha doğal?
## Veri Akışı hakkında daha fazla bilgi

* Bir veri akış makinesinde, bir program veri akışından oluşur düğümler.

* Bir veri akış düğümü, her şey tamamlandığında tetiklenir (getirilir ve çalıştırılır).Girişler hazırlanır.
* Tüm girişlerin jetonları(tokens) olduğunda

* Veri akış düğümü ve ISA gösterimi

# ISA düzeyinde Ödünleşim: Talimat İşaretçisi

* ISA'da bir yönerge işaretçisine ihtiyacımız var mı?
* Evet: Kontrol odaklı, sıralı çalıştırma
    * IP onu işaret ettiğinde bir talimat yürütülür
    * IP otomatik olarak sıralı olarak değişir (kontrol akışı dışındaTalimatlar)
* Hayır: Veriye dayalı, paralel yürütme
    * Bir komut, tüm işlenen değerleri olduğunda çalıştırılır.mevcut ( veri akışı )
* Ödünleşimler: BİRÇOK üst düzey olan
    *  Programlama kolaylığı (ortalama programcılar için)?
    *  Derleme kolaylığı?
    *  Performans: Paralelliğin çıkarılması?
    *  Donanım karmaşıklığı?


    * Von Neumann ve Veri akışı yalnızca modellerdir
    * Günümüzde tüm ana komut seti mimarileri bu VonNeumann modeli
    * x86, ARM, MIPS, SPARC, Alpha, GÜÇ


    ## ISA ve Mikro Mimari

    * ISA ve Uarch'ın parçası nedir?
        * Gaz pedalı: "hızlanma" için arayüz
        * Motorun içi: "hızlanma" uygulayın
    * ISA
        * Yazılım ve donanım arasında arayüz üzerinde anlaşmaya varıldı ( SW / derleyici varsayar, HW vaatleri)
        * Programcının yazmak ve hata ayıklamak için bilmesi gerekenler sistem / kullanıcı programları ve kullanıcıya bir sıralı kontrol akışı veya veri akışı yürütme sırası.
    * Mikro mimari
        * ISA'nın özel uygulaması
        * Yazılım veya programcı tarafından görülmez
    * Mikroişlemci
        * ISA, uarch , devreler
        * "Mimari" = ISA + mikro mimari

## ISA Örneği

* Talimatlar
    * İşlem Kodları, Adresleme Modları, Veri Tipleri
    * Talimat Türleri ve Biçimleri
    * Kayıtlar, Durum Kodları
* Bellek

    * Adres alanı, Adreslenebilirlik, Hizalama
    * Sanal bellek yönetimi
* Çağrı, Kesinti / İstisna İşlemleri
* Erişim Kontrolü, Öncelik / Ayrıcalık
* G / Ç: bellek eşlemeli vs. enstr.
* Görev / iş parçacığı Yönetimi
* Güç ve Isı Yönetimi∎ Çoklu iş parçacığı desteği, Çoklu işlemci desteği

## Mikromimari Örneği


* Altında (mikro mimari düzeyinde), yürütme modelineredeyse tüm uygulamalar (veya mikro mimariler) çok farklı
*  Ardışık düzenlenmiş talimat yürütme: Intel 80486 uarch
*  Bir seferde birden fazla talimat: Intel Pentium uarch
* Arıza yürütme: Intel Pentium Pro uarch❑ Ayrı talimat ve veri önbellekleri
* Uygulama (uarch), aşağıdakileri karşıladığı sürece çeşitli olabilir:şartname (ISA)
    * Talimat ekleme ve Toplayıcı uygulaması
        * Bit seri , dalgalanma taşıma , önden taşıma ekleyicileri mikro mimarinin bir parçasıdır
    * x86 ISA'nın birçok uygulaması vardır: 286, 386, 486, Pentium, Pentium Pro,Pentium 4, Çekirdek,…

## Mikromimarlık Değişimi: kontrol ve veri odaklı


* Benzer bir değiş tokuş (kontrol ve veriye dayalı yürütme),mikro mimari seviyesi
* Mikro mimari: Temel uygulama aslında nasıl çalışır?Talimatlar
*  Mikromimarlık, komutları herhangi bir sırayla çalıştırabilir.talimatı verirken ISA tarafından belirtilen semantiğe uyaryazılıma görünür sonuçlar
    *  Programcı ISA tarafından belirtilen sırayı görmelidir.


## (ISA || Uarch)?    

*  ADD komutunun işlem kodu
*  Genel amaçlı kayıt sayısı
*  sicil dosyasına limanların sayısı
*  MUL komutunu yürütmek için döngü sayısı
*  Makinenin boru hattı talimatını kullanıp kullanmadığı icra