# 🏭 Üretim Planlama ve Optimizasyon Simülasyonu

Bu proje, bir üretim tesisindeki işlerin farklı makineler arasında en verimli şekilde nasıl dağıtılacağını hesaplayan bir Java uygulamasıdır. Algoritma, toplam süreyi ve geçiş maliyetlerini en aza indirmek için **Dinamik Programlama (Dynamic Programming)** yöntemini kullanır.

## 🚀 Proje Hakkında
Üretim süreçlerinde her işin farklı makinelerde farklı işlem süreleri olabilir. Ayrıca, bir işten diğerine geçerken makineler arası geçiş maliyetleri (setup time) oluşabilir. Bu yazılım:
- Tüm makine ve iş kombinasyonlarını değerlendirir.
- En düşük maliyetli (minimum süre) rotayı belirler.
- Hangi işin hangi makinede yapılması gerektiğini adım adım raporlar.

### 🧠 Kullanılan Algoritma ve Yapılar
- **Dinamik Programlama (DP):** Karmaşık problemleri alt problemlere bölerek verimli çözüm sağlar.
- **Backtracking (Geriye İz Sürme):** Minimum maliyet hesaplandıktan sonra, en iyi rotayı bulmak için tabloda geriye doğru iz sürer.
- **Çok Boyutlu Diziler:** İşlem süreleri ve geçiş maliyetlerini saklamak için `int[][]` yapıları kullanılmıştır.

## 🛠️ Teknik Detaylar
- **Dil:** Java
- **Yöntem:** Minimum Path Optimization (En Kısa Yol Optimizasyonu)
- **Veri Yapıları:** DP Tablosu ve Matrisler

## 💻 Nasıl Çalıştırılır?
1. `UretimPlanlama.java` dosyasını bilgisayarınıza indirin.
2. Terminal veya komut istemcisini açın ve dosyayı derleyin:
   ```bash
   javac UretimPlanlama.java
