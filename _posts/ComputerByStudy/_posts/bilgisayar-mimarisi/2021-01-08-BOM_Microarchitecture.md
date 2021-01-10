---
title: "Bilgisayar Organizasyonu ve Mimarisi - Mikromimariye Giriş: Tek Döngü"
created: Jan 8, 2021 3:02 AM
modified: Jan 8, 2021 3:02 AM
layout: postByComputer
author: Avni Kaşıkçı
date: '2021-01-08 10:02:00'
thumbnail: "/assets/img/posts/hello.jpg"
summary: BOM,ISA Tradeoffs
permalink: "/ComputerEngineer/BOM_Microarchitecture"
category:
- computerStudy
- BOM
- computer
---

## Mikromimariye Giriş: Tek Döngü

***Gözden geçirmek;***
* Günümüz Bilgisayar Mimarisi ve Temelleri
* Temel Kavramlar 
* ISA temelleri ve değiş tokuşları
* Talimat uzunluğu
* Tek tip ve tek tip olmayan kod çözme
* Kayıt sayısı
* Adres modları
* Hizalı ve hizasız erişim
* RISC ve CISC özellikleri






## Mikro mimari aşağıdakileri kapsayacaktır
* Mikromimariye Başlayın
* Tek çevrimli Mikro mimariler
* Çok çevrimli Mikro mimariler
* Mikroprogramlanmış Mikro Mimariler
* Boru hattı döşeme
* Ardışık Düzenlemede Sorunlar: Kontrol ve Veri 
* Bağımlılığı Yönetimi, Durum Bakımı ve Kurtarma


## ISA'nın Uygulanması: Mikromimarinin Temelleri





## Talimat İşleme "Döngüsü"
* Talimatlar, adım adım bir "kontrol ünitesi" yönetimi altında işlenir.
* Talimat döngüsü: Bir talimatı işlemek için adım dizisi
* Temel olarak, altı aşama vardır:
* Fetch
* Kod çözme
* Adresi Değerlendir
* Fetch Operandları
* Yürüt
* Store Sonucu
* Tüm talimatlar altı aşamanın hepsini gerektirmez 




## Bir Makine Talimatları Nasıl İşler?
* Bir talimatın işlenmesi ne anlama gelir?
* Von Neumann modelini hatırlayın
AS = Bir talimat işlenmeden önce Mimari (programcı görünür) durumu
İşlem talimatı
AS ’= Mimari (programcı görünür) bir talimat işlendikten sonraki durum
Talimatın ISA spesifikasyonuna göre "Bir talimatı işleme: AS'yi AS'ye dönüştürme"


## Talimat İşleme "Döngüsü" - Makine Saat Döngüsü
* Tek döngülü makine:
* Komut işleme döngüsünün altı aşamasının tümü, tamamlamak için tek bir makine saat döngüsü alır
* Çok çevrimli makine:
* Komut işleme döngüsünün altı aşamasının tümü, tamamlanması için birden fazla makine saat döngüsü alabilir
* Aslında, her aşamanın tamamlanması birden fazla saat döngüsü alabilir




## Tek döngülü ve Çok Döngülü Makineler
* Tek döngülü makineler
* Her talimat tek bir saat döngüsü alır
* Bir talimatın yürütülmesinin sonunda yapılan tüm durum güncellemeleri
* Büyük dezavantaj: En yavaş talimat döngü süresini belirler 
* Uzun saat döngü süresini
* Çok döngülü makineler
* Birden çok döngüye / aşamaya bölünmüş talimat işleme
* Bir komutun yürütülmesi sırasında durum güncellemeleri yapılabilir
* Yalnızca bir talimatın yürütülmesinin sonunda yapılan mimari durum güncellemeleri
* Tek döngüye göre avantaj: En yavaş "aşama", döngü süresini belirler
* Hem tek döngülü hem de çok döngülü makineler mikro mimari düzeyinde tam anlamıyla von Neumann modelini takip eder



## Talimat İşleme Başka Bir Şekilde Görüntülendi
* 'Talimatlar Verileri (AS) Veriye (AS') dönüştürür
* Bu dönüşüm fonksiyonel birimler tarafından yapılır
* Veriler üzerinde "çalışan" birimler
* Bu birimlere verilere ne yapacaklarının söylenmesi gerekir
* Bir komut işleme motoru iki bileşenden oluşur
* Datapath: Veri sinyalleri ile ilgilenen ve bunları dönüştüren donanım öğelerinden oluşur
* Veriler üzerinde çalışan işlevsel birimler
İşlevsel birimlere ve kayıtlara veri akışını sağlayan donanım yapıları (ör. Teller ve çoklayıcılar)
* Veri depolayan depolama birimleri (ör. Kayıtlar)
* Kontrol mantığı: Kontrol sinyallerini, yani veri yolu öğelerinin verilere ne yapması gerektiğini belirten sinyalleri belirleyen donanım öğelerinden oluşur




## Tek döngü ve Çok döngü: Kontrol ve Veriler
* Tek döngülü makine:
* Kontrol sinyalleri, veri sinyallerinin çalıştırıldığı aynı saat döngüsünde üretilir.
* Bir komutla ilgili her şey bir saat döngüsünde gerçekleşir (serileştirilmiş işlem)
* Çok çevrimli makine:
* Bir sonraki döngüde ihtiyaç duyulan kontrol sinyalleri mevcut döngüde üretilebilir
* Kontrol işlemenin gecikmesi, veri yolu işleminin gecikmesiyle örtüşebilir (daha fazla paralellik)




## Flash-Forward: Performans Analizi
*  Bir talimatın uygulama süresi
*  {CPI} x {saat döngü süresi}
*  Bir programın yürütme süresi
*  Tüm talimatları toplayın [{CPI} x {saat döngü süresi}]
* {# talimat} x {Ortalama CPI} x {saat döngüsü süresi}
* Tek döngülü mikro mimari performansı
* CPI = 1
* Saat çevrim süresi = uzun
* Çok döngülü mikro mimari performansı
* CPI = her talimat için farklı
* Ortalama CPI  umarım küçük
* Saat çevrim süresi = kısa
 
Şimdi, bağımsız olarak optimize etmek için iki serbestlik derecemiz var

## Tek Döngülü Mikro Mimari Daha Yakından Bir Bakış





 <img class="card-img-top" src="{{site.url}}/_posts\ComputerByStudy\_posts\bilgisayar-mimarisi\BOM_Microarchitecture\Capture1.PNG"> 

![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Microarchitecture/Capture1.png)



## Şimdilik Varsayacağız
* "Magic" bellek ve kayıt dosyası
*  Kombinasyonel okuma
Okunan veri portunun çıkışı, kayıt dosyası içeriklerinin ve karşılık gelen okuma seçme portunun kombinasyonel bir fonksiyonudur.
* Eşzamanlı yazma
* Yazma izni verildiğinde seçilen kayıt pozitif kenar saat geçişinde güncellenir
* Saat kenarları arasındaki okuma çıktısını etkileyemez
* Tek döngülü, eşzamanlı bellek
* Verinin ne zaman hazır olduğunu söyleyen bellekle bunu karşılaştırın...
Yani, Hazır bit: okuma veya yazma işleminin tamamlandığını gösterir




![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Microarchitecture/Capture.png)


## sipariş düzenleniyor


* 5 genel adım (P&H kitabı)
* Talimat getirme (IF)
* Komut çözme ve kayıt operand getirme (ID / RF)
* Yürütme / Bellek adresi oluşturma (EX / AG)
* Hafıza operand getirme (MEM)
* Kaydetme / geri yazma sonucu (WB)


![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Microarchitecture/Capture2.png)


![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Microarchitecture/Capture3.png)


## Aritmetik ve Mantıksal Komutlar için Tek Döngülü Veri Yolu

# R-Type ALU Talimatları

![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Microarchitecture/Capture4.png)
## ALU Veri Yolu 
![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Microarchitecture/Capture5.png)

## R - Tipi Uygula

![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Microarchitecture/Capture6.png)

## ALU Veri Yolu

![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Microarchitecture/Capture7.png)

## R - Tipi Uygula

![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Microarchitecture/Capture9.png)


## I-Type ALU Talimatları

* Montaj (ör. Kayıt - hemen imzalanan eklemeler)
Ex. ADDI rtreg rsreg immediate16

* Machine encoding

![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Microarchitecture/Capture10.png)

## Semantics


![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Microarchitecture/Capture11.png)


## R ve I-Type ALU Insts için Veri Yolu.


![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Microarchitecture/Capture12.png)



## Veri Taşıma Talimatları için Tek Döngülü Veri Yolu

# Yükleme Talimatları

* Assembly (e.g., load 4-byte word)
        LW rtreg offset16 (basereg)
* Machine encoding
![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Microarchitecture/Capture13.png)

* Semantics

if MEM[PC]==LW rt offset16 (base)
EA = sign-extend(offset) + GPR[base]
GPR[rt] <- MEM[ translate(EA) ]
PC <- PC + 4

## LW Veri Yolu


![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Microarchitecture/Capture14.png)

if MEM[PC]==LW rt offset16 (base)
EA = sign-extend(offset) + GPR[base]
GPR[rt] <- MEM[ translate(EA) ]
PC <- PC + 4
====>>
Combinational
state update logic

# LW uygula...

![](/_posts/ComputerByStudy/_posts/bilgisayar-mimarisi/BOM_Microarchitecture/Capture15.png)


