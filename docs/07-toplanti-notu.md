# 07 — Kısa ekip toplantısı

Ekip: Grup 04 — İhsan Kart, Metin Efe Uğur, Ramazan Berat Koç  
Sürüm: 0.1  
Durum: **Gündem ve karar önerileri hazır. Toplantı henüz yapılmadı.** Toplantıdan sonra tarih, süre, katılanlar ve kararların son hâli yazılacak.

Tarih ve süre: [gg.aa.2026 · __ dk]  
Yer: [Sınıf / çevrimiçi]  
Katılanlar: [ ] İhsan Kart · [ ] Metin Efe Uğur · [ ] Ramazan Berat Koç  
Notu yazan: Ramazan Berat Koç

## Toplantının amacı

1–2. hafta belgelerinin durumunu birlikte gözden geçirmek, görev dağılımını onaylamak, açık soruları ve riskleri takibe almak, GitHub'a yükleme adımlarını sıraya koymak.

## Gündem (yaklaşık 20 dk)

1. **Kapsam ve roller (3 dk):** 01'deki FR-01–FR-06 ve BR-01 kapsamı. Resepsiyon iptal/tamamlama yapmaz, doktor randevu açmaz.
2. **Gözlemler (5 dk):** 08'deki G-01–G-10. Her üye en az bir gözlemi kendi tarayıcısında tekrarlar.
3. **Gereksinim ve kabul koşulları (5 dk):** 03 ile 04'ün karşılaştırılması, 05 izlenebilirlik tablosu.
4. **Riskler (3 dk):** RSK-01 (yanlışlıkla iptal) ve RSK-04 (3 kişilik ekip).
5. **Görev ve GitHub (4 dk):** 09'daki görev dağılımı, depo, issue ve PR adımları.

## Karar önerileri

Toplantıda her satır için "Kabul / Değişti / Ret" yazılacak.

| No | Karar önerisi | Gerekçe | İlgili | Sorumlu | Kontrol zamanı | Toplantı sonucu |
|---|---|---|---|---|---|---|
| K-01 | 1–2. haftada yalnız mevcut FR-01–FR-06 ve BR-01'i belgelemek; yeni yetki önerilerini açık soru olarak tutmak. | Belgelerin aynı kapsamı anlatması. | 01, 03 | Metin Efe Uğur | Yeni kapsam önerisi gelince | [ ] |
| K-02 | İptal penceresi metnini ("Randevuyu iptal et / Vazgeç") paydaşa sormak; yanıta göre 3. haftada değiştirmek. | G-04, RSK-01 | FR-03, ALT-01, S-01 | Ramazan Berat Koç | 3. hafta başı | [ ] |
| K-03 | Kalite hedefleri ölçülene kadar durumlarını "Ölçülmedi" bırakmak. | Fonksiyon denemeleri kalite ölçümü yerine geçmez. | NFR-01–03, AC-NFR | Metin Efe Uğur | Her ölçümden sonra | [ ] |
| K-04 | Her belge değişikliğini kendi dalında yapmak, `main`'e yalnız incelenmiş PR ile almak. | RSK-03, RSK-05 | 05, 09 | İhsan Kart | Her PR'de | [ ] |
| K-05 | Her deneme öncesi örnek veriyi sıfırlamak, ekran görüntülerini `kanit/` klasöründe tutmak. | RSK-02 | 08 | Ramazan Berat Koç | Her denemede | [ ] |
| K-06 | Görevleri 09'daki gibi dağıtıp bir sonraki oturumda döndürmek. | Herkes her işi öğrensin. | 09 | İhsan Kart | Sonraki oturum | [ ] |

## Açık sorular

| No | Soru | Kime | Takip eden | Durum |
|---|---|---|---|---|
| S-01 | İptal penceresi düğmeleri değişsin mi, vazgeçince mesaj çıksın mı? | Hasta | Ramazan Berat Koç | Açık |
| S-02 | Resepsiyon iptal yapabilmeli mi? | Resepsiyon / yönetim | İhsan Kart | Açık |
| S-03 | Tamamlandı işaretini kim koymalı? | Doktor | Metin Efe Uğur | Açık |
| S-04 | Kayıtlar farklı cihazlarda ortak görünmeli mi? | Klinik yönetimi | İhsan Kart | Açık |

## Sonraki küçük hedef

GitHub grup deposunu açmak, 6 issue kartını oluşturmak ve en az bir belgeyi dal + PR + arkadaş incelemesi akışıyla `main`'e almak. Ardından 05'teki Issue/PR sütunlarını gerçek bağlantılarla doldurmak.

## Ders testi kaydı

Her üye `ders-testi.html` dosyasını kendisi çözer. İlk deneme sonucunu aşağıya yazar. (Yanıtlar kaydedilmez, sayfa yenilenince silinir.)

| Üye | Tarih | İlk deneme doğru sayısı (/6) | Yanlış yapılan soru ve öğrendiğimiz |
|---|---|---|---|
| İhsan Kart | [ ] | [ ] | [ ] |
| Metin Efe Uğur | [ ] | [ ] | [ ] |
| Ramazan Berat Koç | [ ] | [ ] | [ ] |
