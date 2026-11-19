# Diyagram notları

Tarih: 19.11.2026 · Sürüm 0.1

| Dosya | Ne için | Takip eden | Kontrol eden |
|---|---|---|---|
| 01-baglam.drawio / .png | Sistemi tek kutu olarak, üç rolün sisteme ne gönderdiğini ve ne aldığını gösterir (6 ok). | İhsan Kart | Metin Efe Uğur |
| 02-kullanim-durumlari.drawio / .png | Hangi rolün hangi işlevi (FR) kullandığını gösterir. | Metin Efe Uğur | Ramazan Berat Koç |

`.drawio` dosyaları https://app.diagrams.net/ adresinde **Dosya → Şuradan aç → Cihaz** ile açılıp düzenlenebilir. `.png` dosyaları sunum ve rapor içindir. Çizim değişirse PNG de yeniden dışa aktarılmalıdır.

## Gereksinimlerle karşılaştırma

| Rol | Kullanım durumu bağlantıları | 03'teki dayanak |
|---|---|---|
| Hasta (3) | FR-01, FR-02, FR-03 | Hasta liste/toplam görmez, tamamlama yapmaz. |
| Resepsiyon (4) | FR-01, FR-02, FR-04, FR-06 | İptal ve tamamlama yok (G-08). |
| Doktor (4) | FR-01, FR-04, FR-05, FR-06 | Randevu oluşturmaz (G-07). |

Toplam 11 bağlantı vardır. Bağlam diyagramındaki ok etiketleri de aynı FR'lere işaret eder.

## Kontrol listesi

- [x] Üç rol ve bir sistem kutusu doğru adlandırıldı.
- [x] Her rol için "istek" (yeşil) ve "sonuç" (mavi) okları ayrı.
- [x] Kullanım durumu bağlantıları 03'teki aktör/koşul sütunuyla aynı.
- [ ] .drawio dosyası diagrams.net'te açılıp kaydedildi ve yeniden açıldı. → [ad, tarih]
- [ ] Çizen dışındaki üye rol ve okları kontrol etti. → [ad, tarih, not]
