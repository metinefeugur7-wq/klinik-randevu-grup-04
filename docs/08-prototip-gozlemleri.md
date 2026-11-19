# 08 — Prototip gözlemleri

Ekip: Grup 04 — İhsan Kart, Metin Efe Uğur, Ramazan Berat Koç  
Tarayıcı: Chromium (otomatik tarayıcı), ekran 1280×900  
İncelenen sürüm: Klinik Randevu v0.1 — birleşik 1–2. hafta başlangıç paketi  
Gözlem tarihi: 19.11.2026  
Başlamadan örnek veri sıfırlandı mı? **Evet.** "Örnek veriyi sıfırla" düğmesine basıldı, onay penceresinde Tamam seçildi.  
Ekran görüntüleri: `kanit/` klasöründe, her satırda dosya adıyla belirtildi.

"Gördüm" ile "olmasını istiyorum" ifadelerini ayırıyoruz. **Beklenen** sütunu denemeden önce yazıldı. **Gözlenen** sütunu ekranda ne çıktıysa onu anlatıyor.

**Öğretmen örneğinden farkımız:** Öğretmen denemeleri ağırlıkla Deniz Arı üzerinden yapılmıştı. Biz kendi denemelerimizde **Doktor Selin Kaya / 12 Kasım 2030** gününü ve **13 Kasım** tarihini kullandık. Öğretmen oturumunda hiç yapılmamış olan **Resepsiyonun randevu oluşturması**nı da denedik (G-02). Kayıt numaraları (R008 vb.) bizim denememize aittir.

## Başlangıç durumu (sıfırlama sonrası)

Hasta / Ece Yılmaz / Deniz Arı / 12.11.2030 açıldı. B1'de 09:00 ve 10:00 Dolu, 11:00 Kapalı, diğer saatler Uygun. B2'de "Randevularım" başlığı altında R001 (Bekliyor, İptal et düğmeli) ve R003 (Tamamlandı) var. B3 günlük toplamlar hasta rolünde gizli. Kanıt: `kanit/G00-baslangic.png`.

## Gözlem tablosu

| No | Rol / hasta / doktor / tarih | Uygulanan adımlar | Beklenen | Gözlenen | Alan | Yorum / soru |
|---|---|---|---|---|---|---|
| G-01 | Hasta / Kaan Demir / Selin Kaya / 12.11.2030 | Örnek hasta Kaan, doktor Selin Kaya seçildi. | Saatler Selin Kaya'ya göre değişmeli. Randevularım'da yalnız Kaan'ın Selin Kaya kayıtları görünmeli. | 09:30 Dolu (R005), 11:00 Kapalı (R006), diğerleri Uygun. Randevularım'da yalnız R006 / 11:00 / Tamamlandı var; iptal düğmesi yok. Ece'nin R005 kaydı listede yok ama 09:30 Dolu görünüyor. | B1, B2 | Beklenenle aynı. Hasta, saatin kime ait olduğunu görmüyor, yalnız Dolu olduğunu görüyor. Kanıt: `G01-hasta-kaan-selin.png` |
| G-02 | Resepsiyon / Kaan Demir / Selin Kaya / 12.11.2030 | Resepsiyon rolüne geçildi. 14:00 seçildi, "Randevuyu onayla"ya basıldı. | Kaan adına Bekliyor kayıt oluşmalı, 14:00 Dolu olmalı. Toplamlar 1/1/0/2'den 2/1/0/3'e geçmeli. | Seçim öncesi onay düğmesi pasif. 14:00 seçilince "Seçili" yazdı ve düğme etkinleşti. Onaydan sonra "R008 oluşturuldu: Kaan Demir, 12 Kasım 2030 saat 14:00" bildirimi çıktı. R008 Bekliyor olarak listede, 14:00 Dolu. Toplamlar 2 bekleyen / 1 tamamlanan / 0 iptal / 3 toplam. | B1, B2, B3, bildirim | Resepsiyonun hasta adına kayıt açabildiği doğrulandı. Öğretmen oturumunda bu adım denenmemişti. Kanıt: `G02a-…`, `G02b-resepsiyon-olusturdu.png` |
| G-03 | Hasta / Ece Yılmaz / Selin Kaya / 12.11.2030 | Hasta rolünde Ece seçildi. Kaan'a ait 14:00 Dolu saatine tıklanmaya çalışıldı. | 14:00 Dolu ve seçilemez olmalı. Onay düğmesi pasif kalmalı, yeni kayıt oluşmamalı (BR-01). | 14:00 Dolu ve düğme pasif. Tıklama denemesi hiçbir şeyi değiştirmedi; onay düğmesi pasif kaldı, kayıt eklenmedi. | B1 | BR-01'in arayüzdeki karşılığı. Hasta değişse de doktor + tarih + saat dolu kalıyor. Kanıt: `G03-ece-1400-dolu.png` |
| G-04 | Hasta / Kaan Demir / Selin Kaya / 12.11.2030 | R008 için "İptal et"e basıldı. Açılan "R008 — 12 Kasım 2030 saat 14:00 randevusu iptal edilsin mi?" penceresinde **İptal** seçildi (vazgeçme). | R008 Bekliyor kalmalı, 14:00 Dolu kalmalı. | R008 Bekliyor ve İptal et düğmesi duruyor. 14:00 Dolu. Üstteki bildirim değişmedi; vazgeçildiğine dair ayrı bir mesaj çıkmadı. | Onay penceresi, B1, B2 | Vazgeçme doğru çalıştı. Ancak "İptal et" ile pencerenin "İptal" düğmesi ters anlamda; vazgeçince geri bildirim yok (bkz. RSK-01). Kanıt: `G04-vazgec.png` |
| G-05 | Hasta / Kaan Demir / Selin Kaya / 12.11.2030 | R008 için tekrar "İptal et"e basıldı, pencerede **Tamam** seçildi. | R008 İptal edildi olmalı, listede kalmalı, 14:00 yeniden Uygun olmalı. | "R008 iptal edildi. İlgili saat yeniden uygun…" bildirimi çıktı. R008 "İptal edildi" etiketiyle listede, düğmesi yok. 14:00 Uygun. | Onay penceresi, B1, B2 | Beklenenle aynı. Kanıt: `G05-iptal.png` |
| G-06 | Hasta / Ece Yılmaz / Selin Kaya / 12.11.2030 | Hasta seçimi Ece yapıldı. | Yalnız Ece'nin kaydı görünmeli. Günlük toplamlar gösterilmemeli. | Randevularım'da yalnız R005 / 09:30 / Bekliyor (İptal et düğmeli). Kaan'ın R006 ve R008 kayıtları görünmüyor. B3'te sayılar yerine kilit açıklaması var. | B2, B3 | Hasta rolünde toplamların gizlendiği ekranda doğrulandı. Kanıt: `G06-hasta-ece.png` |
| G-07 | Doktor / (hasta seçimi pasif) / Selin Kaya / 12.11.2030 | Doktor rolüne geçildi. Liste incelendi, ardından R005 için "Tamamlandı"ya basıldı. | Önce: R005, R006, R008 birlikte görünmeli. Toplamlar 1/1/1/3 olmalı. Saatler seçilememeli. Sonra: R005 Tamamlandı, 09:30 Kapalı, toplamlar 0/2/1/3 olmalı. | Önce: üç kayıt görünüyor. Yalnız Bekliyor olan R005'te "Tamamlandı" düğmesi var. Toplamlar 1/1/1/3. Örnek hasta alanı ve bütün saat düğmeleri pasif, onay düğmesi pasif. Sonra: R005 Tamamlandı ve düğmesi kalktı. 09:30 "Kapalı" oldu. Toplamlar 0/2/1/3. | B1, B2, B3 | Beklenenle aynı. Doktor rolünde boş saatler "Uygun" yazıyor ama tıklanamıyor; kullanıcı kafası karışabilir. Kanıt: `G07a-…`, `G07b-doktor-tamamladi.png` |
| G-08 | Resepsiyon / Kaan Demir / Selin Kaya / 12.11.2030 | Resepsiyon rolüne geçildi. Liste ve toplamlar incelendi. | Üç kayıt görünmeli. Hiçbir kayıtta İptal et veya Tamamlandı düğmesi olmamalı. Toplamlar 0/2/1/3 olmalı. | Üç kayıt durum etiketleriyle görünüyor, işlem düğmesi yok. Toplamlar 0/2/1/3, doktor görünümüyle aynı. Hasta seçimi Kaan olduğu hâlde Ece'nin R005 kaydı da listede. | B2, B3 | Resepsiyonda hasta seçimi listeyi daraltmıyor. Kanıt: `G08-resepsiyon-liste.png` |
| G-09 | Resepsiyon / Kaan Demir / Deniz Arı / 13.11.2030 | Doktor Deniz Arı, tarih 13 Kasım seçildi. | Yalnız o güne ait R007 görünmeli. 10:30 Dolu olmalı. Toplamlar 1/0/0/1 olmalı. | Listede yalnız R007 / Kaan / 10:30 / Bekliyor. 10:30 Dolu, diğer saatler Uygun. Toplamlar 1/0/0/1. | B1, B2, B3 | Liste ve toplamlar yalnız seçili doktor + tarih için. Kanıt: `G09-deniz-13kasim.png` |
| G-10 | Resepsiyon → yenileme → Resepsiyon / Selin Kaya / 12.11.2030 | Sayfa yenilendi. Açılışta görülen durum not edildi. Ardından yeniden Resepsiyon ve Selin Kaya seçildi. | Randevu kayıtları korunmalı. Rol ve seçimler başlangıç değerine dönebilir. | Açılışta rol Hasta / Ece / Deniz Arı / 12 Kasım'a döndü. Yeniden Resepsiyon + Selin Kaya seçilince R005 Tamamlandı, R006 Tamamlandı, R008 İptal edildi görünüyor. Toplamlar 0/2/1/3, yenileme öncesiyle aynı. Altta "Kaydetme: Bu tarayıcıda yerel kayıt." yazıyor. | Tüm sayfa, kaydetme açıklaması | Aynı dosya ve tarayıcıda kayıtlar korundu. Rol seçiminin sıfırlanması veri kaybı değil. Kanıt: `G10-yenileme.png` |

## Kayıt davranışı

- **Ekrandaki kaydetme açıklaması:** "Kaydetme: Bu tarayıcıda yerel kayıt." Altında sunucuya veri gönderilmediği, tarayıcı verisi silinirse kaybolacağı ve sekmeler/cihazlar arasında eşzamanlama olmadığı yazıyor.
- **Yenilemede gördüğümüz:** Randevu durumları ve toplamlar korundu; rol, hasta, doktor ve tarih seçimleri başlangıç değerine döndü (G-10).
- **Neden başka cihazda aynı sonuç garanti değil:** Kayıt yalnız bu tarayıcının yerel deposunda tutuluyor. Başka bir tarayıcı veya cihaz bu veriyi görmez. Başka cihaz denemesi yapmadık.

## Gördüğümüz ama hata saymadığımız noktalar

Bunlar kapsam ve kullanılabilirlik sorusudur. Yazılım hatası olduklarını iddia etmiyoruz:

1. **Vazgeçince geri bildirim yok (G-04):** Onay penceresinde İptal seçilince kayıt korunuyor, ancak ekranda "işlem iptal edilmedi" gibi bir mesaj çıkmıyor.
2. **Aynı kelime, iki anlam (G-04/G-05):** Karttaki "İptal et" randevuyu iptal etmeyi başlatıyor; penceredeki "İptal" ise bu işlemden vazgeçmek demek.
3. **Doktor rolünde "Uygun" ama pasif saatler (G-07):** Saat boş olduğu için Uygun yazıyor ama doktor seçemiyor. Açıklama metni var, ama düğmenin üzerinde yok.
4. **Hasta, dolu saatin kime ait olduğunu görmüyor (G-01, G-03):** Gizlilik açısından doğru olabilir. Paydaşa soracağız.

## Paydaşa götürülecek sorular

Bu sorular gözlemlerimizden çıktı. Henüz yanıt alınmadı.

1. İptal penceresindeki düğmeler "Randevuyu iptal et" ve "Vazgeç" olarak değiştirilsin mi? Vazgeçince ekranda kısa bir bilgi mesajı gösterilsin mi? (G-04)
2. Resepsiyon hasta adına randevu açabiliyor (G-02), ancak iptal edemiyor (G-08). Telefonla iptal isteyen hasta için resepsiyonun iptal yetkisi olmalı mı?
3. Hasta, başka hastaya ait dolu saati yalnız "Dolu" olarak mı görmeli, yoksa hiç görmemeli mi? (G-01, G-03)
4. Hasta, doktor ve resepsiyon farklı cihazlardan aynı kayıtları görmeli mi? (G-10)

## Tekrar kontrolü

Bu denemeler otomatik bir tarayıcıda, adım adım uygulanıp ekran görüntüsüyle kaydedildi. Ekip üyelerinden biri aynı adımları kendi Chrome tarayıcısında (önce "Örnek veriyi sıfırla") tekrar edip sonucu karşılaştıracak:

- Tekrar eden üye: Ramazan Berat Koç — Tarih: 19.11.2026 — Tarayıcı: Google Chrome, yerel `index.html` — Önce örnek veri sıfırlandı.
  - G-02 (Resepsiyon / Kaan / Selin Kaya / 14:00 → onayla): R008 Bekliyor oluştu, 14:00 Dolu. **Aynı.**
  - G-05 (Hasta / Kaan / R008 → İptal et → Tamam): R008 İptal edildi, listede kaldı, 14:00 Uygun; hasta rolünde toplamlar gizli. **Aynı.**
  - G-07 (Doktor / Selin Kaya / R005 → Tamamlandı): R005 Tamamlandı, 09:30 Kapalı, toplamlar 0/2/1/3; saatler ve onay düğmesi pasif. **Aynı.**
  - Diğer satırlar (G-01, G-03, G-04, G-06, G-08–G-10) bu tekrarda ayrıca denenmedi.
