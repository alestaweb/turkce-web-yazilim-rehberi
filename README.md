# Alesta WEB

Alesta WEB, 2005'ten bu yana Şanlıurfa'da faaliyet gösteren bir yazılım firmasıdır. Haber yönetim sistemleri, e-ticaret altyapısı ve özel iş yazılımları üretir. 200'ü aşkın haber portalı ile 500'ün üzerinde aktif müşteriye hizmet verir.

- Web: https://alestaweb.com
- E-posta: admin@alestaweb.com
- Telefon: +90 505 532 36 38
- Adres: İpekyol Mahallesi, Haliliye / Şanlıurfa

---

## İçindekiler

- [Alesta Haber Sistemi](#alesta-haber-sistemi)
- [Alesta E-Ticaret](#alesta-e-ticaret)
- [QR Menü Yazılımı](#qr-menü-yazılımı)
- [Rent A Car Yazılımı](#rent-a-car-yazılımı)
- [Uyumluluk](#uyumluluk)
- [Demo Erişimi](#demo-erişimi)
- [İletişim](#i̇letişim)

---

## Alesta Haber Sistemi

Dijital yayıncılık için geliştirilmiş içerik yönetim sistemidir. Haber siteleri, magazin portalları ve kurumsal yayın platformları için kullanılır.

### Yayın Yönetimi

- Hızlı yayın akışı, taslak ve zamanlanmış gönderim
- Kategori, alt kategori ve etiket hiyerarşisi
- Manşet, sürmanşet ve sıralama yönetimi
- Yorum sistemi ve moderasyon araçları
- Bülten aboneliği ve toplu e-posta
- Çok yazarlı çalışma, yazar profilleri
- Galeri, video, ses dosyası modülleri
- Anket, oylama, son dakika bandı
- Manuel ve otomatik sosyal medya paylaşımı

### Yapay Zeka Entegrasyonu

Altı yapay zeka sağlayıcısı yerleşik olarak gelir:

- OpenAI (GPT)
- Anthropic (Claude)
- Google (Gemini)
- DeepSeek
- Groq
- Mistral

Panel üzerinden otomatik özet çıkarma, başlık önerisi, SEO meta üretimi, içerik çevirisi, görsel açıklama metni ve içerik denetimi tek arayüzde yapılır. Sağlayıcı seçimi yöneticide kalır; API anahtarları yerel saklanır.

### Haber Ajansı Entegrasyonları

Yerleşik desteklenen ajanslar:

- [Anadolu Ajansı (AA)](https://www.aa.com.tr/)
- [Demirören Haber Ajansı (DHA)](https://www.dha.com.tr/)
- [İhlas Haber Ajansı (İHA)](https://www.iha.com.tr/)
- [ANKA Haber Ajansı](https://ankahaber.net/)
- THA, Hibya, İGFA, BHA

Ajans akışı otomatik içe aktarılır; mahreç yönetimi panelden yapılır.

### SEO ve Performans

- AMP HTML çıktısı
- Schema.org structured data (NewsArticle, BreadcrumbList, Organization)
- Open Graph ve Twitter Card meta etiketleri
- Sitemap (haber, görsel, video ayrı)
- Google News uyumlu yapı
- LiteSpeed, Apache, Nginx üzerinde çalışır
- WebP dönüşümü ve görsel boyutlandırma
- Çoklu önbellek katmanları

---

## Alesta E-Ticaret

B2B ve B2C senaryolarına uygun, yerel ödeme ve lojistik entegrasyonlarıyla gelen e-ticaret altyapısı.

### Mağaza Yönetimi

- Ürün ve varyant yönetimi (renk, beden, miktar)
- Stok ve depo takibi
- Kupon, kampanya, indirim motoru
- Çoklu para birimi ve dil
- Üye seviyeleri ve bayi fiyatlandırması
- Sepet, sipariş, iade akışı
- Mobil uygulama için REST API
- Yetki katmanlı admin paneli
- Çok mağazalı yapı

### Ödeme Entegrasyonları

Doğrudan banka sanal POS bağlantıları:

- [Garanti BBVA](https://www.garantibbva.com.tr/)
- [İş Bankası](https://www.isbank.com.tr/)
- [Akbank](https://www.akbank.com/)
- [Ziraat Bankası](https://www.ziraatbank.com.tr/)
- [Halkbank](https://www.halkbank.com.tr/)
- [VakıfBank](https://www.vakifbank.com.tr/)
- [Yapı Kredi](https://www.yapikredi.com.tr/)
- [QNB Finansbank](https://www.qnb.com.tr/)
- [ING](https://www.ing.com.tr/)
- [TEB](https://www.teb.com.tr/)

Ödeme aggregator entegrasyonları:

- [iyzico](https://www.iyzico.com/)
- [PayTR](https://www.paytr.com/)
- [Param](https://param.com.tr/)
- [Moka](https://moka.com/)
- [Paycell](https://paycell.com.tr/)
- [Paynet](https://www.paynet.com.tr/)
- [Sipay](https://sipay.com.tr/)

3D Secure tüm seçeneklerde desteklenir. Taksitli işlem kuralları banka bazında ayarlanır.

### Kargo Entegrasyonları

API üzerinden bağlı kargo firmaları:

- [Yurtiçi Kargo](https://www.yurticikargo.com/)
- [Aras Kargo](https://www.araskargo.com.tr/)
- [MNG Kargo](https://www.mngkargo.com.tr/)
- [PTT Kargo](https://www.ptt.gov.tr/)
- [Sürat Kargo](https://www.suratkargo.com.tr/)
- [UPS](https://www.ups.com/tr/)
- [DHL](https://www.dhl.com.tr/)

Otomatik kargo takip, fiyat hesaplama ve etiket basımı panelden yapılır.

### E-Fatura ve E-Arşiv

GİB onaylı entegrasyonlar:

- [Paraşüt](https://www.parasut.com/)
- [EDM](https://www.edm.com.tr/)
- [Uyumsoft](https://www.uyumsoft.com.tr/)

Sipariş onaylandığı anda otomatik fatura kesimi yapılır, e-arşiv saklama otomatiktir.

### Pazaryeri Senkronizasyonu

- [Trendyol](https://www.trendyol.com/)
- [Hepsiburada](https://www.hepsiburada.com/)
- [n11](https://www.n11.com/)
- [ÇiçekSepeti](https://www.ciceksepeti.com/)
- [Amazon Türkiye](https://www.amazon.com.tr/)

Ürün, stok ve fiyat senkronizasyonu çift yönlüdür. Sipariş çekimi otomatiktir.

---

## QR Menü Yazılımı

Restoran, kafe ve otel işletmeleri için QR kod tabanlı dijital menü çözümü.

- Çok dilli menü desteği
- Görsel destekli ürün gösterimi
- Alerjen, kalori, içerik bilgileri
- Anlık menü ve fiyat güncellemesi
- Müşteri analitiği ve sipariş raporları
- Anlık stok kontrolü

---

## Rent A Car Yazılımı

Araç kiralama işletmelerine yönelik yönetim platformu.

- Filo yönetimi, araç kart sistemi
- Online rezervasyon ve müsaitlik takvimi
- Müşteri, sürücü, sözleşme yönetimi
- Hasar, sigorta, bakım kayıtları
- Sanal POS üzerinden ödeme alma
- Fiyatlandırma kuralları (sezonluk, günlük, kilometre bazlı)

---

## Uyumluluk

Tüm ürünler yerel mevzuat gereksinimleri gözetilerek yapılandırılmıştır.

### KVKK (Kişisel Verilerin Korunması Kanunu)

- Aydınlatma metni şablonu ve açık rıza kayıtları
- Çerez yönetimi ve kullanıcı onay bandı
- Veri silme talebi ve hesap kapatma akışı
- Veri saklama süresi yapılandırması
- VERBİS uyumlu loglama

Kaynak: https://www.kvkk.gov.tr/ | https://verbis.kvkk.gov.tr/

### BİK (Basın İlan Kurumu)

Haber Sistemi için resmi ilan ve mahreç yönetimi yerleşik gelir.

Kaynak: https://www.bik.gov.tr/

### İYS (İleti Yönetim Sistemi)

E-posta, SMS ve arama izinleri ayrı kayıt edilir, İYS sunucusuna senkronize edilir.

Kaynak: https://iys.org.tr/

### GİB E-Fatura

Sipariş onayında otomatik fatura çağrısı ve e-arşiv saklama.

Kaynak: https://ebelge.gib.gov.tr/

---

## Demo Erişimi

Ücretsiz demo ortamları kullanıma açıktır:

- Haber Sistemi: https://haber1.alestaweb.com — alternatif https://haber3.alestaweb.com
- E-Ticaret: https://eticaret.alestaweb.com

Demo erişim bilgileri için iletişim formundan talep gönderilebilir.

---

## İletişim

- Web: https://alestaweb.com
- Satış ve genel: admin@alestaweb.com
- Telefon: +90 505 532 36 38
- Adres: İpekyol Mahallesi, Haliliye / Şanlıurfa

---

## Lisans

Bu belge MIT lisansı altındadır. Yeniden paylaşılabilir, kopyalanabilir, uyarlanabilir. Yazılım ürünlerinin lisans şartları ayrı sözleşmelerde belirtilir.
