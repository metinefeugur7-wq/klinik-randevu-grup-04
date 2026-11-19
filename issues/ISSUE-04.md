# FR-04: günlük liste gereksinimini ve kabul koşullarını belgele

Bu metni GitHub Issue gövdesine kopyalayın; başlığı yukarıdaki satırdan alın.

## Amaç ve kullanıcı ihtiyacı

Resepsiyon ve doktor, seçili doktorun o günkü bütün randevularını ve durumlarını görmek ister.

## Prototipte gözlemlediğimiz

- Rol, hasta, doktor, tarih: Resepsiyon / Kaan Demir / Selin Kaya / 12.11.2030; Doktor / Selin Kaya
- Uygulanan adımlar: Resepsiyon ve Doktor rollerinde günlük liste incelendi; tarih 13 Kasım yapıldı.
- Gerçek gözlem: Hasta seçimi Kaan iken Ece'nin R005 kaydı da listede; işlem düğmesi yok (G-08). Doktorda üç kayıt birlikte (G-07). 13 Kasım'da yalnız R007 (G-09).
- Belirsiz nokta / paydaş sorusu: Hasta, başka hastanın dolu saatini hiç görmemeli mi?

## Gereksinim taslağı

Sistem, Resepsiyon ve Doktor rollerinde seçili doktor ve tarihin bütün kayıtlarını saat sırasıyla ve durum etiketiyle göstermeli; resepsiyondaki hasta seçimi listeyi daraltmamalıdır.

## Kabul koşulları

- Verilen: Resepsiyon, örnek hasta Kaan, Selin Kaya, 12 Kasım.
- Ne zaman: Günlük liste incelenir.
- O zaman: Ece ve Kaan'ın kayıtları birlikte görünür; işlem düğmesi yoktur (AC-04).
- Alternatif / reddedilen işlem: Hasta rolünde yalnız kendi kayıtları görünür (G-06).

## Görevler

- [x] Gözlemi docs/08-prototip-gozlemleri.md içine yaz.
- [x] FR-04 satırını docs/03-gereksinimler.md içinde tamamla.
- [x] Kabul koşulunu docs/04-kabul-kriterleri.md içinde tamamla.
- [x] İlgili kimlikleri docs/05-izlenebilirlik.md ile bağla.
- [ ] Belge değişikliğini kısa bir dalda commit et.
- [ ] Pull request aç; arkadaşından belirli bir konu için inceleme iste.
- [ ] İnceleme sonucunu işle; tamamlanma ölçütünü kontrol et.

## Takip

- Sorumlu: İhsan Kart (Üye 1)
- İnceleyen: Metin Efe Uğur (Üye 2)
- Öncelik ve gerekçe: Yüksek — günlük takip.
- Hedef tarih: [ ]
- İlgili FR/BR: FR-04
- Bağımlılık: Yok
- Belge bağlantısı: docs/03-gereksinimler.md, docs/04-kabul-kriterleri.md, docs/08-prototip-gozlemleri.md
- Pull request bağlantısı: [PR açılınca eklenecek]

## Tamamlandı ölçütü

FR-04 satırı 03'te, kabul koşulu 04'te ve bağlantısı 05'te birbiriyle aynı davranışı anlatıyor; dayandığı gözlem 08'de ekran görüntüsüyle var; Metin Efe Uğur (Üye 2) PR üzerinde 03–04–08'i karşılaştıran yazılı inceleme yaptı ve bulgular düzeltildi; PR `main`e birleştirildi ve bağlantısı 05'e eklendi.
