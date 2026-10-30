# Web Sitesini Yeni Sunucuya Taşırken Kontrol Listesi: Unutulan Tek Satır 19 Gün Fark Edilmeyebilir

Bir siteyi yeni sunucuya ya da yeni barındırma firmasına taşımak çoğu zaman sorunsuz görünür. Ana sayfa açılır, yönetim paneline girilir, yeni içerik eklenir. Taşımayı yapan kişi "her şey çalışıyor" der ve iş kapanır.

Oysa bir sitenin önemli bir kısmı ekranda görünmez. Gece çalışan temizlik işleri, saat başı toplanan istatistikler, ileri tarihli yayınlar, otomatik e-postalar, site haritasının yenilenmesi, döviz ve hava durumu gibi küçük veri kutularının güncellenmesi. Bunların hepsi "zamanlanmış görev" denen bir düzenle çalışır ve taşımada en kolay unutulan parça budur.

Bu yazı site sahipleri için hazırlandı. Teknik ayrıntıya girmeden, taşımayı yapan kişiye soracağınız soruları ve taşıma sonrasında kendi gözünüzle kontrol edebileceklerinizi anlatır.

## 1. Gerçek bir örnek: her şey yeşil, arka plan durmuş

Bir yerel haber sitesi yeni sunucuya taşındı. Site eskisinden çok daha hızlı açılıyordu, editörler haber girebiliyordu, sayfalar sorunsuzdu. On dokuz gün sonra yapılan rutin bir kontrolde, normalde birkaç bin satır tutan bir kayıt tablosunun yaklaşık 600 bin satıra çıktığı görüldü.

Neden basitti: yeni sunucuda, uygulamanın bütün arka plan işlerini çalıştıran tek bir zamanlanmış görev satırı hiç eklenmemişti. Temizlik işi çalışmadığı için tablo büyümüş, istatistik özetleri üretilmemişti. Siteye her gün bakan kimse bunu görmedi, çünkü sayfalar bu işlere o gün ihtiyaç duymuyordu.

Şanslı tarafı, o sitede ileri tarihe planlanmış haber yoktu. Planlı yayın kullanan bir sitede sabah 06.00'ya kurulan haberler taslak olarak kalacak ve fark edildiğinde sabah haberleri kaçmış olacaktı.

## 2. Zamanlanmış görev nedir, neden taşınırken kaybolur?

Sunucu, belirli aralıklarla (her dakika, her saat, her gece) belirli bir işi çalıştırmak için ayrı bir listede kayıt tutar. Sitenin dosyaları ve veritabanı bir yerdedir, bu liste ise sunucunun kendi ayarlarındadır.

Taşıma genellikle "dosyaları kopyala, veritabanını aktar, alan adını yönlendir" diye planlanır. Zamanlanmış görev listesi bu üçünün hiçbirine dahil değildir. Elle yeniden kurulması gerekir. Unutulursa hiçbir hata mesajı çıkmaz; görev sadece çalışmaz.

## 3. Taşımadan önce sorulacak sorular

Taşımayı kim yapıyorsa, işe başlamadan önce şunları sorun ve cevaplarını yazılı alın:

- Sitenin zamanlanmış görevleri neler, kaç tane, hangi sıklıkta çalışıyor?
- Bu görevlerin listesi taşımadan önce bir yere kaydedilecek mi?
- Sitenin dışarıya bağlandığı servisler hangileri (ödeme, kargo, e-fatura, SMS, haber kaynağı, döviz verisi)? Bunların anahtarları ve izinleri yeni sunucuda da geçerli olacak mı?
- E-posta gönderimi yeni sunucudan da çalışacak mı? İletişim formu, sipariş bildirimi, şifre sıfırlama e-postası denenecek mi?
- Taşıma günü kaç dakikalık kesinti bekleniyor, eski sunucu kaç gün açık tutulacak?
- Taşımadan hemen önce tam yedek alınacak mı ve bu yedek nerede duracak?

## 4. Taşıma günü kontrol listesi

- **Tam yedek:** Taşımadan hemen önce hem dosyalar hem veritabanı.
- **Yazma dondurma:** Veritabanı aktarılırken yeni sipariş ya da içerik girilmemesi için kısa bir bakım penceresi.
- **Alan adı ve sertifika:** Yeni sunucuda güvenli bağlantı sertifikası kurulu mu, hem "www"li hem "www"siz adres doğru yere gidiyor mu?
- **Zamanlanmış görevler:** Eski sunucudaki listenin aynısı yeni sunucuda kurulu mu? Fazlası ya da eksiği var mı?
- **Bekleyen işler:** Görevler yeniden açılmadan önce kuyrukta bekleyen işler var mı? Uzun süre kapalı kalmış bir görev, açıldığı ilk dakikada biriken her şeyi birden yapabilir: eski taslakları yayımlamak ya da aylar önceki hatırlatma e-postalarını müşterilere göndermek gibi.
- **Dosya izinleri:** Resim ve belge yükleme yeni sunucuda çalışıyor mu?

## 5. Taşımadan sonra kendiniz kontrol edin

Teknik bilgi gerektirmeyen ama çok şey anlatan kontroller:

- Bir iç sayfayı, bir ürün ya da haber detayını ve bir resmi açın. Sadece ana sayfaya bakmak yetmez.
- İletişim formundan kendinize bir mesaj gönderin.
- Planlı yayın kullanıyorsanız 10 dakika sonrasına bir deneme içeriği planlayın ve zamanında yayına girdiğini görün.
- E-ticaret sitesinde deneme siparişi verin, sipariş e-postasının geldiğini görün.
- Yönetim panelinde istatistik ya da rapor ekranını açın; ertesi gün dünkü rakamların oluştuğunu kontrol edin.
- Döviz, hava durumu, namaz vakti gibi kutular varsa bir gün sonra güncellendiklerine bakın.
- Site haritasının tarihine bakın; yeni eklenen içerik birkaç saat içinde orada görünmeli.

## 6. Bir hafta sonra tekrar bakın

Arka plan işlerinin aksaması ilk gün değil, günler sonra belirti verir. Taşımadan bir hafta sonra şunları isteyin:

- Zamanlanmış görevlerin son çalışma zamanlarının listesi. Her biri beklenen sıklıkta çalışmış olmalı.
- Sunucu disk kullanımı. Taşımadan sonra beklenmedik hızda artıyorsa bir temizlik işi çalışmıyor olabilir.
- Hata kayıtlarında taşımadan sonra başlayan yeni hata türleri.

## 7. Sürekli izleme: "site açık mı" sorusu yetmez

Çoğu izleme servisi yalnız sitenin açılıp açılmadığına bakar. Bu, arka plan işlerinin durduğunu hiçbir zaman göstermez. Barındırma ya da bakım hizmeti aldığınız kişiye şunu sorun: "Zamanlanmış görevler belirli bir süre çalışmazsa kim, nasıl haberdar oluyor?"

İyi bir cevap, her görevin son çalışma zamanının kaydedildiği ve bu zaman belli bir sınırı geçince uyarı gönderildiğidir. Bu basit kontrol, yukarıdaki örnekte 19 günlük sessizliği ilk gün yakalardı.

## 8. Kısa kontrol listesi

1. Taşımadan önce zamanlanmış görevlerin listesi yazılı olarak alındı.
2. Taşımadan hemen önce dosya ve veritabanı yedeği alındı, ayrı bir yerde saklanıyor.
3. Dış servis bağlantıları (ödeme, kargo, e-fatura, SMS) yeni sunucuda denendi.
4. Yeni sunucuda görev listesi eskisiyle karşılaştırıldı, fark yok.
5. Görevler açılmadan önce bekleyen işler gözden geçirildi.
6. İç sayfa, resim, form, e-posta ve planlı yayın elle denendi.
7. Ertesi gün istatistik, site haritası ve veri kutularının güncellendiği görüldü.
8. Bir hafta sonra görevlerin son çalışma zamanları ve disk kullanımı kontrol edildi.
9. Görevler durursa uyarı gönderen bir izleme kuruldu.
10. Eski sunucu, her şey doğrulanana kadar kapatılmadı.

---

Bu rehber [Alesta WEB](https://alestaweb.com) tarafından hazırlanmıştır. Aynı olayın teknik ayrıntılarını İngilizce olarak [şu yazıda](https://dev.to/mahmut_gndzalp_c736ac4b/the-site-moved-the-scheduler-didnt-19-days-of-silent-background-jobs-after-a-migration-ja8) anlattık.
