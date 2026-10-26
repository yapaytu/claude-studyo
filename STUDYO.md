# Stüdyo sözleşmesi

Bütün skill'ler aynı sözleşmeyle çalışır. Bu dosyayı her skill'den önce oku.

## Çıktı

- Her sahne **tek bir HTML dosyası**: `ciktilar/<ad>.html`. Şablon: `araclar/sablon.html`. Şablonu kopyala, sadece `window.SURE` ve `window.ciz` kısmını değiştir.
- Tuval 1080 × 1920 (dikey Reels/TikTok/Shorts). İnsan yatay isterse `W`, `H` ve `#sahne` boyutunu birlikte değiştir.
- 30 kare/sn. Bir sahne 4–8 saniye. Daha uzun iş, birden fazla sahne demektir.
- Önizleme: dosyayı tarayıcıda aç, döngüde oynar.
- MP4: `node araclar/kaydet.mjs ciktilar/<ad>.html`. Ses eklemek için sonuna `--ses ses.mp3`.

## Kurallar

1. **Her şey kareye bağlı.** `window.ciz(f)` sadece `f` kare numarasına bakarak çizer. `Math.random`, `Date`, `setTimeout`, CSS animasyonu, CSS transition yok. Rastgelelik lazımsa şablondaki `rnd(n)` (her seferinde aynı sonucu verir).
2. **Hazır yardımcılar:** `c01` (0–1 arası sıkıştır), `cik` (yumuşak duruş), `geri` (hafif taşıp oturma), `rnd`.
3. **Yazı tipleri şablonda yüklü:** Unbounded (başlık), Fraunces (serif, sinematik), Fredoka (çizgi film), JetBrains Mono (teknik). Başkası lazımsa Google Fonts linkine ekle, `display=block` kalsın.
4. **Dış kütüphane** sadece gerektiğinde ve sürüm numarasıyla (ör. `three@0.160.0`). 3D sahnede `<script type="module">` kullan ve `WebGLRenderer`'a `preserveDrawingBuffer: true` ver.
5. **Ekranın kenarları:** Yazı ve önemli şeyler soldan/sağdan 90 px, üstten 220 px, alttan 380 px içeride kalsın (Instagram arayüzü oraları kapatır).
6. **Okunur yazı:** En küçük yazı 34 px. Bir karede tek fikir.
7. **İlk kare boş olmaz.** 0. karede sahne zaten görünür; siyah ekran ya da boş giriş yok.

## Bitti demeden önce

1. `node araclar/kaydet.mjs` ile MP4'ü al.
2. Baştan, ortadan ve sondan kare çıkar ve kendin bak:
   `ffmpeg -ss 0.5 -i cikti.mp4 -frames:v 1 kare1.png` (2.5 ve son saniyeden önce de aynısı).
3. Kesilen yazı, taşan öğe, boş kare, yanlış Türkçe karakter varsa düzelt ve tekrar kaydet.
4. İnsana dosya yolunu ve 1–2 cümlelik özeti ver.

## Örnekler

`ornekler/` klasöründe her skill'in çalışan bir örneği var. Yeni sahneye başlamadan ilgili örneği oku: hangi tekniğin nasıl yazıldığını oradan al, aynen kopyalama.
