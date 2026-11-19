# 03 — Gereksinimler

Ekip: Grup 04 — İhsan Kart, Metin Efe Uğur, Ramazan Berat Koç  
Tarih: 19.11.2026  
Sürüm: 0.1  
Hazırlayan: Metin Efe Uğur · İnceleyen: Ramazan Berat Koç (inceleme henüz yapılmadı)  
Durum: Taslak. İşlevsel gereksinimlerin dayanağı gözlemlerimiz. Kalite hedefleri ölçülmedi.

Gereksinimleri "Sistem … koşulunda … yapmalıdır" biçiminde, kontrol edilebilir yazdık. Ekrandaki düğme adı tek başına gereksinim sayılmaz.

**Öncelik:** **Yüksek**, temel randevu akışını veya kayıt durumunu doğrudan etkiler. **Orta**, takibi kolaylaştırır ama bilgi başka yerden de elde edilebilir. Altı gereksinimin hepsi v0.1 kapsamındadır.

## İşlevsel gereksinimler

| Kimlik | Başlık | Sistem ne yapmalı? | Aktör / koşul | Öncelik | Dayanak |
|---|---|---|---|---|---|
| FR-01 | Uygun saatleri listeleme | Sistem, seçili doktor ve tarihin 10 sabit saatini göstermelidir. O saatte iptal edilmemiş kayıt yoksa **Uygun**, Bekliyor kayıt varsa **Dolu**, Tamamlandı kayıt varsa **Kapalı** yazmalıdır. Doktor veya tarih değişince saatler yeni seçime göre güncellenmelidir. | Üç rol de görür. Yalnız Hasta ve Resepsiyon saat seçebilir. | Yüksek: Kullanıcı boş saati bilmeden randevu alamaz. | G-01, G-07, G-09 |
| FR-02 | Randevu oluşturma | Sistem, Uygun bir saat seçilip "Randevuyu onayla"ya basılınca seçili hasta, doktor, tarih ve saatle yeni bir kayıt oluşturmalıdır. Kayıt **Bekliyor** durumunda olmalı, saat **Dolu**ya geçmelidir. Saat seçilmeden onay düğmesi pasif olmalıdır. | Hasta kendi adına, Resepsiyon seçili hasta adına. Doktor oluşturamaz. BR-01'e uymalı. | Yüksek: Ürünün ana işi. | G-02, G-07 |
| FR-03 | Kendi randevusunu iptal etme | Sistem, hasta rolünde yalnız seçili hastanın kendi kayıtlarını göstermelidir. Hastanın kendi **Bekliyor** kaydı için iptal isteğinde onay sormalıdır. Onaylanırsa kayıt **İptal edildi** olmalı, listede kalmalı ve saat Uygun olmalıdır. Vazgeçilirse hiçbir şey değişmemelidir. | Yalnız Hasta, yalnız kendi Bekliyor kaydı. Tamamlandı/İptal edildi kayıt iptal edilemez. | Yüksek: Hasta plan değişikliğini kendisi yönetir. Yanlışlıkla iptal riski var (RSK-01). | G-04, G-05, G-06 |
| FR-04 | Günlük liste | Sistem, Resepsiyon ve Doktor rollerinde seçili doktorun seçili tarihteki **bütün** hasta kayıtlarını saat sırasıyla ve durum etiketiyle göstermelidir. Resepsiyondaki hasta seçimi listeyi daraltmamalıdır. | Resepsiyon ve Doktor. Hasta bu listeyi görmez. | Yüksek: Klinik çalışanının günü takip etmesini sağlar. | G-07, G-08, G-09 |
| FR-05 | Randevuyu tamamlama | Sistem, Doktor rolünde görevli doktorun günlük listesindeki **Bekliyor** kayıt için "Tamamlandı" işlemi sunmalıdır. İşlem sonrası kayıt **Tamamlandı**, saat **Kapalı** olmalı, kayıtta yeniden tamamlama düğmesi bulunmamalıdır. | Yalnız Doktor; kayıt seçili doktor + tarihe ait ve Bekliyor olmalı. | Yüksek: Biten ve bekleyen muayeneyi ayırır. | G-07 |
| FR-06 | Günlük toplamlar | Sistem, Resepsiyon ve Doktor rollerinde seçili doktor ve tarih için Bekleyen, Tamamlanan, İptal edilen ve Toplam sayıları göstermelidir. Toplam, üç durumun toplamına eşit olmalıdır. Her oluşturma, iptal veya tamamlamada sayılar güncellenmelidir. Hasta rolünde sayılar gizlenmelidir. | Resepsiyon ve Doktor; yalnız seçili doktor + tarih. | Orta: Günü hızlı okumayı sağlar; aynı bilgi listede de var. | G-02, G-06, G-07, G-08, G-09 |

## İş kuralı

**BR-01:** Aynı doktor, tarih ve saat için iptal edilmemiş (Bekliyor veya Tamamlandı) ikinci randevu oluşturulamaz. İptal edildi kaydı saati engellemez.

| O saatteki kayıt | Saatin görünümü | Yeni kayıt açılabilir mi? |
|---|---|---|
| Bekliyor | Dolu | Hayır |
| Tamamlandı | Kapalı | Hayır |
| Yalnız İptal edildi veya hiç kayıt yok | Uygun | Evet |

**Bizim denememizden örnek:** Selin Kaya / 12 Kasım / 14:00'te Kaan'ın R008 kaydı Bekliyor iken Ece seçildiğinde de saat Dolu kaldı ve seçilemedi (G-03). R008 iptal edilince 14:00 yeniden Uygun oldu (G-05). R005 tamamlanınca 09:30 **Kapalı** oldu, yani yeniden açılmadı (G-07). Saatin anahtarı **doktor + tarih + saat**tir; hasta değişikliği bunu etkilemez.

**BR-01 hangi işlevleri etkiliyor?** FR-01 (saatin görünümü), FR-02 (oluşturma engeli), FR-03 (iptal saati açar), FR-05 (tamamlama saati kapalı tutar). FR-04 ve FR-06 yalnız sonucu gösterir.

**Kuralın sınırı:** Aynı hastanın farklı doktorlardan aynı saate randevu almasını engellemez. Kontrol yalnız aynı sayfanın verisi içindir; iki sekme veya iki cihazda çakışma önlenmez (BILINEN_KISITLAR.md). Bunun istenip istenmediğini paydaşa soracağız.

## Kalite gereksinimleri

Bu sayılar ekibin önerdiği **hedeflerdir**, ölçülmüş sonuç değildir.

| Kimlik | Konu | Ölçülebilir hedef | Ölçüm koşulu | Durum |
|---|---|---|---|---|
| NFR-01 | Kullanılabilirlik | Daha önce prototipi kullanmamış 4 kişiden en az 3'ü, "bekleyen randevuyu iptal et" ve "iptali başlat ama vazgeç" görevlerinin ikisini de yardımsız, doğru ve her biri 60 saniyenin altında yapmalı. | Hasta rolü, Ece Yılmaz, Selin Kaya, 12 Kasım. Her görev için ayrı Bekliyor kayıt. Gözlemci hangi düğmeye basılacağını söylemez. | Ölçülmedi |
| NFR-02 | Yanıt süresi | Resepsiyon rolünde doktor seçimi değişince B1, B2 ve B3'ün üçü de yeni doktora ait doğru içeriği en geç 1 saniyede göstermeli. 10 denemenin 10'u bu sınırı sağlamalı. | Aynı bilgisayar ve tarayıcı, tek sekme, en fazla 20 kayıt, 12 Kasım, Deniz Arı ↔ Selin Kaya. Ekran kaydı ile ölçülür. | Ölçülmedi |
| NFR-03 | Klavyeyle kullanım | Randevu oluşturma, iptal, iptalden vazgeçme ve tamamlama görevleri yalnız klavye (Tab, Shift+Tab, Enter, Boşluk) ile yapılabilmeli. Odaklanan öğe her an görünür olmalı. | Aynı tarayıcı, örnek veriler, onay penceresi dahil. | Ölçülmedi |

**Belirsiz ifadeyi düzeltme örneği:** "Sistem hızlı olmalı" ifadesi hangi işlem, ne kadar süre ve hangi ortam olduğunu söylemiyor. Bu yüzden ölçülemez. Bunu NFR-02'deki gibi rol, işlem, süre sınırı, deneme sayısı ve ölçüm yöntemiyle yazdık.

Ölçüm adımları `04-kabul-kriterleri.md` belgesinde. Sonuçlar ölçüm yapıldıktan sonra 08'e yeni satır olarak eklenecek.
