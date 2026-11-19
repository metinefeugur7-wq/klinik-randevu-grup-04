# 05 — İzlenebilirlik

Ekip: Grup 04 — İhsan Kart, Metin Efe Uğur, Ramazan Berat Koç  
Sürüm: 0.1 — 19.11.2026  
Hazırlayan: Metin Efe Uğur · İnceleyen: Ramazan Berat Koç

GitHub Issue ve Pull request sütunları, kayıtlar **gerçekten açıldıktan sonra** doldurulacak. O zamana kadar "—" bırakıyoruz.

| Kullanıcı ihtiyacı | Gereksinim | Kabul koşulu | Gözlem kanıtı | GitHub Issue | İlgili dosya | Pull request |
|---|---|---|---|---|---|---|
| Hasta ve resepsiyon boş saati görmek ister. | FR-01 | AC-01 | G-01, G-07, G-09 | — | docs/03, docs/04, issues/ISSUE-01.md | — |
| Hasta / resepsiyon uygun saate randevu açmak ister; aynı saate çift kayıt olmamalı. | FR-02, BR-01 | AC-02, AC-07, AC-08 | G-02, G-03, G-07 | — | docs/03, docs/04, issues/ISSUE-02.md | — |
| Hasta planı değişince randevusunu iptal etmek, yanlışlıkla iptal etmemek ister. | FR-03 | AC-03, ALT-01 | G-04, G-05, G-06 | — | docs/03, docs/04, docs/06 (RSK-01), issues/ISSUE-03.md | — |
| Resepsiyon ve doktor günün bütün randevularını görmek ister. | FR-04 | AC-04 | G-07, G-08, G-09 | — | docs/03, docs/04, issues/ISSUE-04.md | — |
| Doktor biten muayeneyi ayırmak ister. | FR-05 | AC-05 | G-07 | — | docs/03, docs/04, issues/ISSUE-05.md | — |
| Resepsiyon ve doktor günü sayılarla hızlı okumak ister. | FR-06 | AC-06, AC-08 | G-02, G-06, G-07, G-08, G-09 | — | docs/03, docs/04, issues/ISSUE-06.md | — |

## Kalite gereksinimleri

| Gereksinim | Kabul kontrolü | İlgili risk | Durum |
|---|---|---|---|
| NFR-01 Kullanılabilirlik | AC-NFR-01 | RSK-01 | Ölçülmedi |
| NFR-02 Yanıt süresi | AC-NFR-02 | — | Ölçülmedi |
| NFR-03 Klavyeyle kullanım | AC-NFR-03 | — | Ölçülmedi |

## Kontrol

- [x] Her FR için en az bir kabul koşulu var.
- [x] Kart (issues/) ile belge (03, 04) aynı davranışı anlatıyor. Kartlardaki FR, AC ve G kimlikleri bu tabloyla aynı.
- [x] Oluşmamış bağlantılar (Issue, PR) boş bırakıldı.
- [ ] İlgili değişiklik arkadaş incelemesinden geçti. → İnceleyen: [ ], tarih: [ ]
