# 02 — Paydaşlar, ihtiyaçlar ve sorular

Ekip: Grup 04 — İhsan Kart, Metin Efe Uğur, Ramazan Berat Koç  
Tarih: 19.11.2026  
Sürüm: 0.1  
Hazırlayan: İhsan Kart · İnceleyen: Metin Efe Uğur (inceleme henüz yapılmadı)  
Durum: Taslak. Gerçek paydaş görüşmesi yapılmadı. İhtiyaçlar senaryodan ve prototip gözlemlerimizden çıkarıldı.

## Paydaşlar ve ihtiyaçları

| Paydaş | Sistemden beklediği | Soracağımız soru | Doğrulanmamış varsayım |
|---|---|---|---|
| Hasta | Boş saati görüp randevu almak, randevusunun durumunu izlemek, gerekirse iptal etmek. | İptal penceresinde "Tamam / İptal" yerine "Randevuyu iptal et / Vazgeç" yazsa daha anlaşılır olur mu? | Hastanın kendi randevusunu iptal etmek istediğini ve mevcut düğme adlarının kafa karıştırdığını varsayıyoruz (G-04). |
| Resepsiyon | Telefonla arayan hasta adına randevu açmak, doktorun günlük listesini ve sayılarını izlemek. | Hasta telefonla iptal isterse bu işlemi siz yapabilmeli misiniz? Hangi durumlarda? | Resepsiyonun kayıt açma ihtiyacı var (G-02). İptal yetkisinin gerekip gerekmediğini bilmiyoruz (G-08). |
| Doktor | Günün bekleyen hastalarını görmek, biten muayeneyi işaretlemek. | Muayene bitince "Tamamlandı" işaretini siz mi koyarsınız, yoksa resepsiyon mu? | Tamamlama bilgisini doktorun kendisinin gireceğini varsayıyoruz (G-07). |
| Klinik yönetimi (ek paydaş) | Rollerin ve yetkilerin net olması, çift randevu olmaması, kayıtların güvenilir tutulması. | Kayıtlar farklı cihazlardan ortak görülmeli mi? Bir değişiklik diğer kullanıcılara ne kadar sürede yansımalı? | Yetki ve ortak veri kararını yönetimin vereceğini varsayıyoruz. Prototipte yönetici ekranı yok. |

**Klinik yönetimini neden ekledik?** Rol yetkileri ve ortak veri gibi kararlar birden çok kullanıcıyı etkiliyor. Bu kararları verecek kişi uygulamayı doğrudan kullanmasa da paydaştır. Bu ekleme prototipe yeni bir rol veya ekran eklemiyor.

**Paydaş ile ekip görevi farklıdır:** Hasta, resepsiyon, doktor ve yönetim ürünün paydaşlarıdır. Belge yazmak, test etmek veya incelemek ise ekip üyelerinin görevidir (`09-ekip-rolleri.md`).

## Rol ve işlem tablosu

Bu tablo **prototipte gördüğümüzü** gösterir; onaylanmış yetki tasarımı değildir. G-… kodları `08-prototip-gozlemleri.md` satırlarıdır.

| İşlem | Hasta | Resepsiyon | Doktor | Paydaşa sorulacak nokta |
|---|---|---|---|---|
| Uygun saatleri görme | Evet (G-01) | Evet (G-02) | Evet, ama saat seçemez (G-07) | Doktor rolünde boş saatlerin "Uygun" yazması yanıltıcı mı? |
| Randevu oluşturma | Evet, kendi adına | Evet, seçili hasta adına (G-02) | Hayır, onay düğmesi pasif (G-07) | Doktorun kendi hastasına kontrol randevusu vermesi gerekir mi? |
| İptal etme | Yalnız kendi Bekliyor kaydı, onayla (G-04, G-05) | Hayır, düğme yok (G-08) | Hayır, düğme yok (G-07) | Resepsiyon iptal edebilmeli mi? |
| Liste görme | Yalnız kendi kayıtları (G-06) | Seçili doktor + günün bütün kayıtları (G-08) | Seçili doktor + günün bütün kayıtları (G-07) | Hasta başka hastanın dolu saatini hiç görmemeli mi? |
| Tamamlandı yapma | Hayır | Hayır (G-08) | Evet, Bekliyor kayıt için (G-07) | Tamamlamayı kim, ne zaman girmeli? |
| Günlük toplamlar | Hayır, gizli (G-06) | Evet (G-08) | Evet (G-07) | Toplamlar başka günler için de gerekli mi? |

**Dikkat ettiğimiz fark:** Resepsiyonda "Örnek hasta" seçimi, adına kayıt açılacak kişiyi belirler; listeyi daraltmaz (G-08). Hasta rolünde aynı seçim, kimin randevularının görüneceğini belirler (G-06). Doktor rolünde bu alan pasiftir (G-07).

## Görüşme planı

Gerçek görüşme yapılmadı. Aşağıdakiler görüşmede soracağımız sorular ve yanıta göre yapılacak değişikliklerdir. Yanıt sütunu görüşmeden sonra doldurulacak.

| No | Kime | Soru | Dayanak | Yanıt | Yanıt "evet" olursa etkisi |
|---|---|---|---|---|---|
| S-01 | Hasta | Onay penceresindeki düğmeler "Randevuyu iptal et / Vazgeç" olsun mu? Vazgeçince ekranda mesaj görmek ister misiniz? | G-04 | [ ] | FR-03 metni ve RSK-01 önlemi güncellenir. |
| S-02 | Resepsiyon | Hasta telefonla iptal isterse siz iptal edebilmeli misiniz? | G-02, G-08 | [ ] | FR-03'e Resepsiyon aktörü eklenir, yeni kabul koşulu yazılır. |
| S-03 | Doktor | Muayene bitince Tamamlandı işaretini kim koymalı? | G-07 | [ ] | FR-05 aktörü değişebilir. |
| S-04 | Klinik yönetimi | Kayıtlar farklı cihazlardan ortak görülmeli mi? | G-10 | [ ] | Ortak veritabanı kapsam dışından kapsam içine alınır. Sonraki haftaların MVC işi etkilenir. |
