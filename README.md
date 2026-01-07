# 🔒 İşletim Sistemleri: Deadlock Simülasyonu ve Performans Analizi

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Durum-Tamamlandı-green?style=for-the-badge)

Bu proje, İşletim Sistemleri (Operating Systems) dersi kapsamında; **Ölümcül Kilitlenme (Deadlock)** durumlarını simüle etmek, farklı çözüm stratejilerini (Prevention, Avoidance, Detection) uygulamak ve bunların sistem üzerindeki maliyetlerini analiz etmek amacıyla geliştirilmiştir.

## 🎯 Projenin Amacı
Modern işletim sistemlerinde sınırlı kaynakların (CPU, RAM, I/O vb.) paylaşımı sırasında oluşan Deadlock problemini çözmek için kullanılan algoritmaların; **İşlemci Yükü (Overhead)**, **İşlem Süresi** ve **Veri Kaybı (Wasted Value)** açısından kıyaslanmasıdır.

## ⚙️ Özellikler & Desteklenen Algoritmalar

Proje modüler bir yapıya sahiptir ve aşağıdaki yaklaşımları destekler:

### 1. Önleyici (Prevention)
- **Resource Ordering:** Kaynaklara hiyerarşik numara vererek "Döngüsel Bekleme" (Circular Wait) şartını matematiksel olarak engeller.

### 2. Kaçınma (Avoidance)
- **Banker's Algorithm:** Dijkstra'nın ünlü algoritması. Sistem her kaynak talebinde "Güvenli Durum" (Safe State) analizi yapar.

### 3. Tespit ve Kurtarma (Detection & Recovery)
Sistemde döngü (Cycle) oluştuğunda DFS ile tespit eder ve bir kurban seçer:
- **Random Victim:** Rastgele bir işlem sonlandırılır.
- **Minimum Victim:** En az ilerleme kaydeden işlem (en düşük maliyetli) sonlandırılır.
- **Maximum Victim:** En fazla kaynak tutan işlem sonlandırılır (Starvation çözümü için).
- **Valued Victim:** Öncelik değeri (Priority) en düşük olan işlem sonlandırılır.

### 4. Alternatif Yaklaşımlar
- **Rollback:** Deadlock oluştuğunda işlem öldürülmez, zaman geriye sarılarak (state reset) işlem baştan başlatılır.

---

## 📂 Proje Yapısı

```bash
📦 Deadlock-Simulation
 ┣ 📂 req
 ┃ ┣ 📂 scenarios       # Test senaryoları (JSON formatında)
 ┃ ┗ 📜 options.json    # Simülasyon ayar dosyası
 ┣ 📂 scripts
 ┃ ┗ 📂 algorithms      # Algoritma modülleri (Banker, RandomVictim vb.)
 ┣ 📜 project.py        # Simülasyon Çekirdeği (Kernel)
 ┣ 📜 graphic.py        # Matplotlib grafik çizim modülü
 ┣ 📜 index.py          # Ana başlatıcı (Main Launcher)
 ┗ 📜 README.md         # Proje dokümantasyonu
