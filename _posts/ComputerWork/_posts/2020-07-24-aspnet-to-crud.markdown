---
title: Asp.net Mvc Basic Crud İşlemleri
layout: post
date: '2020-07-24 19:51:02 +0700'
tags:
- foo
- bar
image: assets/bower_components/icono/sass/icons/cup.scss
author: Avni Kaşıkçı
New field 2: May 23, 2020 12:52 PM
thumbnail: "/assets/img/posts/hello.jpg"
summary: Content
permalink: "/blog/categories/turkish/aspnetcrud"
categories: [AspNet,ComputerWork]

---

<p>Herkese merhabalar, bu yazımızdada güçlü yapılar kurarken bile ihtiyac duyduğum test amaçlı crud işlemlerine deyiniceğim.Crud işlemleri veritabanındaki değerleri ekleme güncelleme,silme ve okuma işlemleridir.İsmide buradan geliyor zaten "Create,Read,Uptade,Delete" bir çok profosyonel projeyi ele alırken direk view değeri göndermek yerine bir testUI'si oluşturup verilerin kontrolünü bu şekilde yapıyorum ve herkesede bunu öneriyorum.</p>

<p>Şimdi internette bir çok kaynakta Crudların çok farklı veriyonları var ben bu yazımda en yalın haliyle ele alaçağım.</p>
<p>Şimdi Bir mvc projesi oluşturalım,Oluşturduğumuz Projeye Bir controller ekliyelim.</p>

<figure class="wp-block-image size-large"><img src="https://canisikilanmuhendis.files.wordpress.com/2020/07/image.png?w=1024" alt="" class="wp-image-139"/></figure>

<p>Daha sonra oluştruduğumuz controle bir ActionResult Oluşuturalım.</p>

<figure class="wp-block-image size-large"><img src="https://canisikilanmuhendis.files.wordpress.com/2020/07/image-1.png?w=499" alt="" class="wp-image-140"/></figure>


<p>İlk işlemimiz Create olsun,buradaki get ve post kavramlarını geniş bir konu olduğu için başka yazımda ele almak istiyorum fakat kısaca bir bilgi vermem gerekirse,meslek hayatımda sürekli kullandığım bir ezberleme şekli olan Get getirir Post götürür tekerlemesini aklınıza yazmak istiyorum :) Resmi Dikkatli incersek bir service katmanımız var buradaki işlemleri controller kısmında erişmek için gerekli bağlantılar kurulmuş örnekteki categoryService.SaveCategory servis bağlantısını ilk seviyede direk veritabanına bağlanacak bir method olarakda yazılabilirdi.Bunun için entityFramework kullanarak bir örnek vermem gerekirse,</p>

<p>Direk Database bağlantısı yapalım ve entity framework yapısı ile direk veritabanında işlemlerimizi yapalım.</p>


<p><code>Db_Entitites db= new Db_Entitites(); //Veri Tabanına direk bağlantı<br>//Daha sorna ilgili eklenecek nesneyi ekleyip kaydetmemiz kalıyor.<br>db.Category.Add(Category);<br>db.SaveChanges();</code></p>


<p>Gördüğünüz üzere 3 satırlık bir kod bloğu oldu bunu tek satıra indirmek ve her linq sorgusu için farklı satır oluşturmak yerine biz bunu service kısmında yaptık bu konu çok derin ve uzun konu olduğu için başka yazımda bahsetmek istiyorum.Şimdi görselimize dönelim burada bir Create action ' umuz var.Bu yapı bizim view kısmına giderken cağrılcak olan yapıdır.Post kısmında parametreleri Category'den türemiş yapı gelicek ve actiondan gelen Nesne ile veri tabanımıza kayıt işlemini gerçekleştirmiş okucaz.Gelelim view kısmına buradada yazı için oluşturduğum tertemiz bir view yapısı var.</p>


<figure class="wp-block-image size-large"><img src="https://canisikilanmuhendis.files.wordpress.com/2020/07/image-2.png?w=436" alt="" class="wp-image-141"/></figure>


<p>Tabi tertemiz dedim ama bir çok veri ile çalışan çeşitli güvenlik zafiyetlerini istemeyenler için berbat bir kod bloğu tabi biz ilgili projemizin test aşamasında olduğumuz için böyle bir yapı yeterli olcaktır.Viewde ki html kodlarında form method post demişiz yani girilen veriyi control kısmına post et bunun içinde çok derin algoritmalar var.Biz sornaki yazımız için benim sürekli kullandığım ajax methodlarına deyinecez.Ajax'danda kısaca bahsetmek gerekirse buradaki değerleri alıp ilgili yere post ediyor aynı işlem gerçekleşiyor fakat crud işlemlerindeki create ve uptade aynı zamanda read kısmını tek parça view halinde kod israfından kaçınarak yapıyor.Gayet kullanışlı bunu da tavsiye ederim.Araştırın kullanın hocam :)</p>


<p>Gelelim sumbit kısmına html bize sağladığı kolaylıkları kullanmıyalım mı? Buradaki sumbit arka tarafındaki css kodları hazır olarak html kısmında barındırıyor yani bir nevi her dilin özelliği olan toplama fonksiyonu olan sum methodu gibi düşünelebilir yani herhangi bir ajax methodu olmadan sumbit butonu ile veriyi Controller kısmına gönderdik.View'in Post methodu olduğu yere gönderdik.Burada category nesnemizin name kısmına ilgili veriyi kaydettik.</p>


<p>Şimdi gelelim neden bu kadar basit bir yapı kurduğumuza ve yazının başındada söylediğim profosyenel işlerde bu yapıyı nerede kullanacağımıza Profosyonel yapılarda veriyi kaydetme aşamasında hatta sorgu aşamasında bile tonlarca methodtan geçerek kaydetme işlemi gerçekleştiriyoruz.Bu devoleperı cok yoran aynı zamanda asıl yapının oluşmasındaki kavram karşıklığını beraberinde getiriyor.Tabi çoğu profosyonel bir testUI oluşturarak bu yaptığımız yapıyı console kısmında yapıyor ama benim herhangi bir sayfada oluşacak action için controller kısmında kanlı canlı view oluşturarak yapmaktan yana bu yapıyı bile çoğu projenin temel aşamasında veriyi yönetmek adına yer vermişimdir.</p>


<p>Sağlıcakla kalın dostlar umarım bildiklerimi aktarabilmişimdir.Sizlerde yazımdan keyif almıssınızdır.Yazıda bahsettiğim konuları takip etmeyi araştırmayı unutmayın.Hepinize sevgiler dotnet'e saygılarımı sunuyorum :)</p>
