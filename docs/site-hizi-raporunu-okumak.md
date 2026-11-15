# Site hızı raporunu okumak: LCP, INP, CLS ve 12 sık hata

Hız ölçüm aracına sitenizin adresini yazdınız, karşınıza renkli bir puan ve üç harfli kısaltmalar çıktı. Kırmızı bir sayı görünce paniğe kapılmak, yeşil bir sayı görünce de işin bittiğini sanmak çok yaygın. Bu yazı, site sahibinin ve yeni başlayan geliştiricinin bu raporu doğru okuyabilmesi, neyin gerçekten önemli olduğunu ayırabilmesi için hazırlandı.

## Önce iki tür veri olduğunu bilin

Hız raporlarında iki farklı kaynak yan yana durur ve çoğu yanlış yorum bunları karıştırmaktan doğar.

**Saha verisi (gerçek kullanıcı verisi):** Sitenizi Chrome ile ziyaret eden gerçek insanların cihazlarında ölçülen değerlerdir. Google bu verileri son 28 güne yayılan bir pencerede toplar. Arama sonuçlarındaki sayfa deneyimi değerlendirmesi bu veriye dayanır. Siteniz yeterince ziyaret almıyorsa bu bölüm boş görünür; bu bir hata değildir, yalnızca yeterli veri yoktur.

**Laboratuvar verisi:** Aracın o an, tek bir sanal cihazda ve belirli bir bağlantı hızıyla yaptığı denemedir. Sorunun nerede olduğunu bulmak için çok faydalıdır ama tek bir anın fotoğrafıdır. Aynı sayfayı arka arkaya üç kez ölçtüğünüzde farklı puanlar görmeniz normaldir.

Kısacası: saha verisi "kullanıcılarım ne yaşıyor" sorusunu, laboratuvar verisi "neden böyle oluyor" sorusunu cevaplar.

## Üç temel ölçüm

Google'ın Core Web Vitals adını verdiği üç ölçüm, kullanıcı deneyiminin üç ayrı yönüne bakar. Her biri için değerlendirme, ziyaretlerin yüzde 75'inde ulaşılan değere göre yapılır. Yani birkaç yavaş ziyaret sonucu bozmaz, ama ziyaretçilerin dörtte birinden fazlası kötü deneyim yaşıyorsa sonuç kötü çıkar.

### LCP — En büyük içeriğin görünme süresi

Sayfadaki en büyük görsel ya da metin bloğunun ekranda belirdiği andır. Ziyaretçinin "sayfa açıldı" hissine en yakın ölçümdür.

- İyi: 2,5 saniye ve altı
- İyileştirilmeli: 2,5 ile 4 saniye arası
- Kötü: 4 saniyenin üstü

Haber sitelerinde bu öğe çoğunlukla manşet görseli, ürün sayfalarında ana ürün fotoğrafı, kurumsal sitelerde ise üstteki büyük afiştir.

### INP — Tıklamaya verilen tepki süresi

Ziyaretçi bir düğmeye bastığında, menüyü açtığında ya da bir alana yazdığında sayfanın bunu ekranda göstermesi ne kadar sürüyor? INP, ziyaret boyunca yapılan etkileşimlerin en yavaşlarından birini temel alır. Mart 2024'te eski ölçüm olan FID'in yerini aldı; eski yazılarda FID görürseniz bilginin güncel olmadığını anlayın.

- İyi: 200 milisaniye ve altı
- İyileştirilmeli: 200 ile 500 milisaniye arası
- Kötü: 500 milisaniyenin üstü

Laboratuvar raporunda INP yoktur, çünkü sanal ölçümde kimse bir şeye tıklamaz. Onun yerine "toplam engelleme süresi" (TBT) gösterilir; bu değer yüksekse sayfanız büyük olasılıkla tıklamalara geç tepki veriyordur.

### CLS — Sayfanın zıplaması

Okurken metnin aniden aşağı kayması, tam tıklayacakken düğmenin yer değiştirmesi. CLS bunu ölçer ve birimsiz bir sayıdır.

- İyi: 0,1 ve altı
- İyileştirilmeli: 0,1 ile 0,25 arası
- Kötü: 0,25'in üstü

## Puan mı, ölçüm mü?

Aracın en üstte gösterdiği 0–100 arası puan laboratuvar denemesinden hesaplanır. Arama motoru bu puana bakmaz; saha verisindeki üç ölçümün durumuna bakar. 60 puan alan ama saha verisinde üç ölçümü de yeşil olan bir site, 95 puan alan ama gerçek kullanıcıları zıplayan sayfalar yaşayan bir siteden daha iyi durumdadır. Puanı bir ipucu olarak görün, hedef olarak değil.

## Search Console'daki rapor nasıl okunur

Search Console'da "Core Web Vitals" raporu sayfaları tek tek değil, benzer yapıdaki sayfaları gruplayarak gösterir. Örneğin bütün haber detay sayfaları ya da bütün ürün sayfaları tek grupta toplanabilir. Bir gruptaki sorun genellikle o sayfa türünün şablonundan kaynaklanır; tek bir sayfayı değil şablonu düzeltmek gerekir.

Düzeltme yaptıktan sonra rapordaki "düzeltmeyi doğrula" seçeneği kullanılabilir. Saha verisi 28 günlük bir pencereden geldiği için iyileşmenin rapora yansıması birkaç hafta sürer. Ertesi gün değişiklik görmemek düzeltmenin işe yaramadığı anlamına gelmez.

## 12 sık hata

1. **Yalnızca masaüstü sonucuna bakmak.** Ziyaretçilerin büyük kısmı telefondan gelir ve mobil sonuç neredeyse her zaman daha kötüdür. Önce mobile bakın.

2. **Tek bir ölçümle karar vermek.** Laboratuvar puanı her denemede oynar. Karar vermeden önce en az üç ölçüm alın, saha verisi varsa ona öncelik verin.

3. **Yalnızca ana sayfayı ölçmek.** Trafiğin çoğu iç sayfalara gelir: haber detayı, ürün, blog yazısı. En çok ziyaret alan sayfa türlerini ayrı ayrı ölçün.

4. **En üstteki görsele geç yükleme vermek.** Geç yükleme ekranın altındaki görseller için iyidir. Sayfanın en üstündeki büyük görsele uygulanırsa LCP gecikir.

5. **Telefona masaüstü boyutunda görsel göndermek.** 2000 piksel genişliğindeki fotoğrafı 400 piksellik ekrana göndermek hem süreyi hem veri harcamasını artırır. Görselleri kullanılacağı boyuta göre hazırlayın, modern biçimleri (WebP, AVIF) tercih edin.

6. **Görsel ve reklam alanlarına yer ayırmamak.** Genişliği ve yüksekliği belirtilmeyen görsel, yüklenince altındaki her şeyi iter. Reklam ve video gömme alanlarına da baştan sabit bir yer ayrılmalıdır. CLS sorunlarının çoğu buradan gelir.

7. **Sonradan beliren çerez bildirimi ve duyuru çubukları.** Sayfanın üstüne birkaç saniye sonra eklenen şerit içeriği aşağı kaydırır. Bu tür öğeler ya içeriğin üzerine binecek şekilde ya da baştan yeri ayrılmış olarak gösterilmelidir.

8. **Her eklentiyi, her etiketi sayfaya yığmak.** Sohbet balonu, ısı haritası, birden çok ölçüm kodu, sosyal medya akışı… Her biri tıklama tepkisini yavaşlatır. Kullanmadığınız etiketi kaldırın, kalanları içerik yüklendikten sonra çalışacak şekilde ayarlayın.

9. **Yazı tipi aşırılığı.** Dört farklı yazı tipi ailesi ve her birinden altı kalınlık yüklemek ilk görünümü geciktirir. İki aile ve gerçekten kullanılan kalınlıklar çoğu site için yeterlidir.

10. **Sunucu tarafını hiç düşünmemek.** Sayfanın ilk baytı geç geliyorsa ön yüzdeki her iyileştirme sınırlı kalır. Önbellek kullanılıyor mu, yavaş veritabanı sorgusu var mı, barındırma yeterli mi; bunlar da sorulmalıdır.

11. **Puanı yükseltmek için ziyaretçiyi feda etmek.** Ölçüm aracını kandırmaya yönelik numaralar (içeriği gizleyip sonradan göstermek gibi) gerçek kullanıcının deneyimini düzeltmez. Saha verisi zamanla gerçeği gösterir.

12. **Düzeltmeden sonra ölçmemek.** Yapılan değişikliğin işe yarayıp yaramadığını anlamanın tek yolu öncesi ve sonrasını aynı koşullarda ölçmektir. Değişiklik tarihini not edin, birkaç hafta sonra saha verisiyle karşılaştırın.

## Nereden başlamalı?

Sınırlı zamanınız varsa şu sırayla ilerleyin:

1. Search Console'da hangi sayfa grubunun kötü durumda olduğunu bulun.
2. O gruptan en çok ziyaret alan sayfayı mobil ayarla ölçün.
3. Hangi ölçüm kırmızıysa ona odaklanın: LCP ise görsel ve sunucu yanıtı, CLS ise yer ayrılmamış alanlar, INP ise ağır betikler.
4. Tek seferde tek değişiklik yapın, sonucu ölçün.
5. Düzelttiğiniz şablonun bütün sayfalara yansıdığını kontrol edin.

## Kontrol listesi

- [ ] Saha verisi ile laboratuvar verisini ayrı ayrı okuyorum.
- [ ] Önce mobil sonuca bakıyorum.
- [ ] Ana sayfanın yanında en çok ziyaret alan iç sayfa türlerini de ölçtüm.
- [ ] En üstteki büyük görsele geç yükleme uygulanmıyor.
- [ ] Görseller ekran boyutuna göre hazırlanıyor ve modern biçimde sunuluyor.
- [ ] Bütün görsellerin genişliği ve yüksekliği belirtilmiş.
- [ ] Reklam, video ve gömme alanlarının yeri baştan ayrılmış.
- [ ] Çerez bildirimi ve duyuru şeridi içeriği aşağı itmiyor.
- [ ] Kullanılmayan eklenti ve ölçüm etiketleri kaldırıldı.
- [ ] Yazı tipi ailesi ve kalınlık sayısı gerçekten kullanılanlarla sınırlı.
- [ ] Sunucu yanıt süresi ve önbellek durumu kontrol edildi.
- [ ] Her değişikliğin tarihini not ediyor, sonucu birkaç hafta sonra saha verisiyle karşılaştırıyorum.

## Resmî kaynaklar

- Google — Core Web Vitals hakkında: https://web.dev/articles/vitals
- Google — LCP: https://web.dev/articles/lcp
- Google — INP: https://web.dev/articles/inp
- Google — CLS: https://web.dev/articles/cls
- Google Search Central — Core Web Vitals raporu: https://support.google.com/webmasters/answer/9205520
- PageSpeed Insights: https://pagespeed.web.dev

---

Bu yazı genel bilgilendirme amaçlıdır. Hazırlayan: Alesta WEB — İzmir
