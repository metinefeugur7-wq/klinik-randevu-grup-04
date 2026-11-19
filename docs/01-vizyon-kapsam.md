# 01 — Vizyon ve kapsam

Ekip: Grup 04 — İhsan Kart, Metin Efe Uğur, Ramazan Berat Koç  
Tarih: 19.11.2026  
Sürüm: 0.1  
Hazırlayan: İhsan Kart · İnceleyen: Metin Efe Uğur (inceleme henüz yapılmadı)  
İlgili issue: #5, #6  

Durum: Taslak. Paydaş görüşmesi yapılmadı; problem ve kapsam ders senaryosuna dayanıyor.

## Problem

Küçük bir klinikte randevular telefonla ve kâğıt üzerinde tutulduğunda üç sorun çıkıyor:

- Hasta, doktorun hangi saatlerinin boş olduğunu öğrenmek için kliniği aramak zorunda kalıyor.
- Aynı doktora aynı saat için iki farklı hastaya randevu verilebiliyor.
- Resepsiyon ve doktor, gün içinde hangi muayenenin beklediğini, hangisinin bittiğini ve hangisinin iptal edildiğini tek bakışta göremiyor.

Bu problem gerçek bir klinikten alınmadı. Ders için kurgulanmış bir senaryodur.

## Vizyon

**Hastanın boş saati kendisi görüp randevu alabildiği; resepsiyon ve doktorun o günün randevu durumunu tek ekranda takip edebildiği, aynı saate çift kayıt açılmayan basit bir randevu sistemi.**

| Kullanıcı | Sistemden kazancı |
|---|---|
| Hasta | Uygun saati kendi görür ve randevu alır. Planı değişirse bekleyen randevusunu iptal eder. |
| Resepsiyon | Telefonla arayan hasta adına randevu açar. Doktorun o günkü listesini ve sayılarını izler. |
| Doktor | Günün bekleyen hastalarını görür. Biten muayeneyi "Tamamlandı" yaparak listeyi güncel tutar. |

Zaman kazancı veya hata azalması gibi etkileri ölçmedik. Bunlar beklenen faydadır, ölçülmüş sonuç değildir.

## Kapsam içinde (v0.1)

| Kimlik | İşlev | Kısa açıklama |
|---|---|---|
| FR-01 | Uygun saatleri listeleme | Seçili doktor ve tarihin saatleri Uygun / Dolu / Kapalı olarak gösterilir. |
| FR-02 | Randevu oluşturma | Hasta veya Resepsiyon, uygun saati seçip onaylayınca Bekliyor durumunda kayıt oluşur. |
| FR-03 | Kendi randevusunu iptal etme | Hasta yalnız kendi Bekliyor kaydını onay vererek iptal eder. Vazgeçerse kayıt korunur. |
| FR-04 | Günlük liste | Resepsiyon ve Doktor, seçili doktor ve tarihin bütün kayıtlarını görür. |
| FR-05 | Randevuyu tamamlama | Doktor, görevli olduğu günün Bekliyor kaydını Tamamlandı yapar. |
| FR-06 | Günlük toplamlar | Resepsiyon ve Doktor; bekleyen, tamamlanan, iptal edilen ve toplam sayıyı görür. |

**BR-01 (iş kuralı):** Aynı doktor, tarih ve saat için iptal edilmemiş ikinci randevu açılamaz. Bekliyor kaydı saati Dolu, Tamamlandı kaydı Kapalı yapar. İptal edilen kayıt saati serbest bırakır ama listede kalır.

**Çalışma ortamı:** 2 örnek hasta (Ece Yılmaz, Kaan Demir), 2 örnek doktor (Deniz Arı, Selin Kaya), 12–13 Kasım 2030 ve 10 sabit saat kullanılır. Veriler yalnız açılan tarayıcıda tutulur.

## Kapsam dışında

- Gerçek kullanıcı girişi, parola ve sunucu tarafı yetki kontrolü. Rol seçimi yalnız canlandırmadır.
- Ortak veritabanı, farklı cihaz ve sekmeler arasında eşzamanlama.
- SMS / e-posta hatırlatma, ödeme, gerçek hasta veya sağlık bilgisi.
- Doktor çalışma takvimi, tatil, farklı randevu süreleri, geçmiş saat engeli, randevu taşıma ve arama.
- Resepsiyonun iptal veya tamamlama yapması, doktorun randevu oluşturması.
- Tamamlanan kaydı iptal etmek, iptal edilen kaydı geri almak.
- Birden çok günü veya bütün kliniği kapsayan rapor.
- C#/Java MVC uygulaması, otomatik test ve CI/CD (sonraki haftalara bırakıldı).

## Başarıyı nasıl gözleyeceğiz?

Kanıtlar `08-prototip-gozlemleri.md` dosyasındaki 19.11.2026 tarihli denememize dayanıyor.

| Kullanıcı amacı | Gözlenebilir kanıt | Durum |
|---|---|---|
| Resepsiyon, hasta adına randevu açar. | G-02: Kaan için 14:00'te R008 Bekliyor oluştu. 14:00 Dolu oldu, toplam 2'den 3'e çıktı. | Gözlendi |
| Hasta dolu saate randevu alamaz. | G-03: Ece seçiliyken Kaan'a ait 14:00 seçilemedi, kayıt oluşmadı. | Gözlendi |
| Hasta iptalden vazgeçebilir veya iptal edebilir. | G-04: Vazgeçince R008 Bekliyor kaldı. G-05: Onaylayınca İptal edildi oldu, 14:00 Uygun oldu. | Gözlendi |
| Doktor muayeneyi tamamlar. | G-07: R005 Tamamlandı oldu, 09:30 Kapalı oldu, bekleyen 1'den 0'a indi. | Gözlendi |
| Resepsiyon günlük durumu izler. | G-08: Üç kayıt düğmesiz göründü, toplamlar doktorla aynı (0/2/1/3). | Gözlendi |
| Yenilemeden sonra kayıtlar kaybolmaz. | G-10: Aynı tarayıcıda yenileme sonrası durumlar ve toplamlar aynı kaldı. | Gözlendi (yalnız aynı tarayıcıda) |
| Kullanıcılar iptal/vazgeç ayrımını yardımsız yapar. | NFR-01 ölçümü. | Ölçülmedi |

## Varsayımlar ve açık sorular

- **Varsayım:** Prototipteki rol yetkileri, paydaşla konuşulacak başlangıç noktasıdır; onaylanmış kural değildir.
- **Varsayım:** Bir randevu tek bir sabit süreli saat dilimini kaplar.
- **Soru 1:** Resepsiyon, telefonla arayan hasta için randevu iptal edebilmeli mi? (G-02, G-08)
- **Soru 2:** İptal penceresindeki "Tamam / İptal" düğmeleri "Randevuyu iptal et / Vazgeç" olarak değiştirilsin mi? (G-04)
- **Soru 3:** Kayıtların farklı cihazlarda ortak görünmesi gerekiyor mu? (G-10)

Yanıtlar alındığında `07-toplanti-notu.md` dosyasına, kapsam değişikliği varsa bu belgenin yeni sürümüne yazılacak.
