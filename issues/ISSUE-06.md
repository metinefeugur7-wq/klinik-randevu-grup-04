# FR-06: günlük toplamlar gereksinimini ve kabul koşullarını belgele

Bu metni GitHub Issue gövdesine kopyalayın; başlığı yukarıdaki satırdan alın.

## Amaç ve kullanıcı ihtiyacı

Resepsiyon ve doktor günü sayılarla hızlıca okumak ister.

## Prototipte gözlemlediğimiz

- Rol, hasta, doktor, tarih: Resepsiyon / Deniz Arı / 13.11.2030; Hasta / Ece / Selin Kaya
- Uygulanan adımlar: 13 Kasım'da toplamlar okundu; Hasta rolünde B3 incelendi.
- Gerçek gözlem: 13 Kasım: 1/0/0/1 (G-09). Her işlemde sayılar değişti (G-02, G-07). Hasta rolünde sayılar gizli (G-06).
- Belirsiz nokta / paydaş sorusu: Toplamlar başka günler için de gerekli mi?

## Gereksinim taslağı

Sistem, Resepsiyon ve Doktor rollerinde seçili doktor ve tarih için bekleyen, tamamlanan, iptal edilen ve toplam sayıları göstermeli, her işlemde güncellemeli, Hasta rolünde gizlemelidir.

## Kabul koşulları

- Verilen: Resepsiyon, Deniz Arı, 13 Kasım.
- Ne zaman: B3 incelenir.
- O zaman: 1 bekleyen, 0 tamamlanan, 0 iptal, toplam 1 (AC-06).
- Alternatif / reddedilen işlem: Hasta rolünde sayılar görünmez (AC-08).

## Görevler

- [x] Gözlemi docs/08-prototip-gozlemleri.md içine yaz.
- [x] FR-06 satırını docs/03-gereksinimler.md içinde tamamla.
- [x] Kabul koşulunu docs/04-kabul-kriterleri.md içinde tamamla.
- [x] İlgili kimlikleri docs/05-izlenebilirlik.md ile bağla.
- [ ] Belge değişikliğini kısa bir dalda commit et.
- [ ] Pull request aç; arkadaşından belirli bir konu için inceleme iste.
- [ ] İnceleme sonucunu işle; tamamlanma ölçütünü kontrol et.

## Takip

- Sorumlu: Ramazan Berat Koç (Üye 3)
- İnceleyen: İhsan Kart (Üye 1)
- Öncelik ve gerekçe: Orta — aynı bilgi listede de var.
- Hedef tarih: [ ]
- İlgili FR/BR: FR-06
- Bağımlılık: ISSUE-02, ISSUE-03, ISSUE-05 (sayıları değiştiren işlemler)
- Belge bağlantısı: docs/03-gereksinimler.md, docs/04-kabul-kriterleri.md, docs/08-prototip-gozlemleri.md
- Pull request bağlantısı: [PR açılınca eklenecek]

## Tamamlandı ölçütü

FR-06 satırı 03'te, kabul koşulu 04'te ve bağlantısı 05'te birbiriyle aynı davranışı anlatıyor; dayandığı gözlem 08'de ekran görüntüsüyle var; İhsan Kart (Üye 1) PR üzerinde 03–04–08'i karşılaştıran yazılı inceleme yaptı ve bulgular düzeltildi; PR `main`e birleştirildi ve bağlantısı 05'e eklendi.
