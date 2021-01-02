---
title: İşletim Sistemleri
layout: postByComputer
author: Avni Kaşıkçı
date: '2020-10-22 03:02:32'
thumbnail: "/assets/img/posts/hello.jpg"
keywords: using Logic circuits
permalink: "/ComputerEngineer/System-Operation-Tr"
category: [computer, System-Operation]
categoryByComputer: [computer, System-Operation]
categories: [computer, System-Operation]

---

***Kesmlerin Ortak Fonksiyonları***
  

İşletim sistemi,işletim sistemi yazmaçları ve program sayaclarını hafızaya saklıyarak CPU nun durumunu mufaza eder.

  

Şimdi öncelikle bir 'program counter' denilen fonksiyonlardan başlıyalım.şimdi biz kodu derlediğimiz zaman bir birden başlıyarak çalışacak kodları numaralandırırız.Bir progres işlemciye giderken çalışması gereken bir süre vardır.İşlemcide 50 ms süre ile çalışan bir fonksiyon 50 ms yi gecerse debugera gider ve sonra ki fonksiyona geçer.Bu sebeple yarım kalan işlemi bulması için işlemci registera nerede kaldığını program counterını verir ve daha sonra aynı işleme sıra geldği zaman ordan çalışmaya başlar baştan fonksiyonu yazmaz.

  

Aynı zamanda işlemciye hangi tür kesmenin oluştuğunu belirtir.

  

*  **I/O on devices and CPU with run work.**

  

<!-- <img class="card-img-top" src="/assets/img/study/computer-system-operation/kesme-zaman-cizelgesi.png"> -->

  

![](/assets/img/study/computer-system-operation/kesme-zaman-cizelgesi.png)


Yukarıda resimdende anlaşılacağı üzere ilk önce cpu ya gelen bir I O aygıtı mevcut transfer tamamlandıktan sonra görüldüğü gibi CPU da bir kesme oluşur yani işlemci yapıtğı işi bırakıp I/O dan gelen işleme başlar daha sonra kesme işlemi tamamlanır ve kullanıcının işlemine devam eder.I/O cihazi kendi görevini yerine getirir ve bu işlem neticesinde bir interrupt oluşturur. daha sonra bu transfer tamamlanır ve cpu da tekrar bir kesme oluşur. Bu yaşam döngüsü CPU ile I/O cihazları arasındaki ilişki sonsuza kadar bu şekilde devam eder.

**

## I/O Yapısı

Uygulama programları işlketim sistemi yardımıyla I/O isteiğinde bulunabilir.

 - istek **Sistem Çağrısı** yardımıyla yapılır.
 - İşletim sisteminin bir kernelı vardır.Burasını biraz mufaza etmemiz gerekir.
 - İşletim sistemindeki sistem çağrısı rutuni, işletim sistemindeki aygıt sürücüsü rutinleri aracılığıyla I/O işlemini gerçekleştirir.
 - Eğer kernel mudahale edilebilir bir yapıda olsaydı işletim sisteminin güvenliği tehliye girmesi kaçınılmaz olur.
 - Wİn eski versiyonlarda struct action üzerinden windows sistem doslarına erişibilir hale getirilirdi.Bu sebeple o zamanlar fazlaca güvenlik açığı çıktı ve kullanıcıya kernel dosyalarındaki değişikliklerini kullanıcıya sorgulamak için bilgi verir.
 - Linux mimarisinda root ve admin yapıları benzer olmakla beraber linux da su komutu ile süper user yetkisini ele alırsınız.Burada kernel dosyalarını her türlü işleme yetki sahibi olursunuz.
 - Bir progresin çalışmasın iki mod vardır.Bir user mod diğeri root mod.
 - İşletim sistemi burada root modunda kernel dosyalarına izin verir.İşletim sisteminin kernel modundayken kullanıcı mudahalesine çoğu zaman engeller bu engelleme ile işletim sisteminin güvenliğini sağlar eğer muhafaza altında tutulması gereken dosyalar ve I/O trafiği sırasında herhangi bir müdahale oluşursa işletim sistemi güvenliği tehlikeye girer.Bu sebeple kendini kilitler.
 - Kernel progresleri, servisleri güvenlik altında çalışması gerekir.Eğer bir program kerneldaki dosyaları değiştirmesi isteniyorsa bu durumlarda network dll serviceleri vs. kullanılır.Bu durumda araya system code devreye girer.İstek neticesinde program ile istek arasındaki kod bağı kopar ve devreye işletim sistemi kod isteği geçer.
 -İşletim sistemi daha sistemli olması için her aygıtın bir aygıt sürücüsü vardır.
 Eğer I/O istekleri işletim sistemi ile doğrudan yazma ve okuma işlemine sahip olsaydı.Sistem çağrısı olmasaydı işletim sisteminin progres ve dll leri işlem counter sebebiyle sonsuz döngüye girer.
 İşletim sistemi cihaz durum tablosunu yönetir.Her cihaz başına bir giriş bulunur.Bu girişte cihazın durum bilgisi tutulur.
 Eğer bir cihaz bir progres tarafından kullanıbilir ise ikisinede aynı anda izin verirse işlem sırası karışır.Örneğin 20 sayfa çıktı alıcağız 10 10 istekler aynı anda gitti bunu işletim sistemi ayıramaz 20 sayfayı çıkatır fakat 10 10 ile oluşan grupları karıştırır.
 **Çağrı engelleme**
 Eğer istek gönderilir ve sonrasında uygulama aramanın bitmesini bekliyebilir veya başka bir şey yapmaya devam edilebilir.(non-blocing call )
**Depolama Yapıları**
Ram'de bir 
