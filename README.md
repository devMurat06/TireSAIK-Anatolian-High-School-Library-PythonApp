<div align="center">
  <h1>📚 ŞAİK Kütüphane Yönetim Sistemi (Pro Serisi)</h1>
  <p>
    <strong>Okullar ve eğitim kurumları için geliştirilmiş, oyunlaştırma ve yapay zeka destekli yeni nesil kütüphane yönetim ekosistemi.</strong>
  </p>
  
  <p>
    <img src="https://img.shields.io/badge/Python-3.10+-blue.svg" alt="Python Version" />
    <img src="https://img.shields.io/badge/GUI-Tkinter%2FCustomTkinter-brightgreen.svg" alt="GUI" />
    <img src="https://img.shields.io/badge/AI-Groq%20Cloud-orange.svg" alt="AI Integration" />
    <img src="https://img.shields.io/badge/Database-SQLite-lightgrey.svg" alt="Database" />
  </p>
</div>

---

## 🌟 Proje Özeti

ŞAİK Kütüphane Yönetim Sistemi standart bir fiş/kayıt programı değil; yapay zeka entegrasyonu, veri analizi ve öğrenci teşvik (oyunlaştırma) metodolojisini bir araya getiren interaktif bir platformdur. Amacı, kütüphane işlemlerini hızlandırmakla kalmayıp öğrencilerin kitap okuma alışkanlıklarını eğlenceli bir rekabet ortamına dönüştürmektir.

---

## 🚀 Öne Çıkan Modüller ve Özellikler

### 🤖 1. Yapay Zeka Asistanı (Groq AI)
Sistem yöneticileri (öğretmenler) için entegre edilmiş, **Llama 3.3 (70B)** tabanlı akıllı asistan.
- **Canlı Veri Analizi:** Asistan, veritabanına anlık bağlanarak gecikmiş kitapları, toplam ödünç sayısını ve öğrenci kayıtlarını tek soruda özetler.
- **Hızlı Yönlendirme:** Menülerde kaybolmadan "Şu an kütüphanenin güncel durumu nedir?" diyerek rapor almanızı sağlar.

### 🏆 2. Oyunlaştırma (Gamification) & ŞAİK Wrapped
Öğrencilerin okuma şevkini artırmak için tasarlanmış özel modüller:
- **Kitap Kurdu Liderlik Tablosu:** En çok sayfa ve kitap okuyan öğrencilerin rekabet tablosu.
- **Rozet Sistemi:** Belirli okuma hedeflerine ulaşan öğrencilere dijital teşvik rozetleri.
- **ŞAİK Wrapped (Yıllık Özet):** Yıl sonunda "Yılın Kitabı", "Yılın Yazarı", "En Popüler Tür" istatistiklerini *Spotify Wrapped* tarzında görselleştiren rapor ekranı.

### 🏷️ 3. Profesyonel Barkod ve Envanter Yönetimi
- Kameralı cihazlar üzerinden (OpenCV & pyzbar) **fiziksel barkod tarama** ve hızlı ödünç/iade.
- Sisteme yeni eklenen kitaplar için **otomatik barkod etiketi oluşturma** ve dışa aktarma (python-barcode).
- Kaybolmaları önlemek için akıllı "Geciken Kitaplar Kontrol Paneli".

### 📥 4. Güçlü İçe/Dışa Aktarım (I/O) ve Raporlama
- **Excel Entegrasyonu:** Teknolojiye hızlı geçiş; Binlerce e-Okul veya okul sisteminden alınmış öğrenci/kitap verisini saniyeler içinde Excel (.xlsx) ile sisteme gömme (openpyxl).
- **PDF & CSV:** Verileri resmi evraklara dökmek için PDF ve Microsoft Excel tabanlı CSV çıktısı alabilme (fpdf2).

### 🎮 5. Öğrenci Molası (Egzersiz ve Oyunlar)
Öğrenci modunda erişilebilen ve öğrencilerin kütüphanedeki teknolojik alanlarda geçireceği molaları eğlenceli kılan zeka egzersizleri ve klasik oyunlar:
- *Oyunlar:* Pong, Yılan (Snake), Flappy Bird.
- *Egzersizler:* Hızlı Matematik, Flashcard İngilizce, Kelime Karıştırma, Hafıza Geliştirme.

---

## 🔒 Güvenlik ve Roller

Sistem, yetki karmaşalarını önlemek adına **İki Katmanlı (Rol Bazlı)** mimari ile tasarlanmıştır. Güvenlik gereği parolaların değiştirilmesi önerilmektedir. İşletim sistemi arka planında her iki rol için izole işlemler yürütülür.

| Kullanıcı Profili | Varsayılan Parola | Erişim Yetkisi |
| :--- | :--- | :--- |
| **Yönetici / Öğretmen** | `saik2026` | Tam Yetki (AI, Ekle/Sil, Veritabanı, Ayarlar, Wrapped) |
| **Öğrenci / Üye** | `ogrenci+` | Salt Okunur (Kitap Arama, Rezervasyon, Oyunlar) |

> **🚨 Not:** Yapay zeka asistanı, veri sızıntılarını (prompt injection) engellemek adına sistem parolalarına körleştirilmiş (gizlenmiş) şekilde tasarlanmıştır.

---

## 🛠️ Teknik Altyapı ve Kurulum

Sistem yüksek performanslı ve "kendi kendine yeten (self-contained)" bir yapıya sahiptir.

### Sistem Gereksinimleri
- **İşletim Sistemi:** Windows 10/11, macOS, Linux
- **Python Sürümü:** Python 3.10 veya üzeri
- **Donanım:** Barkod tarama özelliği için Webcam (zorunlu değil).

### Bağımlılıkların Kurulumu
Projenin ihtiyaç duyduğu yan kütüphaneleri yüklemek için aşağıdaki komutu terminalinizde çalıştırın:
```bash
pip install customtkinter opencv-python pyzbar python-barcode pillow fpdf2 matplotlib openpyxl urllib3
```

### Projeyi Başlatma
Veritabanı (SQLite) ilk çalıştırmada otomatik olarak kendini kuracak, modülleri yapılandıracak ve `okul_kutuphanesi_pro_v7.db` dosyasını ayağa kaldıracaktır.

```bash
python3 library_app.py
```

---

## 📂 Dosya ve Mimari Yapısı

```
ŞAİK Kütüphane/
├── library_app.py              # Uygulamanın ana beyni ve UI merkezi
├── okul_kutuphanesi_pro_v7.db  # Güvenli, lokal SQLite Veritabanı (Otomatik oluşur)
├── README.md                   # Proje dokümantasyonu (Bu dosya)
├── logo.png                    # Uygulama ikonu ve marka kimliği
├── barkodlar/                  # (Klasör) Barkod modülüyle üretilen resimler buraya düşer
└── ornek_kitaplar.xlsx         # (Opsiyonel) Sisteme yükleyebileceğiniz test Excel dosyası
```

---

<div align="center">
  <p><i>Kütüphaneleri sıkıcı depolar olmaktan çıkarıp, dinamik bir öğrenme merkezine dönüştürmek için tasarlandı.</i></p>
  <b>© 2026 devMurat06 Software & AI Development Solutions</b>
</div>

N♥️