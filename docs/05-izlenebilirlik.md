# 05 — İzlenebilirlik

Ekip: Grup 04 — İhsan Kart, Metin Efe Uğur, Ramazan Berat Koç  
Sürüm: 0.3 — 19.11.2026 (PR numaraları eklendi)  
Hazırlayan: Metin Efe Uğur · İnceleyen: Ramazan Berat Koç

GitHub Issue sütunu, depoda açılan gerçek issue numaralarıyla dolduruldu (19.11.2026). Pull request sütununda, o issue'nun sahibinin açıp arkadaş incelemesinden sonra birleştirdiği PR yer alır (#7, #8, #9).

| Kullanıcı ihtiyacı | Gereksinim | Kabul koşulu | Gözlem kanıtı | GitHub Issue | İlgili dosya | Pull request |
|---|---|---|---|---|---|---|
| Hasta ve resepsiyon boş saati görmek ister. | FR-01 | AC-01 | G-01, G-07, G-09 | #5 | docs/03, docs/04, issues/ISSUE-01.md | #9 |
| Hasta / resepsiyon uygun saate randevu açmak ister; aynı saate çift kayıt olmamalı. | FR-02, BR-01 | AC-02, AC-07, AC-08 | G-02, G-03, G-07 | #3 | docs/03, docs/04, issues/ISSUE-02.md | #8 |
| Hasta planı değişince randevusunu iptal etmek, yanlışlıkla iptal etmemek ister. | FR-03 | AC-03, ALT-01 | G-04, G-05, G-06 | #1 | docs/03, docs/04, docs/06 (RSK-01), issues/ISSUE-03.md | #7 |
| Resepsiyon ve doktor günün bütün randevularını görmek ister. | FR-04 | AC-04 | G-07, G-08, G-09 | #6 | docs/03, docs/04, issues/ISSUE-04.md | #9 |
| Doktor biten muayeneyi ayırmak ister. | FR-05 | AC-05 | G-07 | #4 | docs/03, docs/04, issues/ISSUE-05.md | #8 |
| Resepsiyon ve doktor günü sayılarla hızlı okumak ister. | FR-06 | AC-06, AC-08 | G-02, G-06, G-07, G-08, G-09 | #2 | docs/03, docs/04, issues/ISSUE-06.md | #7 |

## Kalite gereksinimleri

| Gereksinim | Kabul kontrolü | İlgili risk | Durum |
|---|---|---|---|
| NFR-01 Kullanılabilirlik | AC-NFR-01 | RSK-01 | Ölçülmedi |
| NFR-02 Yanıt süresi | AC-NFR-02 | — | Ölçülmedi |
| NFR-03 Klavyeyle kullanım | AC-NFR-03 | — | Ölçülmedi |

## Kontrol

- [x] Her FR için en az bir kabul koşulu var.
- [x] Kart (issues/) ile belge (03, 04) aynı davranışı anlatıyor. Kartlardaki FR, AC ve G kimlikleri bu tabloyla aynı.
- [x] Issue numaraları gerçek kayıtlarla eşleşiyor (#1–#6). Oluşmamış PR bağlantıları boş bırakıldı.
- [x] İlgili değişiklikler arkadaş incelemesinden geçti (19.11.2026): #7 → İhsan Kart, #8 → Ramazan Berat Koç, #9 → Metin Efe Uğur onayladı.
