---
name: kil-animasyon
description: Ürün ya da marka için hamur/kil (claymation) görünümlü stop-motion reklam sahnesi yapar; tek HTML dosyası, MP4'e kaydedilir. "kil animasyon", "claymation", "hamur reklam", "stop motion reklam" isteklerinde kullan.
---

# Kil animasyon reklam

Önce `STUDYO.md` dosyasını ve `ornekler/kil.html` örneğini oku.

## İnsandan al (yoksa kendin seç, sorma)
- Ürün ya da marka adı, rengi
- Tek cümlelik slogan (en fazla 3 kelime: "FERAH KAL.")

## Görünüm reçetesi
- **Stop-motion hissi:** Hareketi 15 kare/sn'ye düşür: `const q = Math.floor(f / 2)`; bütün hareket `q`'dan hesaplanır.
- **Elle tutulmuş titreme:** Her adımda öğelere 1–3 px rastgele kayma ve ±3° dönme ver: `(rnd(q * 13 + k) - 0.5) * 2.4`.
- **Hamur dokusu:** SVG filtresi: `feTurbulence` (fractalNoise, baseFrequency 0.04–0.05, numOctaves 3) → `feDiffuseLighting` (surfaceScale 2–3, ışık sol üstten, elevation ~56) → `feComposite arithmetic k1≈1.18` ile renkle çarp → `SourceAlpha` ile kırp. `seed` her adımda 3 değer arasında değişsin, doku "kaynar".
- **Hacim:** Her şekle üstten sol beyaz, alttan sağ koyu bir radyal gradyan bindir.
- **Renk:** Pastel ve sıcak: şeftali duvar, kiremit zemin, sarı güneş. Siyah kontur yok; şekiller yumuşak ve yuvarlak.
- **Karakter:** Ürünün kendisi yüz kazanır (iki göz, gülümseme). Zıplarken yere değince ezilir (squash), havada uzar (stretch). Yere gölge düşer, yükseldikçe küçülür.
- **Slogan:** Sahnenin 2. saniyesinde, hamur harflerle (aynı filtre) aşağıdan gelir.

## Akış
1. `araclar/sablon.html` → `ciktilar/<urun>-kil.html`.
2. Sahneyi yaz, `STUDYO.md`'deki kontrolleri yap, MP4'ü al.
