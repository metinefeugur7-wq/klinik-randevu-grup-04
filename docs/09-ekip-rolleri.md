# 09 — Ekip rolleri ve katkı planı

Ekip: Grup 04 — 3 kişi  
Tarih: 19.11.2026  
Sürüm: 0.1  
Durum: Görev planı uygulandı. 19.11.2026 itibarıyla her üyenin ilk katkısı ve arkadaş incelemesi "Katkı kaydı" tablosunda.

Buradaki görevler **ekip üyelerinin çalışma sorumluluklarıdır**. Uygulamadaki Hasta, Resepsiyon ve Doktor rolleriyle ilgisi yoktur. Sorumlu kişi işi takip eder, ama diğerleri de katkı verir. Herkes kendi katkısını sözlü olarak açıklayabilmelidir.

## Üyeler

| Üye | Ad soyad | Öğrenci no | GitHub kullanıcı adı |
|---|---|---|---|
| Üye 1 | İhsan Kart | 24118001 | ihsankart1907 |
| Üye 2 | Metin Efe Uğur | 24111001 | metinefeugur7-wq (grup deposunu açan) |
| Üye 3 | Ramazan Berat Koç | 24118036 | beratkoc33 |

## 3 kişilik görev dağılımı (bu oturum)

Sınıf planı 4–5 kişilik gruplara göre hazırlanmış. Biz 3 kişi olduğumuz için beş sorumluluk alanını üçe topladık. Her üye bir belge grubu ve bir diyagram/kart işi alıyor.

| Üye | Sorumluluk | Belgeler / çıktılar | İnceleyen |
|---|---|---|---|
| Üye 1 — İhsan Kart | İhtiyaç, paydaş, kapsam + bağlam diyagramı | 01, 02, diagrams/01-baglam, ISSUE-01 ve ISSUE-04 | Üye 2 |
| Üye 2 — Metin Efe Uğur | Gereksinim, kabul koşulu, izlenebilirlik + kullanım durumu diyagramı + GitHub deposu ve erişimler | 03, 04, 05, diagrams/02-kullanim-durumlari, ISSUE-02 ve ISSUE-05 | Üye 3 |
| Üye 3 — Ramazan Berat Koç | Prototip gözlemi, risk, toplantı ve görev takibi | 08, 06, 07, 09, ISSUE-03 ve ISSUE-06 | Üye 1 |

**İnceleme sırası:** 1 → 2 → 3 → 1. Kimse kendi işini son kontrol etmez.

## Sonraki oturumda görev dönüşümü

| Üye | Bu oturum | Sonraki oturum |
|---|---|---|
| Üye 1 | İhtiyaç, paydaş, kapsam | Gereksinim, kabul koşulu, izlenebilirlik |
| Üye 2 | Gereksinim, kabul koşulu, izlenebilirlik | Prototip gözlemi, risk, takip |
| Üye 3 | Prototip gözlemi, risk, takip | İhtiyaç, paydaş, kapsam |

## Çalışma anlaşması

Toplantıda (07) okunup kabul edilecek.

| Kural | Uygulama |
|---|---|
| Katılım | Her üye en az bir açıklanabilir katkı ve bir somut inceleme yapar. |
| Dal adı | `docs/kisa-konu` (ör. `docs/gereksinimler`). Küçük harf, boşluk yok, sözcükler tireyle. |
| `main` dalı | Doğrudan commit yok. Yalnız incelenmiş PR ile birleştirilir. |
| İnceleme | İnceleyen; dosyayı açar, dayanağıyla (FR, AC, G) karşılaştırır ve neye baktığını yazar. "Güzel olmuş" yeterli değildir. |
| Yardım | 15 dakika ilerleyemeyen üye, denediği adımı ve gördüğü sonucu gruba yazar. |
| Gelemeyen üye | İncelemesini sıradaki üye üstlenir, bu durum katkı kaydına yazılır (RSK-04). |
| Hesap | Herkes kendi GitHub hesabını kullanır. Ortak parola kullanılmaz. |

## Bir iş ne zaman "Tamamlandı" sayılır?

1. Beklenen çıktı (dosya/bölüm) hazır.
2. İlgili kontrol yapıldı: belge ise FR/AC/G ile karşılaştırıldı, deneme ise beklenen ve gözlenen ayrı yazıldı.
3. Yazan dışındaki üye inceledi ve geri bildirimini yazdı.
4. İnceleme bulguları düzeltildi ve yeniden kontrol edildi.
5. Son sürüm `main` dalında, issue ve PR bağlantıları 05'e eklendi.

Yalnız dosyanın yazılmış olması işi tamamlamaz.

## Katkı kaydı

İş **gerçekten yapıldıktan sonra** doldurulur.

| Üye | Yaptığı katkı (dosya/bölüm) | Issue / PR | İnceleyen ve geri bildirimi | Durum |
|---|---|---|---|---|
| Üye 1 — İhsan Kart | 01 vizyon-kapsam, 02 paydaşlar, bağlam diyagramı ve ISSUE-01/04 kartlarını depoya ekledi. Issue #5 (FR-01) ve #6 (FR-04) açtı. 01'e ilgili issue numaralarını ekledi. | #5, #6 / PR #9 | Metin Efe Uğur, PR #9'da eklenen numaraları issue başlıklarıyla karşılaştırıp onayladı. İhsan da Ramazan'ın PR #7'sini inceleyip onayladı. | Tamamlandı (PR #9 birleştirildi) |
| Üye 2 — Metin Efe Uğur | Grup deposunu açtı ve erişimleri verdi. Başlangıç paketi, 03 gereksinimler, 04 kabul koşulları, 05 izlenebilirlik, kullanım durumu diyagramı ve ISSUE-02/05 kartlarını ekledi. Issue #3 (FR-02) ve #4 (FR-05) açtı. 03'e ilgili issue numaralarını ekledi. | #3, #4 / PR #8 | Ramazan Berat Koç, PR #8'de numaraların FR-02/FR-05 ile eşleştiğini kontrol edip onayladı. Not: satır sonu boşluğu silindiği için "İlgili issue" satırı önizlemede "Durum" ile birleşiyor (küçük biçim sorunu, açık). Metin de İhsan'ın PR #9'unu onayladı. | Tamamlandı (PR #8 birleştirildi) |
| Üye 3 — Ramazan Berat Koç | 06 riskler, 07 toplantı notu, 08 prototip gözlemleri, 09 ekip rolleri, kanit/ ekran görüntüleri ve ISSUE-03/06 kartlarını ekledi. Issue #1 (FR-03) ve #2 (FR-06) açtı. 05'e issue numaralarını işledi. | #1, #2 / PR #7 | İhsan Kart, PR #7'de altı issue numarasını başlıklarla karşılaştırıp onayladı. Ramazan da Metin'in PR #8'ini onayladı. | Tamamlandı (PR #7 birleştirildi) |

**İnceleme kaydı biçimi:**

> İnceleyen: [ad] — Tarih: [ ]. İncelediğim dosya/bölüm: […]. Karşılaştırdığım dayanak: […]. Bulgu: […]. Düzeltme ve yeniden kontrol: […].
