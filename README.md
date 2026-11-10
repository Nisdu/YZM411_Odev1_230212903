# YZM 411 Ödev 1 — Renk, Aydınlatma ve Örnekleme (Nisa Duru)

## Klasör Yapısı
```
YZM411_Odev1_230212903/
├── YZM411_Odev1.ipynb      # Tüm deneyler, tahminler, ölçümler ve gözlemler
├── fotograflar/            # 3 özgün iPhone fotoğrafı: IMG_7106 (normal), IMG_7104 (gölge), IMG_7107 (lamba)
├── ciktilar/               # Çalıştırma sonucu üretilen PNG görseller, CSV tablolar ve JSON kayıtları
├── rapor.pdf               # 2 sayfalık ödev raporu
├── kaynak_beyani.md        # Yapay zekâ ve kaynak beyanı
└── README.md
```
Teslim dosyası: `YZM411_Odev1_230212903.zip`

## Kurulum ve Yeniden Çalıştırma
```bash
pip install numpy opencv-python pandas matplotlib pillow notebook
```
1. `YZM411_Odev1.ipynb` dosyasını açın.
2. *Kernel → Restart & Run All* seçeneğiyle tüm hücreleri çalıştırın.
3. Tüm çıktılar `ciktilar/` klasörüne yazılır; son hücre teslim ZIP'ini oluşturur.

## Parametreler ve sürümler
Kullanılan piksel koordinatları, örnek bölge, eşikler, kamera notu, EXIF ve kütüphane sürümleri `ciktilar/parametreler.json` ve `ciktilar/donmus_esikler.json` içinde kayıtlıdır.
Gölge ve lamba fotoğrafları SIFT + RANSAC homografisiyle normal fotoğrafa hizalanıp ortak alana kırpılmıştır (`ciktilar/hizalama.csv`, `00_hizalama.png`).
