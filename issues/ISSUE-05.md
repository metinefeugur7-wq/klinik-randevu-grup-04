# FR-05: doktorun tamamlama gereksinimini ve kabul koşullarını belgele

Bu metni GitHub Issue gövdesine kopyalayın; başlığı yukarıdaki satırdan alın.

## Amaç ve kullanıcı ihtiyacı

Doktor, biten muayeneyi bekleyenlerden ayırmak ister.

## Prototipte gözlemlediğimiz

- Rol, hasta, doktor, tarih: Doktor / Selin Kaya / 12.11.2030
- Uygulanan adımlar: R005 / 09:30 Bekliyor için Tamamlandı'ya basıldı.
- Gerçek gözlem: R005 Tamamlandı, düğmesi kalktı, 09:30 Kapalı, toplamlar 1/1/1/3 → 0/2/1/3 (G-07).
- Belirsiz nokta / paydaş sorusu: Tamamlandı işaretini doktor mu, resepsiyon mu koymalı? (S-03)

## Gereksinim taslağı

Sistem, Doktor rolünde görevli doktorun Bekliyor kaydını Tamamlandı yapabilmeli; saat Kapalı olmalı ve kayıtta yeniden tamamlama düğmesi bulunmamalıdır.

## Kabul koşulları

- Verilen: Doktor, Selin Kaya, 12 Kasım; R005 Bekliyor.
- Ne zaman: R005 için Tamamlandı.
- O zaman: R005 Tamamlandı, 09:30 Kapalı, toplamlar 0/2/1/3 (AC-05).
- Alternatif / reddedilen işlem: Resepsiyonda tamamlama düğmesi yoktur (AC-04).

## Görevler

- [x] Gözlemi docs/08-prototip-gozlemleri.md içine yaz.
- [x] FR-05 satırını docs/03-gereksinimler.md içinde tamamla.
- [x] Kabul koşulunu docs/04-kabul-kriterleri.md içinde tamamla.
- [x] İlgili kimlikleri docs/05-izlenebilirlik.md ile bağla.
- [ ] Belge değişikliğini kısa bir dalda commit et.
- [ ] Pull request aç; arkadaşından belirli bir konu için inceleme iste.
- [ ] İnceleme sonucunu işle; tamamlanma ölçütünü kontrol et.

## Takip

- Sorumlu: Metin Efe Uğur (Üye 2)
- İnceleyen: Ramazan Berat Koç (Üye 3)
- Öncelik ve gerekçe: Yüksek — bekleyen ve biten muayeneyi ayırır.
- Hedef tarih: [ ]
- İlgili FR/BR: FR-05, BR-01
- Bağımlılık: Yok
- Belge bağlantısı: docs/03-gereksinimler.md, docs/04-kabul-kriterleri.md, docs/08-prototip-gozlemleri.md
- Pull request bağlantısı: [PR açılınca eklenecek]

## Tamamlandı ölçütü

FR-05 satırı 03'te, kabul koşulu 04'te ve bağlantısı 05'te birbiriyle aynı davranışı anlatıyor; dayandığı gözlem 08'de ekran görüntüsüyle var; Ramazan Berat Koç (Üye 3) PR üzerinde 03–04–08'i karşılaştıran yazılı inceleme yaptı ve bulgular düzeltildi; PR `main`e birleştirildi ve bağlantısı 05'e eklendi.
