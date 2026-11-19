# FR-02: randevu oluşturma gereksinimini ve kabul koşullarını belgele

Bu metni GitHub Issue gövdesine kopyalayın; başlığı yukarıdaki satırdan alın.

## Amaç ve kullanıcı ihtiyacı

Hasta kendi adına, resepsiyon ise telefonla arayan hasta adına uygun saate randevu açmak ister. Aynı saate çift kayıt olmamalı.

## Prototipte gözlemlediğimiz

- Rol, hasta, doktor, tarih: Resepsiyon / Kaan Demir / Selin Kaya / 12.11.2030
- Uygulanan adımlar: 14:00 seçildi, Randevuyu onayla'ya basıldı. Ardından Hasta Ece ile aynı saate tıklanmaya çalışıldı.
- Gerçek gözlem: R008 Kaan adına Bekliyor oluştu, 14:00 Dolu, toplamlar 1/1/0/2 → 2/1/0/3 (G-02). Ece seçiliyken 14:00 seçilemedi (G-03).
- Belirsiz nokta / paydaş sorusu: Doktorun kendi hastasına kontrol randevusu vermesi gerekir mi?

## Gereksinim taslağı

Sistem, Hasta veya Resepsiyon rolünde Uygun saat seçilip onaylanınca seçili hasta, doktor, tarih ve saatle Bekliyor kayıt oluşturmalı; BR-01'e aykırı kayıt oluşturmamalıdır.

## Kabul koşulları

- Verilen: Resepsiyon, Kaan, Selin Kaya, 12 Kasım; 14:00 Uygun.
- Ne zaman: 14:00 seçilip onaylanır.
- O zaman: Kaan adına Bekliyor kayıt; 14:00 Dolu; toplamlar 2/1/0/3 (AC-02).
- Alternatif / reddedilen işlem: Dolu saate tıklanınca kayıt oluşmaz (AC-07); Doktor rolünde onay düğmesi pasif (AC-08).

## Görevler

- [x] Gözlemi docs/08-prototip-gozlemleri.md içine yaz.
- [x] FR-02 satırını docs/03-gereksinimler.md içinde tamamla.
- [x] Kabul koşulunu docs/04-kabul-kriterleri.md içinde tamamla.
- [x] İlgili kimlikleri docs/05-izlenebilirlik.md ile bağla.
- [ ] Belge değişikliğini kısa bir dalda commit et.
- [ ] Pull request aç; arkadaşından belirli bir konu için inceleme iste.
- [ ] İnceleme sonucunu işle; tamamlanma ölçütünü kontrol et.

## Takip

- Sorumlu: Metin Efe Uğur (Üye 2)
- İnceleyen: Ramazan Berat Koç (Üye 3)
- Öncelik ve gerekçe: Yüksek — ürünün ana işi.
- Hedef tarih: [ ]
- İlgili FR/BR: FR-02, BR-01
- Bağımlılık: ISSUE-01 (saat durumları)
- Belge bağlantısı: docs/03-gereksinimler.md, docs/04-kabul-kriterleri.md, docs/08-prototip-gozlemleri.md
- Pull request bağlantısı: [PR açılınca eklenecek]

## Tamamlandı ölçütü

FR-02 satırı 03'te, kabul koşulu 04'te ve bağlantısı 05'te birbiriyle aynı davranışı anlatıyor; dayandığı gözlem 08'de ekran görüntüsüyle var; Ramazan Berat Koç (Üye 3) PR üzerinde 03–04–08'i karşılaştıran yazılı inceleme yaptı ve bulgular düzeltildi; PR `main`e birleştirildi ve bağlantısı 05'e eklendi.
