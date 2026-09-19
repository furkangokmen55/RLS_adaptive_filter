# RLS Adaptive Filter

`padasip` kütüphanesi kullanılarak **RLS (Recursive Least Squares)** ve **LMS (Least Mean Squares)** adaptif filtreleme algoritmalarının sentetik veri üzerinde karşılaştırıldığı bir Jupyter Notebook çalışması. Filtrelerin gürültülü bir hedef sinyali ne kadar iyi takip edebildiği, farklı öğrenme oranlarıyla (`mu`) nasıl değiştiği ve ağırlıkların/hatanın istatistiksel davranışı inceleniyor.

## İçerik

1. **Sentetik veri üretimi:** 4 girişli, gürültü eklenmiş doğrusal bir hedef sinyal (`d = 2x0 + 0.1x1 - 4x2 + 0.5x3 + gürültü`) oluşturulur.
2. **Filtre karşılaştırması:**
   - RLS algoritması, `mu = 0.9` ile
   - RLS algoritması, `mu = 0.1` ile
   - LMS algoritması, `mu = 0.1` ile
   
   Her biri hedef sinyali ne kadar hızlı ve doğru öğrendiğine göre grafiklerle karşılaştırılıyor.
3. **Analiz:** Giriş/ağırlık/hata değerleri bir DataFrame'de birleştirilip betimsel istatistikler, korelasyon matrisi (`corr()` + heatmap) ve ağırlıklar/çıktı/hata için otokorelasyon grafikleri çıkarılıyor.
4. **Notebook'un sonunda** filtrelemeyle doğrudan ilgisi olmayan, ayrı birkaç alıştırma da var: özyinelemeli (recursive) Fibonacci hesaplama ve fonksiyonel denklem çözme örnekleri — muhtemelen aynı çalışma oturumunda tutulan pratik notlar.

## Gereksinimler

```
pip install padasip numpy pandas matplotlib seaborn
```

## Çalıştırma

Notebook'u Jupyter veya VS Code üzerinden açıp hücreleri sırayla çalıştırman yeterli. `N = 500` örnek sayısı ve `mu` değerleri değiştirilerek filtrelerin davranışı farklı senaryolarda gözlemlenebilir.
