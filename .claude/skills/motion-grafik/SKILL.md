---
name: motion-grafik
description: Bir motion tasarımcısı gibi hareketli grafik yapar: kinetik tipografi, dönen şekiller, çizilen çizgiler, büyüyen grafikler. "motion grafik", "hareketli grafik", "kinetik yazı", "animasyonlu yazı", "motion design" isteklerinde kullan.
---

# Motion grafik

Önce `STUDYO.md` dosyasını ve `ornekler/motion.html` örneğini oku.

## İnsandan al (yoksa kendin seç)
- Mesaj (en fazla 5 kelime) ve varsa bir sayı/veri
- Marka renkleri (yoksa: mor zemin + sarı + pembe + beyaz)

## Görünüm reçetesi
- **Kinetik yazı:** Kelimeler alt alta, her biri 6 kare arayla, dönüşümlü sol/sağdan girer; `geri()` eğrisiyle hafif taşıp oturur. Yazı büyük (150–190 px), sıkı satır aralığı (0.95), negatif harf aralığı.
- **Şekiller:** 2–4 geometrik öğe sürekli hareket eder: nabız gibi büyüyüp küçülen daire, kesikli çizgiyle dönen halka, dönen yuvarlak kare.
- **Çizilen çizgi:** `stroke-dasharray` = yol uzunluğu, `stroke-dashoffset` uzunluktan 0'a iner.
- **Veri:** Çubuklar sırayla (5 kare arayla) yükselir; sayı varsa yanında sayaç.
- **Renk:** Zemin tek ve doygun; en fazla 3 vurgu rengi. Gradyan ve gölge yok, düz renk.
- **Ritim:** Her 12–20 karede bir şey olur. Döngüye uygun kur (`d = f % 120`) ki video sonsuz dönebilsin.

## Akış
`ciktilar/<ad>-motion.html`, kontroller, MP4.
