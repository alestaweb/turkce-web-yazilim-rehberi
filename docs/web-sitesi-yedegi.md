# Web Sitesi Yedeği: Neyi, Ne Sıklıkla, Nereye?

Bir web sitesinin yedeği, ancak geri yüklenebildiği gün işe yarar. Çoğu site sahibi "barındırma firması yedek alıyordur" diye düşünür ve bunu ilk kez bir sorun yaşadığında sorar. O gün öğrenilen cevap genellikle can sıkıcıdır: yedek ya hiç yoktur, ya çok eskidir ya da sadece dosyaları kapsar, veritabanını değil.

Bu yazı küçük işletme sitesi, e-ticaret mağazası ya da haber sitesi işleten herkes için hazırlandı. Teknik bilgi gerektirmez; yedeğinizi kim alıyorsa ona soracağınız soruları ve kendi kontrol etmeniz gerekenleri anlatır.

## 1. Bir sitenin yedeği iki parçadan oluşur

Günümüzdeki sitelerin neredeyse tamamı iki ayrı yerde veri tutar:

- **Dosyalar:** Sitenin yazılımı, tema, yüklenen resimler, belgeler, ürün fotoğrafları.
- **Veritabanı:** Yazılar, haberler, ürünler, siparişler, üyeler, yorumlar, ayarlar.

Sık yapılan hata, yalnız dosyaları yedeklemektir. Dosya yedeği olan ama veritabanı yedeği olmayan bir site geri yüklendiğinde boş bir iskelet olarak açılır. Tersi de sorunludur: veritabanı yerindedir ama ürün fotoğrafları ve haber görselleri kaybolmuştur.

Yedeğinizi kim alıyorsa ilk sorunuz şu olmalı: "Hem dosyalar hem veritabanı yedekleniyor mu?"

## 2. Ne sıklıkla?

Doğru sıklık, kaybetmeyi göze alabileceğiniz süreye göre belirlenir. Kendinize şunu sorun: "Site şu an çökse, en fazla kaç saatlik işi yeniden yapmaya razıyım?"

- **Nadiren değişen tanıtım sitesi:** Haftalık yedek ve her değişiklikten sonra bir yedek çoğu zaman yeterlidir.
- **Düzenli içerik giren blog veya kurumsal site:** Günlük yedek.
- **Haber sitesi:** Günlük tam yedek; gün içinde çok haber giriliyorsa veritabanı için birkaç saatte bir ek yedek.
- **E-ticaret:** Sipariş ve ödeme kaydı her an oluşur. Veritabanı en az günlük, yoğun mağazalarda daha sık yedeklenmelidir. Bir günlük sipariş kaydını kaybetmek, kargo ve fatura tarafında ciddi karışıklık çıkarır.

Ayrıca yedek alınması gereken özel anlar vardır: yazılım güncellemesinden önce, tema veya eklenti değişikliğinden önce, toplu ürün ya da fiyat aktarımından önce, sunucu taşımadan önce. Bu anlarda alınan yedek, sorun çıktığında birkaç dakikada geri dönmenizi sağlar.

## 3. Ne kadar süre saklanmalı?

Yalnız "dünkü" yedeği tutmak yetmez. Bir sitenin içine zararlı kod yerleştirildiğinde bu genellikle günler, bazen haftalar sonra fark edilir. Elinizde sadece son birkaç günün yedeği varsa hepsi zaten bozulmuş olabilir.

Pratik bir saklama düzeni:

- Son 7 günün günlük yedeği,
- Son 4 haftanın haftalık yedeği,
- Son birkaç ayın aylık yedeği.

Bu düzen, hem dünkü hatayı hem de bir ay önce başlamış bir sorunu geri almanıza imkân verir.

## 4. Nereye? 3-2-1 kuralı

Yedekle ilgili en çok bilinen ve hâlâ en sağlam kural 3-2-1 kuralıdır:

- **3 kopya:** Canlı site ve iki ayrı yedek.
- **2 farklı ortam:** Örneğin sunucu diski ve bir bulut depolama alanı.
- **1 kopya başka bir yerde:** Siteyle aynı sunucuda, hatta aynı firmada olmayan bir konumda.

Yedeğin sitenin bulunduğu sunucuda durması tek başına yedek sayılmaz. Sunucu diski arızalanırsa, hesap askıya alınırsa ya da sunucuya saldırı olursa yedek de siteyle birlikte gider. Fidye yazılımı saldırılarında saldırganların ilk aradığı şeylerden biri de aynı sunucudaki yedeklerdir.

## 5. Yedek nerede açıkta kalmamalı?

Yedek dosyası sitenin bütün verisini içerir: üye bilgileri, sipariş adresleri, yönetici parolalarının özetleri. Bu yüzden yedeğin kendisi de korunması gereken bir varlıktır.

- Yedek dosyası sitenin herkese açık klasöründe durmamalıdır. "site-yedek.zip" gibi bir dosya tarayıcıdan indirilebiliyorsa, bütün veritabanınız herkese açık demektir. Arama motorları ve otomatik tarayıcılar bu tür dosya adlarını düzenli olarak dener.
- Bulut depolama alanının paylaşım ayarı "bağlantıya sahip herkes" olmamalıdır.
- Mümkünse yedek şifrelenmiş olarak saklanmalı, şifre yedekle aynı yerde tutulmamalıdır.
- Kişisel veri içeren yedeklerin saklama süresi de kişisel verilerin korunması yükümlülükleri açısından düşünülmelidir. Yıllarca saklanan eski yedekler, silinmiş olması gereken verileri barındırabilir.

## 6. Geri yükleme denenmemiş yedek, yedek değildir

En önemli madde budur. Yedek alındığını gösteren bir bildirim, yedeğin çalıştığını göstermez. Sık görülen sorunlar:

- Yedek dosyası alınmış ama içi boş ya da yarım kalmış.
- Veritabanı yedeği alınırken bir hata olmuş, kimse fark etmemiş.
- Yedek sistemi aylar önce durmuş, bildirim de gelmediği için kimsenin haberi olmamış.
- Yedek var ama geri yükleme için gereken parola, erişim ya da bilgi kimsede yok.

Yılda en az iki kez, tercihen üç ayda bir, yedeği ayrı bir ortama geri yükleyip sitenin açıldığını, son içeriklerin yerinde olduğunu, resimlerin göründüğünü kontrol edin. Bu işi teknik ekibinizden ya da hizmet aldığınız firmadan isteyebilirsiniz. Geri yüklemenin ne kadar sürdüğünü de not edin; gerçek bir arıza anında bu bilgi işinize yarar.

## 7. Barındırma firmasının yedeğine güvenmeli mi?

Barındırma firmalarının çoğu kendi altyapıları için yedek alır. Ancak bu yedeğin size ne kadar faydalı olduğunu sözleşme belirler. Sormanız gerekenler:

- Yedek hangi sıklıkla alınıyor, kaç gün saklanıyor?
- Veritabanı dahil mi?
- Geri yükleme talebinde ücret alınıyor mu, ne kadar sürede yapılıyor?
- Tek bir dosyayı ya da tek bir günün veritabanını geri almak mümkün mü?
- Hesabın askıya alınması ya da sözleşmenin bitmesi durumunda yedeklere ne oluyor?

Firmanın yedeği iyi bir ek güvencedir, ama tek güvenceniz olmamalıdır. Kendi kontrolünüzde, başka bir konumda en az bir kopya bulunsun.

## 8. Yedekle birlikte saklanması gerekenler

Bir siteyi sıfırdan ayağa kaldırmak için yalnız dosya ve veritabanı yetmez. Şu bilgileri de güvenli bir yerde tutun:

- Alan adının kayıtlı olduğu firma ve hesap bilgisi,
- Alan adının yönlendirme (DNS) kayıtlarının bir listesi,
- E-posta hesaplarının listesi ve ayarları,
- Sitenin kullandığı dış hizmetler: ödeme, kargo, e-fatura, SMS, harita, istatistik hesapları,
- SSL sertifikasının nasıl yenilendiği.

Bu liste bir parola yöneticisinde ya da şifreli bir belgede durmalıdır. Arıza anında "o hesabın şifresi kimdeydi?" sorusu, yedeği geri yüklemekten daha uzun sürebilir.

## 9. Bir sorun yaşadığınızda ilk adımlar

Site hacklendiyse ya da veriler bozulduysa:

1. Yeni yedek almayı hemen durdurun ya da mevcut sağlam yedekleri ayrı bir yere kopyalayın; bozuk hâlin sağlam yedeklerin üzerine yazılmasını önleyin.
2. Sorunun ne zaman başladığını tahmin edin ve o tarihten önceki bir yedeği seçin.
3. Geri yüklemeden önce mevcut bozuk hâlin de bir kopyasını alın; sonradan neyin değiştiğini incelemek gerekebilir.
4. Geri yükledikten sonra yönetici parolalarını değiştirin. Saldırı bir açık üzerinden yapıldıysa, açık kapatılmadan geri yüklenen site aynı şekilde yeniden ele geçirilebilir.
5. Aradaki sürede gelen sipariş, üyelik veya yorum gibi kayıtları ayrıca kurtarmanız gerekip gerekmediğini değerlendirin.

## Kontrol listesi

- [ ] Hem dosyalar hem veritabanı yedekleniyor.
- [ ] Yedek sıklığı, kaybetmeyi göze alabileceğim süreye uygun.
- [ ] Güncelleme, taşıma ve toplu değişiklik öncesi ayrıca yedek alınıyor.
- [ ] Günlük, haftalık ve aylık yedekler ayrı ayrı saklanıyor.
- [ ] En az bir kopya siteyle aynı sunucuda ve aynı firmada değil.
- [ ] Yedek dosyaları herkese açık klasörde değil, tarayıcıdan indirilemiyor.
- [ ] Bulut yedeğin paylaşım ayarı kapalı, mümkünse şifreli.
- [ ] Son üç ay içinde bir geri yükleme denemesi yapıldı ve site açıldı.
- [ ] Yedek sistemi durursa haberim olacak bir bildirim var.
- [ ] Alan adı, DNS, e-posta ve dış hizmet bilgileri ayrıca güvenli bir yerde.
- [ ] Barındırma firmasının yedek koşullarını yazılı olarak biliyorum.

## Faydalı kaynaklar

- Ulusal Siber Olaylara Müdahale Merkezi (USOM): https://www.usom.gov.tr
- Kişisel Verileri Koruma Kurumu: https://www.kvkk.gov.tr
- Siber güvenlik farkındalık içerikleri için Bilgi Teknolojileri ve İletişim Kurumu: https://www.btk.gov.tr

---

Bu yazı genel bilgilendirme amaçlıdır. Hazırlayan: Alesta WEB — İzmir
