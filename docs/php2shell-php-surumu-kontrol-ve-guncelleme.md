# PHP2Shell: PHP sürümünüzü nasıl kontrol eder ve güncellersiniz?

21 Ekim 2026'da PHP projesi, PHP motorunun kendisindeki iki kritik açık için acil güncelleme yayımladı: **CVE-2026-109618** ve **CVE-2026-109619**. İkisine birden "PHP2Shell" deniyor. Açıklar, giriş yapmadan, yalnızca hazırlanmış bir dosya yükleme isteğiyle sunucuda kod çalıştırmaya imkân veriyor. PHP'nin resmî puanı CVSS 4.0 ile 9,2.

Bu yazı site sahipleri, küçük işletmeler ve yeni başlayan geliştiriciler için. Amaç üç soruya cevap vermek: Sitem hangi PHP sürümünde çalışıyor? Güncelleme gerekiyor mu? Güncellendiğini nasıl anlarım?

## 1. Neden önemli?

Açık, sitenizin kullandığı yazılımda değil, PHP'nin kendisinde. Bu yüzden içerik yönetim sisteminizi, eklentilerinizi veya temanızı güncellemek **sizi korumaz**. Sunucudaki PHP güncellenmeli.

Saldırgan özel hazırlanmış bir `multipart/form-data` isteği gönderiyor. Bu, dosya yükleme formlarının kullandığı istek türü. Sitenin kodu hiç çalışmadan bile tetiklenebiliyor. Araştırmacılar, sunucu belleğindeki başka ziyaretçilere ait şifre, oturum bilgisi ve API anahtarlarının yanıt çerezine sızabildiğini de gösterdi.

## 2. Hangi sürümler yamalı?

| PHP dalı | Durum |
|---|---|
| 8.5 | **8.5.12** ve üstü yamalı |
| 8.4 | **8.4.27** ve üstü yamalı |
| 8.3 | **8.3.36** ve üstü yamalı |
| 8.2 | **8.2.35** ve üstü yamalı |
| 8.1, 8.0, 7.4 | Resmî sürüm yok. Yalnız dağıtım ve panel üreticilerine kaynak kod yaması verildi; sağlayıcınızın paketine bağlı |
| 5.4 – 7.3 | Desteği bitmiş. PHP projesinden düzeltme yok |

Etkilenen kod 2012'deki PHP 5.4.0'a kadar gidiyor. Yani eski bir sürümde "bize bir şey olmaz" demek doğru değil.

## 3. Sitem hangi PHP sürümünde çalışıyor?

Üç yol var. En güvenilirden başlayalım.

**a) Barındırma panelinden.** Paylaşımlı barındırmada panelde genellikle "PHP Sürümü", "PHP Seçici" veya "MultiPHP" gibi bir ekran olur. Burada her alan adı için seçili PHP sürümü yazar. Bu ekranda yalnızca dal görünebilir (ör. 8.3); alt sürüm (8.3.36 mı, 8.3.35 mi) görünmüyorsa sağlayıcınıza sorun.

**b) Geçici bir sürüm sayfasıyla.** Sitenizin kök dizinine rastgele adlı bir dosya koyun (ör. `surum-k8x2.php`) ve içine yalnızca `<?php echo PHP_VERSION;` yazın. Tarayıcıda açın, sürümü not edin ve dosyayı **hemen silin**. Tam `phpinfo()` sayfası bırakmayın: sunucu hakkında saldırgana fazla bilgi verir.

**c) Sunucuya erişiminiz varsa komut satırından.** `php -v` komutu sürümü gösterir. Ama dikkat: bu, web sitesinin kullandığı PHP'yi değil, komut satırı PHP'sini gösterir. Sunucuda birden fazla PHP olabilir. Web tarafının sürümünü öğrenmenin doğru yolu yine (b) maddesindeki sayfadır.

**Önemli tuzak:** Linux dağıtımlarının paketleri yamayı eski sürüm numarasının üstüne uygular. Örneğin Ubuntu 24.04'te yamalı paketin sürümü `8.3.6-0ubuntu0.24.04.13` olarak görünür; "8.3.36" yazmaz ama yamalıdır. Bu durumda sürüm numarasına değil, dağıtımın güvenlik duyurusundaki **paket sürümüne** bakılır.

## 4. Paylaşımlı barındırmadaysanız

Sunucuyu siz yönetmiyorsanız güncellemeyi sağlayıcınız yapar. Sizin işiniz:

- Sağlayıcınızın duyuru sayfasına veya e-postasına bakın: PHP2Shell için güncelleme yapıldı mı, hangi tarihte?
- Panelde seçili PHP dalı 8.1 veya daha eskiyse, desteklenen bir dala (tercihen 8.3 veya 8.4) geçin. Geçmeden önce sitenizin yedeğini alın ve bir deneme alanında test edin.
- Sağlayıcınızdan net bir cevap alamıyorsanız destek talebi açıp "PHP2Shell (CVE-2026-109618 ve CVE-2026-109619) için sunucudaki PHP sürümleri güncellendi mi, PHP işlemleri yeniden başlatıldı mı?" diye sorun.

## 5. Sunucuyu kendiniz yönetiyorsanız

Genel kural her sistemde aynı: **paketi güncelle, bütün PHP işlemlerini yeniden başlat, sürümü web üzerinden doğrula.**

- **Debian ve Ubuntu:** `sudo apt-get update` ve ardından PHP paketlerini `--only-upgrade` ile güncelleyin. Kontrol için `dpkg -l | grep php`. Ubuntu'da yamalı paket sürümleri USN-8948-1 duyurusunda; 18.04 ve 20.04 için Ubuntu Pro (ESM) gerekiyor.
- **RHEL, AlmaLinux, Rocky:** `sudo dnf upgrade 'php*'`, kontrol için `rpm -q php-common` veya `dnf updateinfo list --security`.
- **Hazır kontrol paneli kullanıyorsanız:** Panelin PHP'si çoğu zaman işletim sistemi paketlerinden ayrıdır; `apt` veya `dnf` onu güncellemez. Panelin kendi güncelleme ekranını veya üreticinin duyurduğu komutu kullanın. Panelin kendi arayüzü için ayrı bir PHP kullanılıyorsa onun da güncellenmesi gerekir.
- **Docker:** Resmî `php` imajlarının yeni etiketini çekin, kendi imajlarınızı `docker build --pull` ile yeniden derleyin, kapsayıcıları yeniden oluşturun. Adında `RC1` geçen etiketler yamalı değildir.
- **Windows ve macOS:** windows.php.net yamalı derlemeleri listeliyor. Homebrew'da `brew upgrade php` yeterli. İkisinde de PHP'yi çalıştıran hizmeti yeniden başlatın.

## 6. En sık yapılan hata: yeniden başlatmamak

Paket kurulduğu hâlde eski PHP bellekte çalışmaya devam edebilir.

- PHP-FPM kullanıyorsanız FPM hizmetini yeniden başlatın (ör. `systemctl restart php8.3-fpm`).
- Apache'de PHP modül olarak çalışıyorsa Apache'yi **tam** yeniden başlatın. "Reload" veya "graceful" komutlarıyla eski PHP'nin çalışmaya devam ettiği görüldü.
- LiteSpeed kullanan sunucularda web sunucusunu yeniden başlatmak PHP işlemlerini yeniden başlatmayabilir; PHP işlemlerinin ayrıca sonlandırılması gerekir.
- Kuyruk işçileri ve sürekli çalışan PHP süreçleri de yeniden başlatılmalı.
- Debian ve Ubuntu'da `needrestart` aracı eski kütüphaneyi kullanan süreçleri listeler.

Son adım her zaman aynı: 3. bölümdeki geçici sürüm sayfasıyla web tarafını kontrol edin, sonra sayfayı silin.

## 7. Hemen güncelleyemiyorsanız

PHP projesinin açık ifadesi şu: tek eksiksiz çözüm güncellemek. Aşağıdakiler yalnızca birkaç saatlik zaman kazandırır.

- `session.upload_progress.enabled` ayarını kapatmak (`0`). Açıklardan birinin bilinen yolunu kapatır, diğerini kapatmaz. Ayar `php.ini` veya FPM havuz dosyasında yapılmalı; `.user.ini` veya kod içinden `ini_set()` geç kalır.
- Sitenizde dosya yükleme kullanılmıyorsa web sunucusunda `multipart/form-data` isteklerini engellemek. Dosya yükleme, bazı iletişim ve ödeme formları ile yönetim panelinde görsel yükleme bozulur; test edin.
- Web uygulama güvenlik duvarı (WAF). Yalnız onun üzerinden geçen trafiği korur; sunucunuza doğrudan erişilebiliyorsa işe yaramaz.
- Siteyi geçici olarak kapatıp statik bir bilgi sayfası koymak. ABD siber güvenlik ajansı CISA dahil birçok resmî kurumun önerdiği en güvenli geçici yol bu. Uygulamanın kendi "bakım modu" yeterli değildir, çünkü PHP isteği yine işler.

İnternette dolaşan "tek satırla düzelt" betiklerine ve resmî olmayan eklentilere güvenmeyin.

## 8. Saldırıya uğradım mı?

Henüz resmî bir saldırı göstergesi listesi yayımlanmadı. Şunlara bakın (önce kayıt dosyalarının kopyasını alın):

- 20 Ekim'den bu yana, dosya yükleme formu olmayan adreslere gelen olağandışı POST istekleri
- Bu istekleri izleyen "Allowed memory size exhausted" hataları ve art arda 500 hataları
- Web sunucusu kullanıcısının başlattığı `sh`, `bash`, `curl`, `wget` gibi komutlar
- 20 Ekim sonrası oluşan veya değişen PHP dosyaları, özellikle yükleme klasörlerinde
- Yeni yönetici hesapları, yeni zamanlanmış görevler

Şüphe varsa sunucunun ele geçirildiğini varsayın: veritabanı ve e-posta şifrelerini, API ve ödeme anahtarlarını, uygulama gizli anahtarlarını değiştirin; bütün oturumları kapatın; yönetici şifrelerini yenileyin. Kişisel veri etkilendiyse Kişisel Verileri Koruma Kurulu'na 72 saat içinde bildirim yükümlülüğünü unutmayın.

## 9. İki dolandırıcılığa dikkat

- **Sahte "$PHP2SHELL" kripto parası:** X'te bu adla sahte token tanıtımları dolaşıyor. Böyle bir token yok; cüzdan bağlamayın.
- **Sahte saldırı kodu depoları:** GitHub'da "PHP2Shell PoC" adlı çok sayıda depo var. Hiçbirinin çalıştığı doğrulanmadı ve bu tür depolar zararlı yazılım taşıyabilir. Sunucunuzda veya kendi bilgisayarınızda çalıştırmayın.

## Kontrol listesi

- [ ] Her sitenin web tarafında kullandığı PHP sürümünü öğrendim (komut satırı sürümü değil).
- [ ] Sürüm yamalı listede: 8.5.12, 8.4.27, 8.3.36, 8.2.35 veya dağıtımın yamalı paket sürümü.
- [ ] Paylaşımlı barındırmadaysam sağlayıcımdan güncellemenin yapıldığını yazılı olarak öğrendim.
- [ ] Güncellemeden sonra bütün PHP işlemleri yeniden başlatıldı.
- [ ] Web üzerinden sürümü tekrar kontrol ettim ve geçici sürüm dosyasını sildim.
- [ ] Hazır panel kullanıyorsam panelin kendi PHP'si de güncellendi.
- [ ] 8.1 veya daha eski sürümdeysem desteklenen bir dala geçiş planı yaptım.
- [ ] Kayıt dosyalarında olağandışı yükleme istekleri ve bellek hataları aradım.
- [ ] Şüphe varsa şifreleri ve anahtarları değiştirdim, oturumları kapattım.

## Resmî kaynaklar

- PHP güvenlik bildirimi CVE-2026-109618: https://github.com/php/php-src/security/advisories/GHSA-w8hw-w9fx-j79w
- PHP güvenlik bildirimi CVE-2026-109619: https://github.com/php/php-src/security/advisories/GHSA-6wmf-4rv5-p3rp
- PHP Foundation açıklaması: https://thephp.foundation/blog/2026/10/21/todays-php-security-release-and-how-were-strengthening-php-security/
- php.net sürüm duyurusu: https://www.php.net/archive/2026.php#2026-10-21-5
- CISA uyarısı: https://www.cisa.gov/news-events/alerts/2026/10/21/critical-vulnerabilities-php-require-immediate-patching
- Birleşik Krallık NCSC: https://www.ncsc.gov.uk/news/critical-security-issue-affecting-php
- CERT-EU 2026-018: https://cert.europa.eu/publications/security-advisories/2026-018/
- PHP sürüm destek takvimi: https://www.php.net/supported-versions.php

---

Bu yazı eğitim amaçlıdır ve 22 Ekim 2026 itibarıyla bilinenlere dayanır. Paket sürümleri ve üretici duyuruları hızla değişebilir; uygulamadan önce güncel resmî kaynakları kontrol edin.

Hazırlayan: Alesta WEB — İzmir
