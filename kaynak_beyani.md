# Kaynak ve Yapay Zekâ Beyanı

**Öğrenci:** Nisa Duru — **No:** 230212903

## Veri
Fotoğraflar (`fotograflar/IMG_7106.JPG, IMG_7104.JPG, IMG_7107.JPG`) tarafımdan 9 Kasım 2026 tarihinde iPhone 16 Pro Max ile çekilmiştir (EXIF saatleri: 17:26). Fotoğraflarda tanınabilir kişi yoktur.

## Yapay zekâ kullanımı
| Araç | Kullanım amacı | Etkilediği dosya/hücre | Nasıl doğruladım |
|---|---|---|---|
| Claude (Kasım 2026) | Çekimler arasındaki el kaymasını gideren SIFT + RANSAC homografi hizalaması ile RGB/HSV maskeleme, parlaklık/gama ve 1/4 küçültme görselleştirme kodlarının düzenlenmesi | `YZM411_Odev1.ipynb` içindeki kod hücreleri | `02_koordinatlar.png` üzerinde turuncu mandalina ve 'PentaPoint' kartı koordinatlarını görsel olarak denetledim; `hizalama.csv` tablosunda medyan hatanın ~0.91–0.94 piksele indiğini, `06_maske_bindirme.png` ve `09_kucultme_yan_yana.png` çıktılarını ve CSV tablolarındaki tüm sayıları kontrol ederek doğruladım. |

Deney öncesi beklenti ve tahminler, koordinat ve eşik seçimleri, gözlem yanıtları ve rapor değerlendirmeleri kendi deney sonuçlarıma dayanarak tarafımdan yazılmıştır.

## Diğer kaynaklar
- YZM 411 Bilgisayarlı Görü ders notları (Hafta 1–2)
- OpenCV dokümantasyonu (`cv2.cvtColor`, `cv2.inRange`, `cv2.resize`, `cv2.findHomography`)
