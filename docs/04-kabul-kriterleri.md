# 04 — Kabul koşulları

Ekip: Grup 04 — İhsan Kart, Metin Efe Uğur, Ramazan Berat Koç  
Tarih: 19.11.2026  
Sürüm: 0.1  
Hazırlayan: Metin Efe Uğur · İnceleyen: Ramazan Berat Koç (inceleme henüz yapılmadı)  
İncelenen prototip: Klinik Randevu v0.1  
Durum: AC-01–AC-08 ve ALT-01 yazıldı ve 19.11.2026 gözlemleriyle karşılaştırıldı. Kalite kontrolleri (AC-NFR-01–03) planlandı, uygulanmadı.

**Verilen:** başlangıç durumu · **Ne zaman:** kullanıcının tek eylemi · **O zaman:** dışarıdan görülebilen sonuç.

Kayıt numaraları (R005, R008) bizim denememize aittir. Başka bir denemede farklı numara çıkabilir; önemli olan kaydın beklenen duruma geçmesidir.

## Kabul koşulları tablosu

| AC | FR / BR | Verilen | Ne zaman | O zaman | Sonuç | Kanıt |
|---|---|---|---|---|---|---|
| AC-01 | FR-01 | Hasta rolü, veri sıfırlanmış. Doktor Deniz Arı, 12 Kasım. | Doktor Selin Kaya seçilir. | Saatler Selin Kaya'ya göre değişir: 09:30 Dolu, 11:00 Kapalı, diğer sekiz saat Uygun. | Geçti | G-01 |
| AC-02 | FR-02 | Resepsiyon, örnek hasta Kaan, Selin Kaya, 12 Kasım. 14:00 Uygun. Toplamlar 1/1/0/2. | 14:00 seçilip "Randevuyu onayla"ya basılır. | Kaan adına Bekliyor yeni kayıt listede görünür. 14:00 Dolu olur. Toplamlar 2/1/0/3 olur. Onay düğmesi tekrar pasifleşir. | Geçti (R008) | G-02 |
| AC-03 | FR-03 | Hasta rolü, Kaan, Selin Kaya, 12 Kasım. Kaan'ın 14:00 kaydı Bekliyor. | "İptal et" → onay penceresinde **Tamam**. | Kayıt İptal edildi olur ve listede kalır. Düğmesi kalkar. 14:00 Uygun olur. | Geçti (R008) | G-05 |
| ALT-01 | FR-03 | AC-03 ile aynı başlangıç. | "İptal et" → onay penceresinde **İptal** (vazgeç). | Kayıt Bekliyor kalır, İptal et düğmesi durur, 14:00 Dolu kalır. | Geçti. Not: vazgeçince ayrı mesaj çıkmıyor. | G-04 |
| AC-04 | FR-04 | Resepsiyon, örnek hasta **Kaan**, Selin Kaya, 12 Kasım. Günde Ece ve Kaan'a ait kayıtlar var. | Günlük liste incelenir. | Ece'nin ve Kaan'ın kayıtları birlikte, saat sırasıyla görünür. Hasta seçimi listeyi daraltmaz. Hiçbir kayıtta İptal et / Tamamlandı düğmesi yoktur. | Geçti | G-08 |
| AC-05 | FR-05 | Doktor rolü, Selin Kaya, 12 Kasım. R005 / 09:30 Bekliyor. Toplamlar 1/1/1/3. | R005 için "Tamamlandı"ya basılır. | R005 Tamamlandı olur, düğmesi kalkar. 09:30 Kapalı olur. Toplamlar 0/2/1/3 olur, toplam değişmez. | Geçti | G-07 |
| AC-06 | FR-06 | Resepsiyon rolü, Deniz Arı, **13 Kasım**. | B3 incelenir. | Sayılar yalnız o güne aittir: 1 bekleyen, 0 tamamlanan, 0 iptal, toplam 1. Listede yalnız R007 vardır. | Geçti | G-09 |
| AC-07 | BR-01, FR-02 | Hasta rolü, **Ece**, Selin Kaya, 12 Kasım. 14:00'te Kaan'ın Bekliyor kaydı var. | 14:00'e tıklanmaya çalışılır. | 14:00 Dolu kalır ve seçilemez. Onay düğmesi pasif kalır. Yeni kayıt oluşmaz. | Geçti | G-03 |
| AC-08 | FR-06, FR-02 (ret) | Önce Hasta (Ece, Selin Kaya), sonra Doktor rolü. | Her iki rolde B3 ve B1 incelenir. | Hasta rolünde toplam sayıları görünmez. Doktor rolünde bütün saat düğmeleri ve "Randevuyu onayla" pasiftir; doktor kayıt açamaz. | Geçti | G-06, G-07 |

## Bir koşulu birlikte okuyalım — AC-05

- **Neden bu başlangıç?** Tamamlama yalnız Bekliyor kayıtta mümkündür. R006 zaten Tamamlandı olduğu için onu seçmedik.
- **Neden toplam değişmez?** Tamamlama yeni kayıt açmaz; yalnız bir kaydı "bekleyen"den "tamamlanan"a taşır.
- **Neden 09:30 Kapalı?** BR-01'e göre Tamamlandı kaydı saati yeniden açmaz. Kapalı ile İptal sonrası Uygun farklı sonuçlardır (AC-03).

## Kalite kontrol planları (henüz uygulanmadı)

### AC-NFR-01 — İptal ve vazgeçme görevleri (NFR-01)

- **Katılımcı:** Prototipi daha önce kullanmamış 4 kişi (gerekirse başka gruplardan). Bir kişinin dört denemesi dört katılımcı sayılmaz.
- **Hazırlık:** Her görev için Kaan / Selin Kaya / 12 Kasım'da ayrı Bekliyor kayıt açılır.
- **Okunacak görevler:** (1) "14:00'teki randevunuzu iptal edin." (2) "13:30'daki randevunuzu iptal etmeye başlayın, sonra vazgeçip randevuyu koruyun."
- **Kayıt:** süre (sn), doğru/yanlış, yardım istedi mi?
- **Başarı:** En az 3/4 katılımcı iki görevi de doğru, yardımsız ve her biri ≤ 60 sn yapar.

| Katılımcı | Görev 1 süre / doğru / yardım | Görev 2 süre / doğru / yardım | Başarılı mı? |
|---|---|---|---|
| K1 | [ ] | [ ] | [ ] |
| K2 | [ ] | [ ] | [ ] |
| K3 | [ ] | [ ] | [ ] |
| K4 | [ ] | [ ] | [ ] |

### AC-NFR-02 — Doktor değişiminde yanıt süresi (NFR-02)

- **Ortam:** Bilgisayar [ ], işletim sistemi [ ], tarayıcı ve sürüm [ ], ekran kaydı programı ve kare hızı [ ].
- **Adım:** Resepsiyon, 12 Kasım. Deniz Arı ↔ Selin Kaya arasında 10 değişiklik yapılır, ekran kaydedilir.
- **Doğruluk referansı:** Deniz Arı'da 09:00 ve 10:00 Dolu, 11:00 Kapalı. Selin Kaya'da 09:30 ve 11:00 durumları G-08'deki gibi.
- **Başarı:** 10/10 denemede üç alan da ≤ 1 sn içinde doğru içeriği gösterir.

| Deneme | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|---|---|---|---|---|---|---|---|---|---|---|
| Süre (sn) | | | | | | | | | | |

### AC-NFR-03 — Klavyeyle dört görev (NFR-03)

| Görev | Başlangıç | Beklenen son durum | Tamamlandı mı? | Odak görünür mü? | Takılma var mı? |
|---|---|---|---|---|---|
| Randevu oluşturma | Hasta, Ece, Selin Kaya, 12 Kasım | Yeni Bekliyor kayıt, saat Dolu | [ ] | [ ] | [ ] |
| İptalden vazgeçme | Hasta, kendi Bekliyor kaydı | Kayıt Bekliyor, saat Dolu | [ ] | [ ] | [ ] |
| İptal | Hasta, kendi Bekliyor kaydı | İptal edildi, saat Uygun | [ ] | [ ] | [ ] |
| Tamamlama | Doktor, Bekliyor kayıt | Tamamlandı, saat Kapalı | [ ] | [ ] | [ ] |

## Kontrol

- [x] Her FR için en az bir kabul koşulu var (FR-01: AC-01 · FR-02: AC-02, AC-07, AC-08 · FR-03: AC-03, ALT-01 · FR-04: AC-04 · FR-05: AC-05 · FR-06: AC-06, AC-08).
- [x] BR-01 için olumlu (AC-02) ve reddedilen (AC-07) durum var.
- [ ] İkinci ekip üyesi koşulları 03 ile karşılaştırdı. → Ramazan Berat Koç, tarih [ ]
- [ ] Kalite ölçümleri yapıldı.
