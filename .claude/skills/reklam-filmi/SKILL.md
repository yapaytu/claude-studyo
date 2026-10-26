---
name: reklam-filmi
description: Ürün için sinematik reklam filmi sahnesi yapar: karanlık stüdyo, ışık süzmesi, toz, letterbox, kamera bilgisi, ürün adı. "reklam filmi", "ürün reklamı", "sinematik reklam", "commercial" isteklerinde kullan.
---

# Sinematik ürün reklamı

Önce `STUDYO.md` dosyasını ve `ornekler/reklam-filmi.html` örneğini oku.

## İnsandan al (yoksa kendin seç)
- Ürün (parfüm, ayakkabı, kulaklık, kahve…), adı, ana rengi
- Ton: lüks / enerjik / doğal

## Görünüm reçetesi
- **Işık tasarımı:** Ürün karanlık bir stüdyoda, arkadan sıcak radyal ışık. Üründe sabit 1–2 dikey parlama şeridi (hafifçe sallanır) + ara sıra gövdeyi boydan geçen eğik ışık süzmesi (`skewX(-18)`, kırpma maskesi içinde).
- **Kamera:** Sahne boyunca %10–15 yavaş itme (push-in). Kesme yok; tek akıcı plan.
- **Doku:** Havada süzülen 20–30 toz zerresi (farklı hız, yukarı), ürün altında yayılan halka (su/yansıma), süzme geçerken yatay anamorfik parlama çizgisi.
- **Sinema dili:** Üstte ve altta siyah letterbox bantları. Köşelerde küçük kamera bilgisi: kırmızı yanıp sönen REC, zaman kodu, `50mm · f/1.4`. Bunlar küçük ve sade kalır.
- **Ürün adı:** 2. saniyeden sonra, serif (Fraunces), geniş harf aralığından normale daralarak belirir. Altında küçük alt satır.
- **Renk:** En fazla iki renk ailesi (ör. altın + kömür). Saf beyaz yok, en açık renk krem.
- Ürün gerçek bir markaysa logosunu taklit etme; insan kendi markasını veriyorsa onun adını yaz.

## Akış
1. Ürünü SVG ile çiz (gradyanlı gövde + kapak + etiket) ya da insan PNG verdiyse onu kullan.
2. `ciktilar/<urun>-reklam.html`, kontroller, MP4.
