---
name: 3d-animasyon
description: Pixar tadında parlak, yumuşak ışıklı 3D animasyon sahnesi (Three.js) yapar; karakter, oyuncak dünya, ürün sahnesi. "3d animasyon", "pixar gibi", "3 boyutlu sahne", "3d karakter" isteklerinde kullan.
---

# 3D animasyon sahnesi

Önce `STUDYO.md` dosyasını ve `ornekler/3d.html` örneğini oku.

## İnsandan al (yoksa kendin seç)
- Karakter ya da nesne (ör. "turuncu robot", "kahve fincanı", "kedi")
- Ortam (oda, park, masa üstü) ve 1 cümlelik olay

## Görünüm reçetesi
- **Kütüphane:** `three@0.160.0`, `<script type="module">` içinde `await import("https://cdn.jsdelivr.net/npm/three@0.160.0/build/three.module.js")`. Renderer: `antialias`, `alpha`, `preserveDrawingBuffer: true`, `setPixelRatio(1)`, `PCFSoftShadowMap`, `SRGBColorSpace`.
- **Malzeme:** Oyuncak gibi parlak: `MeshPhysicalMaterial` + `clearcoat: 1`, `roughness ~0.3`. Zemin mat (`roughness 0.9`).
- **Işık:** `HemisphereLight` (beyaz gök, sıcak zemin) + gölgeli `DirectionalLight` (sağ üstten) + arkadan soğuk renkli bir `PointLight` (kenar ışığı). Gölge haritası 2048.
- **Arka plan:** HTML'de yumuşak gökyüzü gradyanı, canvas şeffaf.
- **Karakter dili:** Basit büyük formlar (küre, kapsül), iri gözler, göz kırpma (her ~70 karede 3 kare). Zıplarken squash & stretch: hacmi koru (`x = z = 1/√s`, `y = s`).
- **Kamera:** Yavaş yörünge (`sin(f/45)` ile ±30°) ve sahne boyunca hafif yaklaşma. Dikey kadrajda karakter ekranın ortasında, tepeden 220 px içeride.
- **Hayat:** Arka planda 3–5 ikincil öğe kendi ritminde hareket etsin (zıplayan top, dönen küp).

## Akış
1. `ornekler/3d.html`'i kopyala → `ciktilar/<ad>-3d.html`, nesneleri değiştir.
2. Her karede tüm durum `ciz(f)` içinde baştan ayarlanır, sonra `renderer.render`.
3. Kontrolleri yap, MP4'ü al.
