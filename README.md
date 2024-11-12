# MNIST Derin Öğrenme Modelleri ile Rakam Tanıma

Bu proje, MNIST veri seti ile iki farklı derin öğrenme modelinin eğitimini ve karşılaştırmasını yapmaktadır. Amaç, elle yazılmış rakamları doğru bir şekilde sınıflandırabilen bir model geliştirmektir. Projede TensorFlow ve Keras-Tuner gibi kütüphaneler kullanılmıştır.

## İçindekiler
- [Gereksinimler](#gereksinimler)
- [Proje Yapısı](##Proje-yapısı)
- [Veri Seti](#veri-seti)
- [Modeller](#modeller)
- [Eğitim ve Değerlendirme](#eğitim-ve-değerlendirme)
- [Model Performansları](#model-performansları)
- [Kurulum ve Çalıştırma](#kurulum-ve-çalıştırma)

## Gereksinimler
- Python 3.x
- TensorFlow
- Keras-Tuner
- Scikit-Learn, Pandas, Matplotlib, Seaborn, OpenCV, TQDM

Gerekli kütüphaneleri aşağıdaki komutla kurabilirsiniz:
```bash
pip install tensorflow keras-tuner scikit-learn pandas matplotlib seaborn opencv-python tqdm
```
## Proje yapısı (## Proje-yapısı)
- Veri Hazırlama: prepare_data fonksiyonu, eğitim ve test veri kümelerini oluşturur.
- Model Eğitimi ve Değerlendirme: Model eğitimi sırasında plot_training_history ve get_best_epoch_details fonksiyonları ile eğitim ve doğrulama performansı izlenir.
- Model Kaydetme ve Yükleme: Eğitim sonrası en iyi modeli kaydedip tekrar yükleyebilirsiniz.
