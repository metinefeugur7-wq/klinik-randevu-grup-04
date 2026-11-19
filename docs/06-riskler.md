# 06 — Riskler

Ekip: Grup 04 — İhsan Kart, Metin Efe Uğur, Ramazan Berat Koç  
Tarih: 19.11.2026  
Sürüm: 0.1  
Hazırlayan: Ramazan Berat Koç · İnceleyen: İhsan Kart (inceleme henüz yapılmadı)  
Kapsam: Klinik Randevu prototipi ve 1–2. hafta ekip çalışması

Risk, **henüz olmamış** ama olursa projeyi veya ders çalışmasını olumsuz etkileyecek durumdur. Olmuş bir şey gözlemdir ve 08'e yazılır. RSK-… kimlikleri risk numarasıdır, R008 gibi randevu numaralarıyla karıştırılmamalıdır.

Olasılık ve etki, düşük / orta / yüksek olarak verdiğimiz **nitel tahminlerdir**; ölçülmüş değer değildir.

## Risk listesi

| Kimlik | Risk ve nedeni | Olasılık | Etki | Erken işaret | Önlem | Sorumlu |
|---|---|---|---|---|---|---|
| RSK-01 | **Yanlışlıkla iptal:** Karttaki "İptal et" ile onay penceresindeki "İptal" ters anlamda. Vazgeçen kullanıcı yanlış düğmeye basıp randevusunu kaybedebilir. Vazgeçince mesaj çıkmadığı için ne olduğunu da anlamayabilir (G-04). | Orta — biz denemede doğru düğmeyi bilerek seçtik, yeni kullanıcıyla denemedik. | Yüksek — randevu iptal olur, saat başkasına açılır. | Kullanıcının "hangisine basayım?" diye sorması; vazgeçme görevinde Tamam'a basması. | Düğme metnini "Randevuyu iptal et / Vazgeç" yapmayı paydaşa önermek (S-01). Vazgeçince bilgi mesajı göstermek. NFR-01 ölçümünü yapmak. | Ramazan Berat Koç |
| RSK-02 | **Yerel kaydın kaybolması:** Kayıtlar yalnız tarayıcıda. Tarayıcı verisi silinirse, başka tarayıcı/bilgisayar kullanılırsa veya dosya taşınırsa ekibin deneme verisi kaybolur. Ekip üyeleri farklı bilgisayarlarda farklı veri görür. | Orta — 3 kişi farklı bilgisayarda çalışıyoruz. | Orta — gözlemler 08'de ve ekran görüntülerinde duruyor, ama aynı durumu yeniden kurmak zaman alır. | Ekip üyelerinin aynı adımda farklı R numarası görmesi. Kaydetme açıklamasında uyarı çıkması. | Her deneme öncesi "Örnek veriyi sıfırla". Adımları ve ekran görüntülerini `kanit/` klasöründe saklamak. Kayıt numarasına değil durum değişimine bakmak. | Ramazan Berat Koç |
| RSK-03 | **Belgeler arası tutarsızlık:** 03, 04, 05, diyagramlar ve issue kartları ayrı kişilerce güncelleniyor. Bir rolün yetkisi bir belgede değişip diğerinde eski kalabilir. | Orta — 3 kişi, 9 belge, 2 diyagram, 6 kart. | Orta — yanlış davranış test edilir veya değerlendirmede puan kaybı olur. | Bir PR'de yalnız tek belgenin değişmesi. Diyagramda olmayan bir okun gereksinimde bulunması. | Her değişiklikte 05 izlenebilirlik tablosuna bakmak. Yazan dışındaki üyenin incelemesi (09'daki sıra). | İhsan Kart |
| RSK-04 | **3 kişilik ekipte iş yükü:** Sınıf planı 4–5 kişilik gruplara göre. Biz 3 kişiyiz; bir kişi gelemezse inceleme sırası bozulur ve işler yetişmeyebilir. | Orta | Orta — teslim gecikir veya incelemesiz iş teslim edilir. | Bir kartın 2 günden uzun "Üzerinde çalışılıyor"da kalması. | Görevleri küçük kartlara bölmek. Gelemeyen üyenin incelemesini kalan üyenin üstlenmesi ve bunun 09'a yazılması. | İhsan Kart |
| RSK-05 | **GitHub iş akışında hata:** Doğrudan `main` dalına yazmak, çakışan değişiklikler veya incelemesiz birleştirme. | Orta — ekipte branch/PR deneyimi farklı. | Düşük–Orta — geri alınabilir, ama zaman kaybettirir. | PR'siz commit'ler, "merge conflict" uyarısı. | Herkes kendi dalında çalışır (`docs/konu`). `main` dalına yalnız incelenmiş PR ile girilir. | Metin Efe Uğur |

## RSK-01 ayrıntısı

- **Dayanak:** G-04'te vazgeçme doğru çalıştı. Ancak pencere metni ("…iptal edilsin mi?") ile "İptal" düğmesi birlikte okununca anlam karışıyor. Vazgeçtikten sonra ekrandaki bildirim değişmedi.
- **Önemli ayrım:** Bu bir **yazılım hatası değil**, anlaşılırlık riskidir. İşlev doğru çalışıyor.
- **Durum:** Açık. Önlem planlandı, uygulanmadı.
- **Ne zaman yeniden değerlendirilecek?** S-01'in yanıtı alınıp metin değişikliği yapıldıktan ve NFR-01 ölçüldükten sonra.

## Risk gözden geçirme kaydı

| Tarih | Risk | Yeni kanıt | Karar | Kontrol eden |
|---|---|---|---|---|
| [ ] | RSK-01 | [ ] | [Açık / Azaldı / Kapandı] | [ ] |
