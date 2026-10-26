---
name: konusan-maskot
description: Markaya özel, sese göre ağzını oynatan konuşan maskot karakteri tasarlar ve canlandırır; kostüm, göz kırpma, nefes. "maskot", "konuşan karakter", "marka karakteri", "mascot" isteklerinde kullan.
---

# Konuşan marka maskotu

Önce `STUDYO.md` dosyasını ve `ornekler/maskot.html` örneğini oku.

## İnsandan al (yoksa kendin seç)
- Marka adı, ana rengi, markanın ne iş yaptığı
- Varsa seslendirme dosyası (mp3/wav) ve söyleyeceği cümle

## Tasarım kuralları
- **Silüet:** Tek parça, yuvarlak, uzaktan tanınan bir şekil. Gövdesiz kafa + süzülen eller en kolay canlanan yapı.
- **Yüz:** İki büyük göz (parlak noktalı), küçük ağız, yanak allığı. Marka rengi gövdede, kontur koyu ve kalın.
- **Kimlik:** Markayı anlatan tek bir detay (antende ikon, alında harf, şapka). Fazla aksesuar yüzü kalabalıklaştırır.
- **Canlılık:** Nefes (yavaş yukarı aşağı), hafif sallanma, her ~84 karede göz kırpma, eller kendi ritminde süzülür.
- **Kostüm:** İstenirse sahnede değişir (bere, kep…); kostüm yüzü ve markanın yazısını asla kapatmaz.

## Konuşma (ağız senkronu)
1. Ses varsa: `python3 araclar/genlik.py ses.mp3 ciktilar/<ad>-ses.js` → kare başına `window.AGIZ` dizisi üretir.
2. HTML'de `<script src="<ad>-ses.js"></script>`; `ciz(f)` içinde `window.AGIZ[f]` (0–1) ile ağız yüksekliğini aç, 0.08 altıysa gülümseyen kapalı ağız çiz.
3. `window.SURE = window.SES_SURE`.
4. Kaydet: `node araclar/kaydet.mjs ciktilar/<ad>.html --ses ses.mp3`.

## Akış
`ciktilar/<marka>-maskot.html`, kontroller, MP4.
