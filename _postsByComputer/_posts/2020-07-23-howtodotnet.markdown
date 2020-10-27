---
layout: post                         
title: "Asp.Net Sql Error"                  
date: 2020-04-20 19:51:02 +0700       
categories: [AspNet,cyber]          
tags: [foo, bar]                      
image: Broadcast_Mail.png            
---


# I post blog pages and Sql Server Error-Fıx "Database Diagram Error 15517"...

<p><span class="uppercase">Bu blog serisini bu konuyla başlatmış bulunuyorum arkadaşlar :) olası sql hataları gerçekten Türkçe kaynak bulmakta zorluk çektiğim konularından başında geliyor.Bu yazı serimde github projelerini import ederken aldığımız sql hataları üzerinde konuşacağız. Gelelim olası sorunların başında gelen ve konu alt başlığımız olan ""Database Diagram Error 15517 – Cannot Execute as the Database Principal Because the Principal ‘dbo’ Does Not Exist", hatanın çok mükemmel İngilizce'miz ile çevirmeye çalışır isek :) veri tabanımızın sorumlusu olarak kullanıcımız görmüyor yani özel bir izin alarak veritabanının oluşturan kişinin yetkisine alabilme gibi yorumlayabiliriz. Bu hatanın kaynağı genelde github projelerini import ederken asp.net projelerinde "web.config" alanında bulunan "ConnectionString" bölümünde başka servere olan bağlantılar bulunduran kısmı özelleştirmemiş olmamız yada başka bir sunucuya bağlanıp <a href="https://canisikilanmuhendis.wordpress.com/blog-2/">veritabanını "import" yada "export" etme</a>mizden kaynaklıdır. Hatanın olasılıkları tabi ki artırılabilir fakat bu yazımız için yeterli olasılıkları verdiğimi düşünmüyorum. Kısacası veri tabanı sahiplendirme rollerinde bir sorun var. Bu hatayı ilk aldığımda yaptığım ilk adım bağlı olduğunu sql sunucunda ilgili veri tabanına kimler bağlandığını aramak oldu bunun için ilgili <code>veri tabanım "ExampData"...</code></span></p>
<p>USE ExampData<br/>
GO<br/>
SELECT SUSER_SNAME(sid), * from sys.database_principals <br/><p>
  
  <figure class="wp-block-image size-large is-resized"><img src="https://canisikilanmuhendis.files.wordpress.com/2020/06/sql-diagramerror.png?w=1024" alt="" class="wp-image-61" width="895" height="156"/></figure>
  <p><span class="uppercase">İlgili kod sonucu 14 satır değer döndü.Eğer burada ilk sütünda yer alan değerlerin hepsi NULL dönüyor ise iki çözüm yolumuz var.İlki Sağ tıklayıp Properties-Files-Owner ilgili sql serverini giriniz yani bağlandığınız bilgisayardaki "bilgisayarAdi" olan sunucu </span></p>
  <p>İkinci olarak sql new query açarak yapabiliriz siniz.</p>
  
  
  <p>USE ExampData
GO
ALTER AUTHORIZATION ON DATABASE::ExampData TO [sa]
GO<p>
<p><span class="uppercase">Bu kodlardan sonra ilgili sorunun çözülebileceğini umuyorum şayet çözülmez ise farklı yetkilendirme methodlarından veri tabanına sağ tıklayıp users seçeneğinden yetkimizin olup olmadığını kontrol etmeliyiz bu konuya da bir sonraki yazımda yer vermek istiyorum.</span></p>

<p>Umarım faydalı bir yazı olmuştur.Sevgilerle...</p>

