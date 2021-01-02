---
title: Bilgisayar Organizasyonu ve Mimarisi - Introduction and Basics
created: Jan 1, 2021 3:02 AM
modified: Jan 1, 2021 3:02 AM
layout: postByComputer
author: Avni Kaşıkçı
date: '2021-01-01 03:02:00'
thumbnail: "/assets/img/posts/hello.jpg"
summary: BOM
permalink: "/ComputerEngineer/BOM_Introduction"
category:
- computerStudy
- BOM
- computer
- ''
categories:
- computer
- System-Operation
---

## I Hope You Are Here for This
***"Bilgi işlemin amacı iç görüdür" (Richard Hamming)***
Sorunları çözerek içgörü kazanır ve üretiriz. Sorunların elektronlarla çözülmesini nasıl sağlarız?

# **Soyutlamanın Gücü
# **

# Dönüşüm seviyeleri soyutlamalar yaratır
*  Soyutlama: Daha yüksek bir seviyenin yalnızca  alt seviyenin nasıl olduğuna değil, alt seviyeye arayüz  uygulanır.  Örneğin, üst düzey dil programcısının gerçekten
* ISA'nın ne olduğunu ve bir bilgisayarın talimatları nasıl uyguladığını bilmek.

# Soyutlama üretkenliği artırır;


Bir programcı altta yatan donanım özel kararlarından habersizdir ve bilmeside gerekmek.
Ör. Java, C, derleme, binary ve bytes  her çevrimde her transistörün kontrol sinyallerini belirleme



** Soyutlama Katmanlarını Geçme **

Karar Koşullar Eğer Ne Demek?

Yazdığınız program yavaş mı çalışıyor?

Yazdığınız program düzgün çalışmıyor mu?

Yazdığınız program çok mu enerji tüketiyor?

Tasarladığınız donanımın programlanması çok mu zor?

Çok daha verimli ve daha yüksek performans tasarlamak istiyorsunuz?

Bilgisayar Mimarisindeki tasarım bir geliştirme sanatıdır.donanım bileşenleri birbirine bağlayarakan bir bilgi işlem sistemi oluşturmak tasarımdaki en başlıca kriterlerden biridir.
Bilgisayar 3 temel özellik ihtiyacından ortaya çıkmıştır bunlar;
* Hesaplama
* İletişim
* Saklama(Hafıza)

> # The Von Neumann Model/Architecture
> 
> 
Depolanan program bilgisayarı olarak da adlandırılır (
hafıza). İki temel özellik:
 Kaydedilmiş program;
 
 *Doğrusal bellek dizisinde saklanan talimatlar
 *Bellek, talimatlar ve veriler arasında birleştirilmiştir
 *Kaydedilen bir değerin yorumlanması, kontrol ünitesine bağlıdır.
 
 
 Sıralı talimat işleme;
 
* Bir talimat bir anda işlendi (getirildi, yürütüldü ve tamamlandı)
* Program sayacı (komut işareti) mevcut enstrümanı tanımlar.
* Program sayacı, kontrol aktarımı dışında sıralı olarak geliştirilir

# The von Neumann Model (of a Computer)  
 <img class="card-img-top" src="/assets/img/posts/ComputerByStudy/Bilgisayar-Mimarisi/Bilgisayar_Organizasyonu_ve_Mimarisi-Introduction_and_Basics/The-von-Neumann-Model-(of-a Computer).png">
 
 # Dataflow Modeli (Bir Bilgisayarın) 
 
 Von Neumann modeli: Bir talimat getirilir ve kontrol akış sırasına göre yürütülür.
 * Komut işaretçisi tarafından belirtildiği gibi
 * Açık kontrol akışı talimatı olmadıkça sıralı
 
Dataflow modeli: Bir talimat alınır ve yürütülür
veri akışı sırası
* i.e, işlenenleri hazır olduğunda
* i.e, komut gösterici yok
* Veri akışı bağımlılığı ile belirtilen talimat sıralaması
* Her talimat sonucu "kimin" alması gerektiğini belirtir
* Tüm işlenenler alındığında bir talimat "ateşleyebilir"
* Potansiyel olarak birçok talimat aynı anda yürütülebilir
* Doğası gereği daha paralel


# Von Neumann vs Dataflow #

Bir von Neumann programını düşünün
* Program sırasının önemi nedir?
* Depolama yerlerinin önemi nedir?

 <img class="card-img-top" src="{{site.url}}/assets/img/posts/ComputerByStudy/Bilgisayar-Mimarisi/Bilgisayar_Organizasyonu_ve_Mimarisi-Introduction_and_Basics/von-Neumann-vs-Dataflow">
 
 
 Bir veri akış makinesinde, bir program veri akışından oluşur. Bir veri akış düğümü, her şey tamamlandığında tetiklenir (getirilir ve çalıştırılır). ISA nın veri akış düğümü ve Isa gösterimi aşağıdaki görseldedir.



 <img class="card-img-top" src="/assets/img/posts/ComputerByStudy/Bilgisayar-Mimarisi/Bilgisayar_Organizasyonu_ve_Mimarisi-Introduction_and_Basics/ISASHOW.png">


# ISA DÜZEYİNDE TALİMATLAR #

ISA'da bir yönerge işaretcisine sizce gerçekten gerek varmı ?
Bu soruya iki farklı cevap verebiliriz.
Evet var cünkü kodtol odaklı sıralı çalıştırma prensibine göre çalışır ve ip onu gösterdeğinde bir talimat yürütülür.ip otomatik olarak sıralı olarak değişşir tabi kontrol akışı dışında bir talimat yok ise.Örneğin evimizdeki modeme yeni bir cihaz erişim istediğinde otomatik olarak sıradaki ip numarası ona verilir ve modem üzerinden o cihaza erişim sağlıyabilirsiniz bu sadece localdaki cihazlar için geçerlidir.Dışarıdaki bir cihaza bu şekilde ip atanmaz.

Isanın realist örnekleri aşağıda sıralıdır.

* İşlem Kodları, Adresleme Modları, Veri Tipleri
* Komut Türleri ve Biçimleri
* Kayıtlar, Durum Kodları
* Hafıza
* Adres alanı, Adreslenebilirlik, Hizalama
* Sanal bellek yönetimi
* Çağrı, Kesinti / İstisna İşlemleri
* Erişim Kontrolü, Öncelik / Ayrıcalık
* G / Ç: bellek eşlemeli vs. enstr.
* Görev / iş parçacığı Yönetimi
* Güç ve Isı Yönetimi
* Çoklu iş parçacığı desteği, Çoklu işlemci desteği
