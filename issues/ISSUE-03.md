# FR-03: hastanın iptal gereksinimini ve kabul koşullarını belgele

Bu metni GitHub Issue gövdesine kopyalayın; başlığı yukarıdaki satırdan alın.

## Amaç ve kullanıcı ihtiyacı

Hasta planı değişince kendi bekleyen randevusunu iptal etmek ister; vazgeçerse randevusu korunmalı.

## Prototipte gözlemlediğimiz

- Rol, hasta, doktor, tarih: Hasta / Kaan Demir / Selin Kaya / 12.11.2030
- Uygulanan adımlar: R008 için İptal et → pencerede önce İptal (vazgeç), sonra tekrar İptal et → Tamam.
- Gerçek gözlem: Vazgeçince R008 Bekliyor, 14:00 Dolu kaldı; mesaj değişmedi (G-04). Onaylayınca R008 İptal edildi, listede kaldı, 14:00 Uygun oldu (G-05).
- Belirsiz nokta / paydaş sorusu: Pencere düğmeleri "Randevuyu iptal et / Vazgeç" olsun mu? (S-01, RSK-01)

## Gereksinim taslağı

Sistem, Hasta rolünde yalnız seçili hastanın kendi Bekliyor kaydı için onaylı iptal sunmalı; onaylanırsa kaydı İptal edildi yapıp saati açmalı, vazgeçilirse hiçbir şeyi değiştirmemelidir.

## Kabul koşulları

- Verilen: Hasta, Kaan, Selin Kaya; Kaan'ın 14:00 kaydı Bekliyor.
- Ne zaman: İptal et → Tamam.
- O zaman: Kayıt İptal edildi, listede kalır, 14:00 Uygun (AC-03).
- Alternatif / reddedilen işlem: Pencerede İptal seçilirse kayıt Bekliyor kalır (ALT-01).

## Görevler

- [x] Gözlemi docs/08-prototip-gozlemleri.md içine yaz.
- [x] FR-03 satırını docs/03-gereksinimler.md içinde tamamla.
- [x] Kabul koşulunu docs/04-kabul-kriterleri.md içinde tamamla.
- [x] İlgili kimlikleri docs/05-izlenebilirlik.md ile bağla.
- [ ] Belge değişikliğini kısa bir dalda commit et.
- [ ] Pull request aç; arkadaşından belirli bir konu için inceleme iste.
- [ ] İnceleme sonucunu işle; tamamlanma ölçütünü kontrol et.

## Takip

- Sorumlu: Ramazan Berat Koç (Üye 3)
- İnceleyen: İhsan Kart (Üye 1)
- Öncelik ve gerekçe: Yüksek — yanlışlıkla iptal riski var (RSK-01).
- Hedef tarih: [ ]
- İlgili FR/BR: FR-03, BR-01
- Bağımlılık: ISSUE-02 (iptal edilecek kayıt için)
- Belge bağlantısı: docs/03-gereksinimler.md, docs/04-kabul-kriterleri.md, docs/08-prototip-gozlemleri.md
- Pull request bağlantısı: [PR açılınca eklenecek]

## Tamamlandı ölçütü

FR-03 satırı 03'te, kabul koşulu 04'te ve bağlantısı 05'te birbiriyle aynı davranışı anlatıyor; dayandığı gözlem 08'de ekran görüntüsüyle var; İhsan Kart (Üye 1) PR üzerinde 03–04–08'i karşılaştıran yazılı inceleme yaptı ve bulgular düzeltildi; PR `main`e birleştirildi ve bağlantısı 05'e eklendi.
