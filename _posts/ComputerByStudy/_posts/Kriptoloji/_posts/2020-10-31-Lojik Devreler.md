---
title: Kriptolojiye Giriş
created: '2020-10-318T16:33:42.376Z'
modified: '2020-10-31T16:39:37.142Z'
layout: postByComputer
author: Avni Kaşıkçı
date: '2020-10-31 03:02:32'
thumbnail: "/assets/img/posts/hello.jpg"
summary: Kriptoloji
keywords: Kriptoloji
permalink: "/ComputerEngineer/Kriptoloji"
category: [computer, Kriptoloji]
categories: [computer, Kriptoloji]
---

# Rastsal Sayı Üreteçleri
**Rastsal Sayılar ve Temel Özellikleri**

* Kaynağ,sonucunu önceden belirlenimci yönemlerle tahmin edemediğimiz olaylara dayanan sayılardır.Kriptografide şifreleme anahtarları algoritma ilklendirme değerleri kimlik doğrulama gibi alanlarda kullanılır.
* Rastsal Sayıların temel özellikleri;
  - Yüksek Rassallık 
  - Düzgün Dağılım her sayının ortaya çıkma olasığının eşit olması
  - Bağımsızık ardışıl üretilen sayılar arasında ilinti olmaması
  - Aperiyodiklik yada çok uzun periyot kullanım sürecinde sayıların tekrar etmemesi 
  - Kolay ve Hızlı Üretebilirlik
  
**Entropi** ,bilgi kuramında belirsizliğin ölçütüdür, rastsallığı yüksek olayların entropileride yüksek olur.
**Düzgün Dağılım** rastsal sayıların kaynak küme içinde homejen dağışıma sahip olması gerektirir, böylece kayntaktan alınan her sayı örneğinin ortaya çıkma olasılığı eşit olur. N adet sayı olan bir kümede rastsal şeçilecek her sayı 1/N olasıklara gelmelidir.

**Aperiyodiklik** sabit aralıklarla tekrarlanmayan rastsal olayları tanımlar. Güvenlik için rastsal sayı dizilerinin kendilerini tekrar etmemesi gereklidir.İdealde periyodun sonsuz,şartlar elvermiyor ise olabildiğince uzun olması gereklidir.


**Kriptografide Rastsal Sayıların Kullanım Alanları**
Genellikle kriptografide **şifreleme anahtarları** iki uç nokta arası simetrik / asimetrik şifreleme algoritmalarında anahtar olarak kullanılıyor.**Tek kullanımlık Şifreler** tek defaul üretilen (OTP) ve kullanılan sayılar. **Zaman Damgası** hesaplama işlemlerinde verileri tekil olarak etiketlemek için kullanılırlar. **Sözde Rs Üreteçlerinin ilklendirilmesi** gibi askeri alanlarda araç kaza şaşe numaraları gibi birçok alanlarda kullanılırlar.


**Rastal Sayı Üreteçleri ve Sınıflandırılması**

Rastsal sayıları üreten aygıt ve algoritmalara rastsal sayı üretici (RSÜ) denir.


**Sözde Rastsal Sayı Üreteçleri** 

Kısa kullanımda avantajı güvenlik duvarları oluşturabilecek yapılardan üreteç çıkışının ilk değere en az şekilde bağımlı olduğu algoritmaları vardır.bunlar ktiptografik güvenli sözde rsü lerdir.Bir saldırganın ilk değeri bilmesinin çıkışı tahmin etmek için avantaj sağlamaması beklenir.Periyodların çok uzun olması gereklidir.İstatiksel olarak çok kapsamlı şekilde test edilmeleri gerekir.
Bu sayılara örnek olarak;
  - Kesintisisz şifreleme algoritmaları 
  - Sayaç modda yada geri beslemeli modda blok şifreleme algoritmaları 
  - Çeşitli sayı kombinasyonları
  - Tek yönlü fonksiyon art işlemesiyle genel SRSÜ kombinasyonları
  - Güvenliği matematiksel olarak ispatlanmış problemlere dayanan SRSÜ'ler.

Sözde RSÜ ler eş daığımlı sayılar üretebilirler ancak sonlu bir periyoda sahiptirler üretilen sayılar arasında belirlenimci birilişki ve ilk değer bağımlılığı vardır.

Teorik olarak bütün mat. sistemler bir şekilde kırılabilir.Sistemde belirleyici olmayan bir fail bulmamız gerekir.bu sebeple gerçek sayı üreteçleri cok büyük önem arz ediyor.(Sistem Güvenliği Açısından)


**Rastsal Sayıların İstatilsel Testleri**

Her Biri farklı rastsallık özelliklerini sınayan çeşitli testlerden oluşur.Testler uzun bir bit disinin alt dizilerinde desen ve tekrarları kontrol ederler.Toplanan veri sabit uzunluklu bit bloklarına bölünür ve bu bloklar test edilir. Her test için bunların testleri geçme oranları hesaplanır ve bu orana göre gü ven sevitesi artılır yada azaltılır eğer testlerden geçen bit dizilerinin oranı düşük ise bu durum üreticin sorunlu olduğuna işaret eder.


- istatiksel testler, bit dizelerindeki desenleri ve tekrarları yakalarlar.
- bir bit dizisinin rastsal olmadığını tam olarak anlamak mümkün değil fakat rastsal olduğunu tesbit edebiliriz. bu sebeple güvenlik sektöründeki bu rastsallık büyük kolaylık sağlamaktadır.

