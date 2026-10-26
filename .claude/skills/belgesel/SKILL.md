---
name: belgesel
description: Netflix belgeseli havasında anlatım videosu sahnesi yapar: karanlık atmosfer, film greni, serif bölüm başlığı, akan yıl/sayı, alt yazı. "belgesel", "anlatım videosu", "documentary", "explainer giriş" isteklerinde kullan.
---

# Belgesel / anlatım sahnesi

Önce `STUDYO.md` dosyasını ve `ornekler/belgesel.html` örneğini oku.

## İnsandan al (yoksa kendin seç)
- Konu ve bölüm adı ("İnsan ve Makine")
- Varsa anlatım metni (alt yazı olarak) ve seslendirme dosyası

## Görünüm reçetesi
- **Atmosfer:** Neredeyse siyah zemin (#050608), tek bir güçlü görsel merkez (dönen dünya, harita, eski fotoğraf). Görsel sahne boyunca yavaşça büyür (Ken Burns, %15–20).
- **Dönen dünya tekniği:** Rastgele enlem/boylam noktaları; ortografik izdüşüm `x = cos(lat)·sin(lon+dön)`, `z = cos(lat)·cos(lon+dön)`, `z > 0` olanları çiz, parlaklığı `z` ile çarp. Kenarda ince mavi hale.
- **Film greni:** Tam ekran `feTurbulence` (baseFrequency 0.9) + `feColorMatrix` ile %8–10 opak beyaz; `seed` her karede değişir.
- **Başlık:** Kısa kırmızı çizgi → mono, geniş aralıklı "BÖLÜM 1" → büyük serif başlık. Yavaş belirir (0.5 sn), zıplamaz.
- **Bilgi:** Yıl ya da sayı sayacı (1950 → 2026) yumuşak yavaşlayarak durur.
- **Alt yazı:** Altta, beyaz, gölgeli, cümle cümle. Seslendirme varsa her cümle kendi zamanında çıkar.
- Hareketler yavaş ve ağır; hiçbir şey sekmez, parlamaz.

## Akış
1. Uzun anlatım = birden çok sahne. Her sahne ayrı HTML; sonra `ffmpeg -f concat` ile birleştir.
2. `ciktilar/<konu>-belgesel.html`, kontroller, MP4 (`--ses` ile seslendirmeyi ekle).
