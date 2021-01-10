---
title: Bilgisayar Organizasyonu ve Mimarisi - ISA Tradeoffs
created: Jan 5, 2021 3:02 AM
modified: Jan 5, 2021 3:02 AM
layout: postByComputer
author: Avni Kaşıkçı
date: '2021-01-05 10:02:00'
thumbnail: "/assets/img/posts/hello.jpg"
summary: BOM,ISA Tradeoffs
permalink: "/ComputerEngineer/BOM_ISA-Tradeoffs"
category:
- computerStudy
- BOM
- computer
- ISA Tradeoffs
---

## Tasarım Noktası

***Bir dizi tasarım düşüncesi ve önemi;***
* Hem ISA hem de uarch'ta değiş tokuşlara yol açar.
*** Düşünceler ***
* Maliyet
* Performans
* Maksimum güç tüketimi
* Enerji tüketimi (pil ömrü)
* Kullanılabilirlik
* Güvenilirlik ve Doğruluk
* Pazara Giriş Süresi

***"Problem" alanı tarafından belirlenen tasarım noktası (uygulama alanı) veya hedeflenen kullanıcılar / pazar***

## Yıllar Boyunca Birçok Farklı ISA


* x86
* PDP-x: Programmed Data Processor (PDP-11)
* VAX
* IBM 360
* CDC 6600
* SIMD ISAs: CRAY-1, Connection Machine
* VLIW ISAs: Multiflow, Cydrome, IA-64 (EPIC)
* PowerPC, POWER
* RISC ISAs: Alpha, MIPS, SPARC, ARM


* Temel farklılıklar nelerdir?
* Örneğin, talimatların nasıl belirtildiği ve ne işe yaradığı
* Ör. Talimatlar ne kadar karmaşık?


## Why Is It (Somewhat) Art?
* We do not (fully) know the future (applications, users, market)


 <img class="card-img-top" src="{{site.url}}/assets/img/posts/ComputerByStudy/Bilgisayar-Mimarisi/Bilgisayar_Organizasyonu_ve_Mimarisi-Introduction_and_Basics/The-von-Neumann-Model-(of-a-Computer).png">

 
* Geleceği (tam olarak) bilmiyoruz (uygulamalar, kullanıcılar, pazar)

## Tradeoffs: Bilgisayar Mimarisinin Ruhu


## ISA düzeyinde ödünleşimler
* Mikromimarlık düzeyinde ödünleşimler
* Sistem ve Görev düzeyinde değiş tokuşlar
* İş gücü donanım ve yazılım arasında nasıl bölünür
* Bilgisayar mimarisi, bir tasarım noktasını karşılamak için uygun ödünleşmeler
* Neden sanat?


## ISA İlkeleri ve Ödünleşmeler

## TALİMAT NEDİR?


Talimat;
* Donanım / Yazılım arayüzünün temel öğesi
* Şunlardan oluşur:
* opcode: talimat ne yapar
* işlenenler: kime yapılacak
* Alpha ISA'dan örnek:

<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_ISA-Tradeoffs/Capture.png">

<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_ISA-Tradeoffs/Capture2.png">

## Talimatlar, Kodlama ve Özellikler Seti

<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_ISA-Tradeoffs/Capture3.png">

  


 ## LC-3b ISA'dan örnek
* http: //www.ece.utexas.edu/~patt/11s.460N/elouts/new_byte.pdf
* x86 Kılavuzu
* Neden kullanılmayan talimatlar?
* Talimatta biraz belirler diğerinin yorumu bitler

## Alfa'da Bit Yönlendirme

<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_ISA-Tradeoffs/Capture4.png">



## Talimat işleme stili
* Bir talimatın "çalıştırdığı" "işlenen" sayısını belirtir 
* 0, 1, 2, 3 adres makineleri
* 0-adres: yığın makinesi (push A, pop A, op)
* 1-adres: akümülatör makinesi (ld A, st A, op A)
* 2 adresli: 2 işlenen makine (biri hem kaynak hem de hedeftir)
* 3-adres: 3-işlenen makine (kaynak ve hedef ayrıdır)
* Ödünleşmeler? Ödev sorunuzu görün
* Daha büyük çalıştırma talimatları ve daha çok yürütülen işlem
* Kod boyutu - yürütme süresi - çip üzerinde bellek alanı


## Bir Örnek: Yığın Makinesi
+ Küçük komut boyutu (çalışma için işlenen gerekmez Talimatlar)
* Daha basit mantık
* Kompakt kod
+ Etkili prosedür çağrıları: yığındaki tüm parametreler
* Parametre geçişi için ek döngü yok
- "postfix" ile kolayca ifade edilemeyen hesaplamalar "notasyonu", makineleri istiflemek için eşlemek zordur
* Aynı anda birçok değer üzerinde işlem gerçekleştirilemez(aynı anda yalnızca yığındaki ilk N değerleri)
* Esnek değil

## Bir Örnek: Yığın Makinesi Çalışması

<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_ISA-Tradeoffs/Capture5.png">



Koopman, “Stack Computers:The New Wave,” 1989.
http://www.ece.cmu.edu/~koopman/stack_computers/sec3_2.html


## Diğer Örnekler
* PDP-11: 2 adresli bir makine
* PDP-11 ADD: 4 bit işlem kodu, 26 bit işlenen belirleyicileri
* Neden? Bir talimatı belirtmek için sınırlı bitler
* Dezavantaj: Bir kaynak işlenen her zaman talimatın sonucu
* Kaynağın eski değerini koruduğunuzdan nasıl emin oluyorsunuz?
* X86: 2 adresli (bellek / bellek) makine
* Alpha: 3 adresli (yükleme / saklama) bir makine
* MIPS?
* ARM?

# Veri türleri #

 ***Tanım: Orada bulunan bilgilerin temsili temsil üzerinde işleyen talimatlardır***
* Tam sayı, kayan nokta, karakter, ikili, ondalık, BCD
* Çift bağlantılı liste, sıra, dizi, bit vektörü, yığın
* VAX: INSQUEUE ve REMQUEUE talimatları iki katına çıkar bağlantılı liste veya kuyruk; FINDFIRST
* Digital Equipment Corp., "VAX11 780 Architecture Handbook"1977.
* X86: SCAN işlem kodu karakter dizileri üzerinde çalışır; İTME / POP


# Veri Türü Değişimi #
* Daha fazla veya üst düzey veri türüne sahip olmanın faydası nedir ISA'da?
* Dezavantajı nedir?
* Derleyici / programcı ile mikro mimariyi düşünün
* Anlamsal boşluk kavramı
* Anlamsal düzeye veya karmaşıklığa sıkı sıkıya bağlı veri türleri talimatların
* Örnek: Erken RISC mimarilerine karşı Intel 432
* Erken RISC: Yalnızca tam sayı veri türü
* Intel 432: Nesne veri türü, yeteneklere dayalı makine


# Hafıza organizasyonu #
* Adres alanı: Bellekte kaç tane benzersiz şekilde tanımlanabilir konum
* Adreslenebilirlik: Her bir benzersiz olarak tanımlanabilir konum ne kadar veri yapar mağaza
* Adreslenebilir bayt: çoğu ISA, karakterler 8 bittir
* Bit adreslenebilir: Burroughs 1700. Neden?
* 64 bit adreslenebilir: Bazı süper bilgisayarlar. Neden?
* 32 bit adreslenebilir: İlk Alfa
* Düşünce için yiyecek
* Yalnızca bayt adreslenebilirliği olan 2 adet 32 ​​bitlik sayıyı nasıl eklersiniz?
* Yalnızca 32 bit adreslenebilirliğe sahip 8 bitlik 2 sayıyı nasıl eklersiniz?
* Büyük endian mı, küçük endian mı? Düşük veya yüksek baytta MSB.
* Sanal bellek desteği

# Kayıtlar(Registers) #
* Kaç tane
* Her kaydın boyutu
* Kayıtlara sahip olmak neden iyi bir fikirdir?
* Programlar veri yerelliği adı verilen bir özellik sergilediği için
* Yakın zamanda üretilen / erişilen bir değerin daha fazla kullanılması muhtemeldir.birden çok kez (geçici yerellik)
* Bu değeri bir kayıt defterinde saklamak, kayıtlara gitme ihtiyacını ortadan kaldırır.Bu değere her ihtiyaç duyulduğunda bellek




# Register Mimarisinin Gelişimi #
* Akümülatör
* "ekleyen" makine günlerinden bir miras
* Akümülatör + adres kayıtları
* kayıt yönlendirmesi gerekiyor
* Başlangıçta adres kayıtları özel amaçlıydı, yani yalnızca yönlendirme için bir adres ile yüklenecek
* sonunda adreslerde aritmetik desteklendi
* Genel amaçlı kayıtlar (GPR)
* tüm kayıtlar tüm amaçlar için iyidir
* birkaç kayıttan 32'ye (RISC için ortak), 128 inç'e çıktı
Intel IA-64

# Öğretim Sınıfları #
* Çalıştırma talimatları
* İşlem verileri: aritmetik ve mantıksal işlemler
* Getirme işlenenleri, hesaplama sonucu, mağaza sonucu
* Örtülü sıralı kontrol akışı
* Veri taşıma talimatları
* Verileri bellek, kayıtlar, I / O cihazları arasında taşıyın
* Örtülü sıralı kontrol akışı
* Kontrol akışı talimatları
* Yürütülen talimatların sırasını değiştirin

# Adresleme Modu #
* Bellek mimarilerine karşı yükleme / depolama
* Yükleme / depolama mimarisi: çalıştırma talimatları yalnızca kayıtlarda çalışır
* Örneğin, MIPS, ARM ve birçok RISC ISA
* Bellek mimarisi: çalıştırma talimatları bellek konumlarında çalışabilir
* Ör. X86, VAX ve birçok CISC ISA


# Adresleme Modu #
* Adresleme modları, işlenenlerin nasıl elde edileceğini belirtir
* Deplasman hareketli balta, [1000] anlık değeri adres olarak kullan
* Dolaylı Register: hareketli balta, [esi] kayıt adresini adres olarak kullan
* Yer değiştirmiş veya temelli: hareketli balta, [bx] [si] adres olarak temel kaydı ve dizin kaydını kullan
* Dizine alınmış: hareketli balta, var1 [esi] adres olarak kullan

# Farklı Adresleme Modlarının Faydaları Nelerdir? #
* Başka bir programcı ve mikro mimarlık değiş tokuşu örneği
* Daha fazla adresleme modunun avantajı:
* Üst düzey yapıların makineye daha iyi eşlenmesini sağlar: bazı erişimler farklı bir modla daha iyi ifade edilir 
* Azaltılmış talimat sayısı ve kod boyutu
* Dizi erişimlerini düşünün (otomatik artış modu)
* Yönlendirmeyi düşünün (işaretçi kovalayan)
* Seyrek matris erişimleri
* Dezavantaj:
* Derleyici için daha fazla iş
* Mikro mimar için daha fazla iş
* Hangisi daha hızlı?


# Talimat Süresi #
* Sabit uzunluk: Tüm talimatların uzunluğu aynı
+ Donanımdaki tek talimatın kodunu çözmek daha kolay
+ Birden fazla talimatı aynı anda çözmek daha kolay
- Talimatlarda boşa harcanan parçalar (Bu neden kötü?)
- Genişletmesi daha zor ISA (yeni talimatlar nasıl eklenir?)
* Değişken uzunluk: Talimatların uzunluğu farklı (işlem kodu ve alt işlem kodu ile belirlenir)
+ Kompakt kodlama (Bu neden iyi?) Intel 432: Huffman kodlaması (tür). 6 ila 321 bit talimatlar. Nasıl?
- Tek bir talimatı çözmek için daha fazla mantık
- Aynı anda birden fazla talimatın kodunu çözmek daha zor
## Ödünleşimler
* Kod boyutu (bellek alanı, bant genişliği, gecikme) ile donanım karmaşıklığı karşılaştırması
* ISA genişletilebilirliği ve ifadesi ile donanım karmaşıklığı
* Performans? Enerji? Daha küçük kod ve kod çözme kolaylığı

# Tek Tip Kod Çözme #
*** Tek tip kod çözme: Her komuttaki aynı bitler aynı anlama karşılık gelir ***
* İşlem kodu her zaman aynı konumdadır
* İşlenen belirteçleri, anlık değerler,… ile aynı
* Birçok "RISC" ISA: Alpha, MIPS, SPARC
+ Daha kolay kod çözme, daha basit donanım
+ Paralelliği etkinleştirir: talimatın bir dal olduğunu bilmeden önce hedef adresi oluşturun
- Talimat formatını kısıtlar (daha az talimat?) Veya alanı boşa harcar
# Tek tip olmayan kod çözme
* Örneğin, opcode x86'da 1.-7. bayt olabilir
+ Daha kompakt ve güçlü talimat formatı
- Daha karmaşık kod çözme mantığı


## Uzunluk ve Tekdüzelik Üzerine Bir Not ##
* Tek tip kod çözme genellikle sabit uzunlukta gider
* Değişken uzunluklu bir ISA'da, tek tip kod çözme bir özellik olabilir.
* Aynı uzunluktaki talimatların, Farklı kişilerin talimatlarının bir özelliği olarak düşünmek zordur.Uzunluklar


## Hizalanmış ve Hizalanmamış erişim ##
* CPU HER ZAMAN kelime boyutunda (32 bit işlemcide 4 bayt) okur.Hizalanmamış bir adres erişimi;
- Onu destekleyen bir işlemcide - işlemci,birden çok kelime oku. CPU, talep ettiğiniz her bir bellek kelimesini okuyacaktır.
* Adres straddles. Bu, bellek sayısının 2 katına kadar yükseltilmesine neden olur istenen verilere erişmek için gerekli işlemler.

* Bu nedenle, iki baytı okumak dörtten çok kolaylıkla daha yavaş olabilir. Örneğin,hafızada şuna benzeyen bir yapınız olduğunu söyleyin:


> struct mystruct {
>char c; // one byte
>int i; // four bytes
>short s; // two bytes
>} 

* X86 Hizalanmamış erişimi yönetir ve MIP'ler yalnızca Hizalanmış erişimle ilgilenir, aksi takdirde
adres istisnası ver

# Karmaşık talimat:
* Bir talimat çok iş yapar, ör. 
birçok işlem
* Çift bağlantılı bir listeye ekleyin
* Dize kopyası
# Basit talimat: Bir talimat, küçük miktarda
iş, karmaşık işlemlerin yapabileceği ilkel bir
inşa edilmek
* Ekle
* ÖZELVEYA
* Çarp


# Karmaşık ve Basit Talimatlar
* Karmaşık talimatların avantajları
+ Daha yoğun kodlama
* daha küçük kod boyutu
* daha iyi bellek
kullanım, çip dışı bant genişliğinden tasarruf sağlar, daha iyi önbellek isabet oranı
(talimatların daha iyi paketlenmesi)
+ Daha basit derleyici: küçük talimatları optimize etmeye gerek yok

* Karmaşık Komutların Dezavantajları
- Daha büyük iş parçalarının  derleyicisinin
optimize edin (yapabileceği ayrıntılı optimizasyonlarla sınırlıdır)
- Daha karmaşık donanım  üst düzeyden
kontrol sinyalleri ve optimizasyonun donanım tarafından yapılması gerekiyor


#ISA düzeyinde Ödünleşimler;
## Anlamsal Boşluk
* ISA nereye yerleştirilir? Anlamsal boşluk
* Yüksek seviyeli dile (HLL) daha yakın
* Küçük anlamsal boşluk, karmaşık talimatlar
* Donanım kontrol sinyallerine daha mı yakın? 
* Büyük anlamsal boşluk,basit talimatlar
* RISC ve CISC makineleri
* RISC: Azaltılmış komut seti bilgisayarı
* CISC: Karmaşık komut seti bilgisayarı
* FFT, QUICKSORT, POLY, FP talimatları?
* VAX INDEX komutu (sınır kontrolü ile dizi erişimi)



# Küçük ve Büyük Anlamsal Boşluk
## CISC ve RISC
* Karmaşık komut seti bilgisayarı
* karmaşık Talimatlar
* Başlangıçta "yeterince iyi değil" kod üretimi ile motive edildi
* Azaltılmış komut seti bilgisayarı  basit talimatlar
* John Cocke, 1970'lerin ortası, IBM 801
* Hedef: daha iyi derleyici kontrolü ve optimizasyonu sağlamak
* RISC,
* Donanımın basitleştirilmesi  daha düşük maliyet, daha yüksek frekans
* Derleyicinin kodu daha iyi optimize etmesini sağlama
* Durmaları azaltmak için ince taneli paralellik bulun



# Ne Kadar Yükseğe veya Alçağa Gidebilirsiniz?
* Çok büyük anlamsal boşluk
* Her komut, içindeki kontrol sinyallerinin tam setini belirtir.
makine
* Derleyici kontrol sinyalleri üretir
* Açık mikro kod (John Cocke, yaklaşık 1970'ler)
* Derleyicileri optimize etmenin yolunu açtı
* Çok küçük anlamsal boşluk
* ISA (neredeyse) üst düzey dil ile aynıdır
* Java makineleri, LISP makineleri, nesne yönelimli makineler,
yetenek tabanlı makineler



# RISC ve CISC'ye Karşı Bir Not
* Genellikle…
* RISC
* Basit talimatlar
* Sabit uzunluk
* Tek tip kod çözme
* Birkaç adresleme modu
* CISC
* Karmaşık talimatlar
* Değişken uzunluk
* Tek tip olmayan kod çözme
* Birçok adresleme modu


# ISA Evrimi Üzerine Bir Not
***ISA'lar günün endişelerini yansıtacak / tatmin edecek şekilde gelişti***
## Örnekler:
* Sınırlı yonga üzerinde ve yonga dışı bellek boyutu
* Sınırlı derleyici optimizasyon teknolojisi
* Sınırlı bellek bant genişliği
* Önemli uygulamalarda uzmanlaşma ihtiyacı (örneğin, MMX)
* Çeviri kullanımı (HW ve SW'de) altta yatan etkin
ISA'dan bağımsız olarak benzer uygulamalar
* Dinamik / statik arayüz kavramı
* Donanım / yazılım arayüzüyle karşılaştırın


## Çevirinin Etkisi
* Değiştirmek için bir ISA'dan başka bir ISA'ya çeviri yapılabilir
anlamsal boşluk değiş tokuşları
## Örnekler
* Intel’in ve AMD’nin x86 uygulamaları x86’yı çevirir
programcı tarafından görünmeyen mikro işlemlerle ilgili talimatlar (basit
talimatlar) donanımda
* Transmeta’nın x86 uygulamaları, x86 talimatlarını tercüme etti
yazılımda "gizli" VLIW talimatlarına (kod dönüştürme
yazılım)
* Değiş tokuşları düşünün
