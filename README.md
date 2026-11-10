# YZM 411 Ödev 1 — Renk, Aydınlatma ve Örnekleme

**Öğrenci:** Nisa Duru  
**Öğrenci no:** 230212903  
**Ders:** YZM 411 Bilgisayarlı Görü (2026–2027 Güz)  
**Repo:** https://github.com/Nisdu/YZM411_Odev1_230212903

## Özet

Aynı masaüstü sahnesinin normal ışık, gölge ve lamba altında çekilmiş üç özgün fotoğrafı üzerinde renk eşikleri, parlaklık/gama dönüşümleri ve 1/4 küçültme deneyleri yapılmıştır. Her deneyden önce tahmin yazılmış; ölçümlerle karşılaştırılmıştır.

**Sahne:** Turuncu mandalina, çay bardağı, “PentaPoint” yazılı prospektüs kartı, beyaz A4 kâğıt, bej masa.  
**Kamera:** iPhone 16 Pro Max, 24 MP JPEG; otomatik pozlama ve otomatik beyaz dengesi açık.

## Klasör yapısı

```
YZM411_Odev1_230212903/
├── YZM411_Odev1.ipynb   # Tüm deneyler, tahminler, ölçümler ve gözlemler
├── fotograflar/         # Özgün çekimler
│   ├── IMG_7106.JPG     # normal ışık
│   ├── IMG_7104.JPG     # gölge
│   └── IMG_7107.JPG     # lamba
├── ciktilar/            # PNG/JPG görseller, CSV tablolar, JSON kayıtları
├── rapor.pdf            # En fazla 2 sayfalık PDF rapor
├── kaynak_beyani.md     # Yapay zekâ ve kaynak beyanı
└── README.md
```

Teslim ZIP adı: `YZM411_Odev1_230212903.zip` (notebook son hücrede üretir).

## Kurulum

```bash
pip install numpy opencv-python pandas matplotlib pillow notebook
```

## Çalıştırma sırası

1. Bu klasörü açın.
2. `YZM411_Odev1.ipynb` dosyasını Jupyter / VS Code ile açın.
3. **Kernel → Restart & Run All** ile tüm hücreleri çalıştırın.
4. Çıktılar `ciktilar/` altına yazılır.
5. Son hücre `YZM411_Odev1_230212903.zip` teslim arşivini oluşturur.

Defterde önce parametreler ve tahminler yer alır; ardından fotoğraf okuma, hizalama, Adım 4–7 deneyleri, sonuç tablosu ve ZIP gelir.

## Giriş dosyaları

| Koşul | Dosya |
|---|---|
| Normal | `fotograflar/IMG_7106.JPG` |
| Gölge | `fotograflar/IMG_7104.JPG` |
| Lamba | `fotograflar/IMG_7107.JPG` |

Çekimler arasında hafif el kayması olduğu için gölge ve lamba kareleri SIFT + RANSAC homografisiyle normal kareye hizalanıp ortak alana kırpılmıştır. Hizalama ölçüleri: `ciktilar/hizalama.csv`, görsel: `ciktilar/00_hizalama.png`.

Hizalama sonrası ortak görüntü boyutu: **5584 × 4120 × 3**, `uint8`, değer aralığı 0–255.

## Ana parametreler

Ayrıntılı kayıt: `ciktilar/parametreler.json` ve `ciktilar/donmus_esikler.json`.

| Parametre | Değer |
|---|---|
| Ölçüm pikselleri (x, y) | (2180, 2520), (2320, 2580), (1750, 3400) |
| Komşuluk | 5×5 |
| Örnek bölge (x, y, w, h) | (2140, 2460, 220, 200) |
| RGB eşiği (dondurulmuş) | R 150–215, G 100–155, B 40–90 |
| HSV eşiği (dondurulmuş) | H 12–22, S 120–205, V 140–220 |
| Parlaklık kaydırması | b = +40 |
| Gama | γ = 0.5 ve γ = 2.0 |
| Yazı kesiti (x, y, w, h) | (2380, 2940, 640, 760) |
| Küçültme oranı | 1/4 (`INTER_NEAREST`, `INTER_AREA`) |

Eşikler yalnız normal ışıklı karedeki örnek bölgeden seçilmiş ve üç fotoğrafta **değiştirilmeden** uygulanmıştır.

## Kütüphane sürümleri (kayıtlı çalıştırma)

| Paket | Sürüm |
|---|---|
| Python | 3.12.9 |
| NumPy | 2.4.4 |
| OpenCV | 4.12.0 |
| pandas | 3.0.2 |
| matplotlib | 3.10.8 |
| Pillow | 11.3.0 |
| Platform | macOS arm64 |

## Önemli çıktılar

| Dosya | İçerik |
|---|---|
| `rapor.pdf` | 2 sayfalık ödev raporu (fotoğraflar, altı maske, karşılaştırma tablosu) |
| `ciktilar/sonuc_tablosu.csv` | Özet sonuç tablosu |
| `ciktilar/adim4_pikseller.csv` | Üç pikselin RGB ölçümleri |
| `ciktilar/adim5_maskeler.csv` | Altı maskenin alan oranları |
| `ciktilar/adim6_donusumler.csv` | Parlaklık / gama ortalamaları |
| `ciktilar/adim7_kucultme.csv` | Küçültme karşılaştırma ölçüleri |
| `ciktilar/05_alti_maske.png` | Altı maske görseli |
| `ciktilar/09_kucultme_yan_yana.png` | 1/4 küçültme karşılaştırması |

## Rapor ve beyan

- PDF rapor: `rapor.pdf` (notebook rapor olarak kullanılmamalıdır).
- Kaynak / yapay zekâ beyanı: `kaynak_beyani.md`.
