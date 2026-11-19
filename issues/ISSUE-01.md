# FR-01: uygun saat gereksinimini ve kabul koşullarını belgele

Bu metni GitHub Issue gövdesine kopyalayın; başlığı yukarıdaki satırdan alın.

## Amaç ve kullanıcı ihtiyacı

Hasta ve resepsiyon, seçili doktorun o gün hangi saatlerinin boş olduğunu görmek ister. Dolu veya tamamlanmış saate yönelmemek için saat durumu açık olmalı.

## Prototipte gözlemlediğimiz

- Rol, hasta, doktor, tarih: Hasta / Kaan Demir / Selin Kaya / 12.11.2030 (ayrıca Doktor rolü ve 13.11.2030)
- Uygulanan adımlar: Doktor Deniz Arı → Selin Kaya değiştirildi; Doktor rolünde saatlere bakıldı; tarih 13 Kasım yapıldı.
- Gerçek gözlem: Selin Kaya'da 09:30 Dolu, 11:00 Kapalı, diğerleri Uygun (G-01). Doktor rolünde bütün saatler pasif (G-07). 13 Kasım Deniz Arı'da yalnız 10:30 Dolu (G-09).
- Belirsiz nokta / paydaş sorusu: Doktor rolünde boş saatler "Uygun" yazıyor ama seçilemiyor; bu yanıltıcı mı?

## Gereksinim taslağı

Sistem, seçili doktor ve tarihin 10 sabit saatini Uygun / Dolu / Kapalı olarak göstermeli ve doktor veya tarih değişince güncellemelidir.

## Kabul koşulları

- Verilen: Hasta rolü, veri sıfırlanmış, Deniz Arı, 12 Kasım.
- Ne zaman: Doktor Selin Kaya seçilir.
- O zaman: 09:30 Dolu, 11:00 Kapalı, diğer sekiz saat Uygun (AC-01).
- Alternatif / reddedilen işlem: Doktor rolünde saatler seçilemez (AC-08).

## Görevler

- [x] Gözlemi docs/08-prototip-gozlemleri.md içine yaz.
- [x] FR-01 satırını docs/03-gereksinimler.md içinde tamamla.
- [x] Kabul koşulunu docs/04-kabul-kriterleri.md içinde tamamla.
- [x] İlgili kimlikleri docs/05-izlenebilirlik.md ile bağla.
- [ ] Belge değişikliğini kısa bir dalda commit et.
- [ ] Pull request aç; arkadaşından belirli bir konu için inceleme iste.
- [ ] İnceleme sonucunu işle; tamamlanma ölçütünü kontrol et.

## Takip

- Sorumlu: İhsan Kart (Üye 1)
- İnceleyen: Metin Efe Uğur (Üye 2)
- Öncelik ve gerekçe: Yüksek — boş saati bilmeden randevu alınamaz.
- Hedef tarih: [ ]
- İlgili FR/BR: FR-01, BR-01
- Bağımlılık: Yok
- Belge bağlantısı: docs/03-gereksinimler.md, docs/04-kabul-kriterleri.md, docs/08-prototip-gozlemleri.md
- Pull request bağlantısı: [PR açılınca eklenecek]

## Tamamlandı ölçütü

FR-01 satırı 03'te, kabul koşulu 04'te ve bağlantısı 05'te birbiriyle aynı davranışı anlatıyor; dayandığı gözlem 08'de ekran görüntüsüyle var; Metin Efe Uğur (Üye 2) PR üzerinde 03–04–08'i karşılaştıran yazılı inceleme yaptı ve bulgular düzeltildi; PR `main`e birleştirildi ve bağlantısı 05'e eklendi.
