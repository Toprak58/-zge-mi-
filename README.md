# 📄 Java ile PDF Özgeçmiş (iTextPDF Kütüphanesi)

Bu proje, **Java programlama dili** kullanılarak **iTextPDF** kütüphanesi yardımıyla bir **PDF formatında özgeçmiş (CV)** oluşturmayı amaçlar.

---

## 🎯 Projenin Amacı

Amaç, dışarıdan herhangi bir PDF editörü kullanmadan **Java kodu ile dinamik bir PDF dosyası üretmek** ve bu dosyaya görsel (fotoğraf), metin gibi içerikleri eklemektir.  
Bu sayede yazılımcılar, otomatik raporlar, belgeler veya CV gibi belgeleri programatik olarak oluşturabilirler.

---

## ⚙️ Kullanılan Teknolojiler ve Araçlar

| Teknoloji / Araç | Açıklama |
|------------------|-----------|
| **Java 21** | Proje dili |
| **Maven** | Proje yönetim aracı |
| **iTextPDF 5.5.13.3** | PDF oluşturma kütüphanesi |
| **IntelliJ IDEA** | IDE (geliştirme ortamı) |

---

## 🧩 Proje Yapısı

Ozgecmis/
├── src/
│ └── main/
│ ├── java/
│ │ └── org/example/Ozgecmis.java
│ └── resources/
│ └── foto.jpg
├── pom.xml
└── README.md



- **Ozgecmis.java** → PDF dosyasını oluşturan ana Java sınıfı  
- **foto.jpg** → Özgeçmişte kullanılacak fotoğraf  
- **pom.xml** → Maven yapılandırma dosyası (iTextPDF bağımlılığı burada tanımlanır)

---

## 💻 Kodun Açıklaması

### 1. **Document Nesnesi Oluşturma**
```java
Document document = new Document();
Bu nesne, oluşturulacak PDF belgesini temsil eder.

2. PdfWriter ile Dosyaya Yazma
java
Kodu kopyala
PdfWriter.getInstance(document, new FileOutputStream("Ozgecmis.pdf"));
PDF’nin nereye kaydedileceğini belirtir.
Burada, Ozgecmis.pdf adında bir dosya proje klasörüne yazılır.

3. Document’i Açma
java
Kodu kopyala
document.open();
PDF üzerine yazmaya başlamak için belgeyi açar.

4. Fotoğraf Ekleme
java
Kodu kopyala
Image img = Image.getInstance("src/main/resources/foto.jpg");
img.scaleToFit(150, 150);
document.add(img);
Belgeye görsel ekler ve fotoğraf boyutunu 150x150 piksele göre ayarlar.

5. Metin (Paragraf) Ekleme
java
Kodu kopyala
document.add(new Paragraph("Ozgecmis\n\n"));
document.add(new Paragraph("Ad Soyad: Ahmet Yilmaz"));
Paragraf şeklinde yazılar PDF’e eklenir.
\n satır atlamayı sağlar.

6. Belgeyi Kapatma
java
Kodu kopyala
document.close();
Belgeyi sonlandırır ve PDF dosyasını kaydeder.

🧠 Öğrenilenler
Java’da dış kütüphane (iTextPDF) kullanımı

Maven ile bağımlılık ekleme (pom.xml)

Dosya yolu (path) yönetimi

Görsel ve metinlerin PDF formatında birleştirilmesi

Hata yakalama (try-catch) ve FileNotFoundException çözümü

🖼️ Örnek Çıktı
PDF dosyası oluşturulduğunda proje klasöründe aşağıdaki şekilde görünür:

Kodu kopyala
Ozgecmis.pdf
İçinde:

Fotoğraf

Kişisel bilgiler

İş deneyimleri listesi
yer alır.

🧾 Çalıştırma Adımları
Projeyi IntelliJ IDEA veya başka bir IDE ile aç.

foto.jpg dosyasını src/main/resources/ klasörüne koy.

Maven bağımlılıklarını yükle (pom.xml → sağ tık → Reload Maven).

Ozgecmis.java dosyasını çalıştır.

PDF otomatik olarak proje dizininde oluşur.

