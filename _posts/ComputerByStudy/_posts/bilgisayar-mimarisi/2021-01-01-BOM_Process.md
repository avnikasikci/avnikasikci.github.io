---
title: Bilgisayar Organizasyonu ve Mimarisi - İşlemci Mimarisi
created: Jan 11, 2021 3:02 AM
modified: Jan 11, 2021 3:02 AM
layout: postByComputer
author: Avni Kaşıkçı
date: '2021-01-11 03:02:00'
thumbnail: "/assets/img/posts/hello.jpg"
summary: BOM
permalink: "/ComputerEngineer/BOM_Process"
category:
- computerStudy
- BOM
- computer
categories:
- computer
- System-Operation
---




 Genel Kavramlar

     CPU Tasarımı, Talimat yürütme döngüsü

 IA-32 İşlemci Mimarisi

     İşlem modları, CPU Kayıtları ve Bayrakları, Intel CPU Geçmişi

 IA-32 Bellek Yönetimi

     Gerçek adres modu, bölümlere ayrılmış bellek, sayfalama

 Giriş-Çıkış Sistemi

     Giriş / çıkış sistemi seviyeleri


## Anahat

 Programları Birleştirme, Bağlama ve Çalıştırma

 Assembly Dilinin Temel Öğeleri

 Örnek: Tamsayı Toplama ve Çıkarma

 Verileri Tanımlama

 Sembolik Sabitler

 Gerçek Adres Modu Programlama


## Anahat

 **Programları Birleştirme, Bağlama ve Çalıştırma**

 Assembly Dilinin Temel Öğeleri

 Örnek: Tamsayı Toplama ve Çıkarma

 Verileri Tanımlama

 Sembolik Sabitler

 Gerçek Adres Modu Programlama


## Assemble-Link Yürütme Döngüsü

 Aşağıdaki şema, bir kaynak oluşturmanın adımlarını açıklamaktadır.program derlenmiş programı çalıştırarak.

 Kaynak kodu değiştirilirse, 2'den 4'e kadar olan Adımlar tekrarlanmalıdır.




<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Process\capture1.png">
![](image/capture1.PNG)
## Liste Dosyası

 Programınızın nasıl derlendiğini görmek için kullanın

 Projeden sonra adlandırılır, örneğin proje.lst

 Baskıya uygun

 Şunları içerir;

     kaynak kodu
    
     adresler
    
     nesne kodu (makine dili)
    
     segment adları
    
     semboller (değişkenler, prosedürler ve sabitler)



 *Ayrıntılı açıklamalı 72-74. Sayfalardaki örnek*- **LÜTFEN OKUYUN!**

## Anahat

 Programları Birleştirme, Bağlama ve Çalıştırma

 Assembly Dilinin Temel Öğeleri

 Örnek : Tamsayı Toplama ve Çıkarma


 Verileri Tanımlama

 Sembolik Sabitler

 Gerçek Adres Modu Programlama

## Basit elementler

 Tamsayı sabitleri ve ifadeleri

 Karakter ve dize sabitleri

 Ayrılmış kelimeler ve tanımlayıcılar

 Yönergeler ve talimatlar

 Etiketler

 Anımsatıcılar ve İşlemciler

 Yorumlar

## Tamsayı Sabitleri

[{+ | -} basamak [taban]

 İsteğe bağlı önde gelen + veya - işareti

 İkili, ondalık, onaltılık

 Yaygın taban karakterleri:

<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Process\capture2.png">

![](image/capture2.PNG)

Örnekler: 30d, 6Ah, 42, 1101b

Onaltılık bir harfle başlayamaz: 0A5h

## Tamsayı İfadeler

 Montaj zamanında değerlendirildi

<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Process\capture3.png">

![](image/capture3.PNG)

 Örnekler:
<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Process\capture4.png">


![](image/capture4.PNG)

## Karakterler ve Dizeler

 Karakteri tek veya çift tırnak içine alın

     'A', "x"

     ASCII karakteri = 1 bayt

 Dizeleri tek veya çift tırnak içine alın

     "ABC"

     'xyz'

     Her karakter tek bir bayt kaplar

 Gömülü alıntılara izin verilir:

     "" İyi geceler "deyin Gracie '

     "Bu bir test değil"

## Ayrılmış Kelimeler ve Tanımlayıcılar

 Ayrılmış sözcükler tanımlayıcı olarak kullanılamaz

     Talimat anımsatıcıları, yönergeleri, tür öznitelikleri, operatörler,önceden tanımlanmış semboller
    
     Ek A'daki MASM referansına bakın

 Tanımlayıcılar

     1-247 karakter, rakamlar dahil
    
     büyük / küçük harfe duyarlı değil
    
     ilk karakter bir harf, _, @,? Veya $ olmalıdır
    
     etiketler (prosedür isimleri, değişkenler), sabitler için kullanılır


## Direktifler

 Montajın nasıl yapılacağına ilişkin talimatlar (@ runtime değil)

 Montajcı tarafından tanınan ve uygulanan komutlar

     Intel talimat setinin parçası değil

     kodu, veri alanlarını bildirmek, bellek modelini seçmek, bildirmek için kullanılırprosedürler, değişkenler vb.

     büyük / küçük harfe duyarlı değildir (.data, .DATA ve .Data)

 Farklı montajcıların farklı direktifleri vardır

     GNU assembler, netwide assembler, MASM ile aynı değil


## Yönergeler: Segmentleri Tanımlama

 assembler direktiflerinin önemli bir işlevi,program bölümlerini veya segmentlerini tanımlayın

    - data

    - code

    - stack 100h


## Intel Talimatları

 assembler tarafından makine koduna monte edilir

 CPU tarafından çalışma zamanında yürütülür

 Bir talimat şunları içerir:

     Etiket
    (isteğe bağlı)

     Anımsatıcı
    (gereklidir)

     Operand (lar)
    (talimatlara göre değişir)

     Yorum
    (isteğe bağlı) - ';' ile başlar

[etiket:] anımsatıcı [işlenenler] [; yorum]

loop1: moveax, 32; dizi öğelerinin sayısı

## Etiketler

 Yer işaretçisi olarak hareket edin

     kod ve verilerin adresini (ofset) işaretler

 Tanımlayıcı kurallara uyun

 Veri etiketi (Değişken adları)

     benzersiz olmalıdır

     örnek: DWORD 100'ü sayın
    (ardından iki nokta üst üste gelmez)

 Kod etiketi

     atlama ve döngü talimatlarının hedefi

     örnek: L1:
    (ardından iki nokta üst üste)

<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Process\capture5.png">

![](image/capture5.PNG)

 No operands

     stc                ; Carry bayrağını ayarla


 One operand

     inc eax                    ; Kayıt ol

     inc myByte                 ; hafıza

 Two operands

     add ebx,ecx                ; kayıt ol

     sub myByte,25              ; hafıza, sabit
    
     add eax,36 * 25            ; reg, const-expr


## NOP Talimatı

 İşlem Yok

     En güvenli ve en yararsız talimat

 1 baytlık depolama kullanır

 CPU: Okur, Kodunu Çözer, Yok Sayar

 Genellikle kodu çift adres sınırlarına hizalamak için kullanılır(4'ün katı):

00000000668BC3movax,bx 

0000000390nop;alignnextinstruction

000000048BD1movedx,ecx 

 x86 işlemciler kodu ve verileri daha fazla yüklemek için tasarlanmıştırçift ​​kelime adreslerinden bile hızlı bir şekilde.

## Anahat

 Programları Birleştirme, Bağlama ve Çalıştırma

 Assembly Dilinin Temel Öğeleri

 Örnek: Tamsayı Toplama ve Çıkarma

 Verileri Tanımlama

 Sembolik Sabitler

 Gerçek Adres Modu Programlama (!!!)

    TITLE Program Template             (Template.asm)

    .data

     (değişkenleri buraya girin) 
    .code
    main PROC
        ; (çalıştırılabilir talimatları buraya ekleyin) 

    main ENDP
        ; (ek prosedürleri buraya ekleyin)

    END main

## Örnek: Tamsayı Toplama ve Çıkarma

    TITLE Add and Subtract           (AddSub.asm)

; Bu program 32 bitlik tam sayıları ekler ve çıkarır.


    INCLUDE Irvine32.inc

    .code

    main PROC
        moveax,10000h                ; EAX = 10000h 
        add eax,40000h               ; EAX = 50000h 
        sub eax,20000h               ; EAX = 50000h 
        call DumpRegs                ; display registers 
        exit 
    main ENDP

    main ENDP

## Örnek Çıktı

 Kayıtları ve bayrakları gösteren program çıktısı:

    EAX=00030000   EBX=7FFDF000  ECX=00000101  EDX=FFFFFFFF 
    ESI=00000000   EDI=00000000  EBP=0012FFF0  ESP=0012FFC4 
    EIP=00401024   EFL=00000206  CF=0  SF=0  ZF=0  OF=0

## Olası Kodlama Standartları

 Büyük harf kullanımı
     Anımsatıcılar ve kayıt adları dahil olmak üzere, ayrılmış sözcükleri büyük harfle yazın

     Hiçbir şeyi büyük harfle yazmayın
    
     İlk harfleri büyük yap

 Açıklayıcı tanımlayıcı adları kullanın

 Girinti ve boşluk

     kod ve veri etiketleri - girinti yok
    
     çalıştırılabilir talimatlar - 4-5 boşluk girintisi (1 sekme)
    
     yorumlar: sayfanın sağ tarafı, dikey olarak hizalanmış
    
     Komut ve işlenenleri arasında 1-3 boşluk (1 sekme)
    
     Prosedürler arasında 1-2 boş satır

##  Örnek: Tamsayı Toplama ve Çıkarma 2 nd versiyonu

    TITLE Add and Subtract        (AddSub2.asm)

    ; Bu program 32 bitlik tam sayıları ekler ve çıkarır.    
    ; Dahil olmadan
    .386
    .model flat, stdcall
    .stack 4096
    ExitProcessPROTO, dwExitCode:DWORD
    DumpRegsPROTO

    .code

    main PROC
        moveax,10000h          ; EAX = 10000h 
        add eax,40000h         ; EAX = 50000h
        sub eax,20000h         ; EAX = 30000h 
        call DumpRegs          ; ekran kayıtları
        INVOKE ExitProcess, 0 
    main ENDP

    END main

## Anahat

 Programları Birleştirme, Bağlama ve Çalıştırma

 Assembly Dilinin Temel Öğeleri

 Örnek: Tamsayı Toplama ve Çıkarma

 Verileri Tanımlama

 Sembolik Sabitler

 Gerçek Adres Modu Programlama

## Temel Veri Türleri

 BYTE, SBYTE: 8-bit işaretsiz ve işaretli tamsayılar

 KELİME, KILIÇ: 16 bit işaretsiz ve işaretli tamsayılar

 DWORD, SDWORD: 32-bit işaretsiz ve imzalı tamsayılar

 QWORD: 64 bit tam sayı

     Not: İmzalanmamış / imzalanmamış

 TBYTE: 80 bit (on bayt) tam sayı

 REAL4, REAL8: 4 bayt kısa ve 8 bayt uzun gerçekler

 REAL10: 10 baytlık IEEE genişletilmiş gerçek


## Eski Veri Direktifleri


<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Process\capture6.png">


![](image/capture6.PNG)

    Netwide Assembler (NASM) tarafından da desteklenir 
                ve Turbo Assembler (TASM)


## Veri Tanımlama Beyanı

 Bir veri tanımlama ifadesi, bir değişken için bellekte depolamayı bir kenara koyar.

 İsteğe bağlı olarak verilere bir ad (etiket) atayabilir

 Sözdizimi:

<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Process\tempsnip.png">

![](image/tempsnip.png)

 kullanın ? Tanımlanmamış değişkenler için sembol

 Tüm başlatıcılar bellekte ikili veri haline gelir

     00110010b, 32h ve 50d'nin tümü aynı ikili değere sahip olur

## BYTE, SBYTE Verilerinin Tanımlanması

 Aşağıdakilerin her biri tek bir depolama baytını tanımlar:
    
    value1 BYTE 'A'           ; karakter sabiti
    value2 BYTE 0             ; en küçük işaretsiz bayt
    value3 BYTE 255           ; en büyük işaretsiz bayt
    value4 SBYTE -128         ; en küçük işaretli bayt
    value5 SBYTE +127         ; en büyük işaretli bayt
    value6 BYTE ?             ; başlatılmamış bayt

 İsteğe bağlı ad, değişkenin başlangıçtan itibaren ofsetini işaretleyen bir etikettironu çevreleyen segmentte.

     değer1, veri segmentinde 0000 ofsetinde bulunuyorsa ve 1 baytdepolama, değer2 otomatik olarak 0001 ofsetinde bulunur

 MASM, bir BYTE'yi negatif bir değerle (zayıf stil) başlatmanıza izin verir

 Bir SBYTE değişkeni bildirirseniz, Microsoft hata ayıklayıcı otomatik olarakdeğerini önde gelen bir işaretle ondalık olarak görüntüler.

## Bayt Dizilerini Tanımlama

 Birden çok başlatıcı kullanan örnekler:

    list1 BYTE 10,20,30,40
    list2 BYTE 10,20,30,40
          BYTE 50,60,70,80
          BYTE 81,82,83,84
    list3 BYTE ?, 32,41h, 00100010b
    list4 BYTE 0Ah, 20h, 'A', 22h


<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Process\capture7.png">

    ![](image/capture7.PNG)

     Bir dizi basitçe bir dizi sıralı bellek konumudur

     yönergesi (BYTE) almak için gerekli ofset gösterirsonraki dizi öğesi

     Uzunluk yok, sonlandırma bayrağı yok, özel özellik yok

## Dizeleri Tanımlama

 Bir dizi, bir karakter dizisi olarak uygulanır

     Kolaylık sağlamak için, genellikle tırnak işaretleri içine alınır
    
     Genellikle boş sonlandırılır

     Karakterler bayttır

     0Dh (CR) ve 0Ah (LF) hex karakterleri kullanışlıdır

 Örnekler:

        str1 BYTE     "Adınızı girin:", 0
        str2 BYTE     'HATASI!', 0Dh, 0Ah, 'Durma programı', 0Dh, 0Ah, 0
        str3 BYTE     'A', 'E', 'I', 'O', 'U'       
        newLine BYTE   0Dh, 0Ah, 0       
        greet   BYTE  "Bir dize"       
                BYTE  "iki bölüm.", 0      
        menu    BYTE  "1. Yeni bir hesap oluştur", 0dh, 0ah,
                            "2. Mevcut bir hesabı açın", 0dh, 0ah,
                            "3. Çıkış", 0ah, 0ah,
                            "Seçim>", 0

## DUP Operatörü

 Veriler için alan ayırmak için DUP'ı kullanın

 Sözdizimi: DUP'yi tekrarlar (bağımsız değişken)

 Tekrarlar ve argüman sabitler veya sabit ifadeler olmalıdır

    var1 BYTE 20 DUP(0)         ; 20 bayt, hepsi sıfıra eşit       
    var2 BYTE 20 DUP(?)         ; 20 bayt, başlatılmamış  
    var3 BYTE 4 DUP("STACK")    ; 20 bayt: "STACKSTACKSTACKSTACK"    
    var4 BYTE 10,3 DUP(0),20    ; 5 bayt

## Diğer Türleri Tanımlama

    val1   WORD   65535         ; en büyük işaretsiz değer
    val2   SWORD  –32768        ; en küçük işaretli değer
    word3  WORD   ?             ; başlatılmamış, imzalanmamış
    word4  DWORD   "ABCD"       ; dört karakter
    myListWORD   1,2,3,4,5      ; kelime dizisi
    array  WORD   5 DUP(?)      ; başlatılmamış dizi
    val5   DWORD  0FFFF0000h    ; imzasız
    val6   SDWORD –2147483648   ; imzalı
    dwd7   SDWORD –2,–1,0,1,2   ; işaretli dizi
    qwd8   QWORD  1234567812345678h 
    rVal1 REAL4  -2.1
    rVal2 REAL8  3.2E-260

## Küçük Endian Düzeni

 Bir bayttan daha büyük tüm veri türleri, kendi baytlarınıTers sipariş. En az önemli bayt ilk anda gerçekleşir(en düşük) hafıza adresi.

 Örnek: 

                val1DWORD 12345678h


<img class="card-img-top" src="{{site.url}}/assets\img\posts\ComputerByStudy\Bilgisayar-Mimarisi\BOM_Process\capture8.png">


![](image/capture8.PNG)

## Örnek: Değişkenleri Kullanma

    TITLE Add and Subtract, Version 3            (AddSub3.asm) 
    ; Bu program 32 bit işaretsiz ekler ve çıkarır
    ; tamsayılar ve toplamı bir değişkende depolar.
    INCLUDE Irvine32.inc

    .data

    val1 DWORD 10000h 
    val2 DWORD 40000h 
    val3 DWORD 20000h 
    finalValDWORD ?

    .code

    main PROC
        mov eax,val1      ; 10000 saat ile başla
        add eax,val2      ; 40000h ekle
        sub eax,val3      ; 20000h çıkar
        movfinalVal,eax   ; sonucu sakla (30000h)
        call DumpRegs     ; kayıtları göster
        exit
    ana ENDP
    END ana

## Segment Kontrolü

 .code

     Aşağıdakilerin tümü kod segmentine gider

 .data

     Aşağıdakilerin tümü veri segmentine gider

 .data?

     başlatılmamış veri segmenti
    
     verileri depolamak için çalışma zamanında ayrılır
    
     depolanan .exe'de yer gerekmez (saklanacak değer olmadığı için)

 Eğer birbirine karıştırılırsa, montajcı tarafından ayrılırlar

## Başlatılmamış Verileri Bildirme

 .data kullanılsın mı? başlatılmamış bir veri kesimi bildirme yönergesi

     .DATA? yönerge, derlenmiş bir programın boyutunu azaltır.

            .data? 
            array1 DWORD 5000 DUP (?)
    
 Program için yüklenene kadar dizi1'e yer ayrılmamıştır.yürütme (.exe 20KB daha küçüktür)

            .data
            array2 DWORD5000 DUP (?)

 dizi2, boş olmasına rağmen, dizini depolamak için .exe'de 20KB'ye sahiptir.var olmayan değerler


## Anahat

 Programları Birleştirme, Bağlama ve Çalıştırma

 Assembly Dilinin Temel Öğeleri

 Örnek: Tamsayı Toplama ve Çıkarma

 Verileri Tanımlama

 Sembolik Sabitler

 Gerçek Adres Modu Programlama

## Tamsayı Sembolik Sabitler
isim = ifade

     ifade 32 bitlik bir tam sayıdır (ifade veya sabit)

     yeniden tanımlanabilir (ancak bunu yapmak için iyi bir biçim değil!)
    
     isim sembolik sabit olarak adlandırılır
    
     Direktifler: Çalışma zamanı etkisi yoktur, .exe'nin parçası değildir

 sembolleri kullanmak için iyi programlama stili

                COUNT = 500
                …
                mov balta, COUNT

## EQU Direktifi

 Bir tamsayı veya metin ifadesi olarak bir sembol tanımlayın

 = yönerge sadece izin verilen tam sayılar

 Yeniden **tanımlanamaz**

 Örnek:

    PI EQU<3.1416> 
    pressKeyEQU<"Press any key to continue...",0>
    .data
    prompt BYTE pressKey

## TEXTEQU Direktifi

 Bir metin sembolünü tam sayı veya metin ifadesi olarak tanımlayın

 Bir metin makrosu çağırdı

 Yeniden tanımlanabilir

 % bir tamsayıyı metne dönüştürür

    ;macros 
    msgTEXTEQU <"Do you wish to continue (Y/N)?"> 
    rowSize= 5
    count TEXTEQU %(rowSize* 2)       ; değerlendir ve metin olarak sakla 
    setupALTEXTEQU <moval,count>      ; mov için makro 
    .data 
    prompt1 BYTE msg 
    .code 
    setupAL                           ; "mov al, 10" u oluşturur

## Dizi Boyutu

 Mevcut konum sayacı: $

     listenin adresini çıkar

     fark bayt sayısıdır

 Örnek:

            liste BYTE 10,20,30,40
            listSize = ($ - liste)

 Bayttan büyükse öğe boyutuna bölün (ör.WORD, DWORD için 4, QWORD için 8)

 Örnek:    

            DWORD 1,2,3,4 listesi
            listSize = ($ - liste) / 4

## Gerçek Adres Programlama

 Bilgisayarınızın 80'lerde yapılmış gibi görünmesini, hareket etmesini ve hissetmesini sağlayın

 16 bit MS-DOS Programları Oluşturun (Neden?)

 "Avantajlar"

     MS-DOS ve BIOS işlevlerinin çağrılmasını sağlar
    
     hafıza erişim kısıtlaması yok

 Dezavantajlar

     hem segmentlerin hem de ofsetlerin farkında olmalıdır

     Win32 işlevleri çağıramaz

Gereksinimler

     Irvine16.inc DAHİL

     DS'yi veri segmentine başlatın:

        movax,@data
        movds,ax

## Anahat

 Programları Birleştirme, Bağlama ve Çalıştırma

 Assembly Dilinin Temel Öğeleri

 Örnek: Tamsayı Toplama ve Çıkarma

 Verileri Tanımlama

 Sembolik Sabitler

 Gerçek Adres Modu Programlama


## Özet

 Tamsayı ifadesi, karakter sabiti

 yönerge - montajcı tarafından yorumlanır

 talimat - çalışma zamanında yürütülür

 kod, veri ve yığın segmentleri

 kaynak, liste, nesne, harita, çalıştırılabilir dosyalar

 Veri tanımlama direktifleri:

     BYTE, SBYTE, WORD, SWORD, DWORD, SDWORD, QWORD, REAL4, REAL8
     TBYTE, REAL10 - Belirsiz ve nadiren kullanılan talimatlar (eski)
     DUP operatörü, konum sayacı ($)

 Sembolik sabitler

     =, EQU ve TEXTEQU