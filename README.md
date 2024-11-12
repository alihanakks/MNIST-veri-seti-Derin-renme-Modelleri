# MNIST Derin Öğrenme Modelleri ile Rakam Tanıma

Bu proje, MNIST veri seti ile iki farklı derin öğrenme modelinin eğitimini ve karşılaştırmasını yapmaktadır. Amaç, elle yazılmış rakamları doğru bir şekilde sınıflandırabilen bir model geliştirmektir. Projede TensorFlow ve Keras-Tuner gibi kütüphaneler kullanılmıştır.

## İçindekiler
- [Gereksinimler](#gereksinimler)
- [Proje Yapısı](#proje-yapısı)  
- [Veri Seti](#veri-seti)  
- [Modeller](#modeller)  
- [Eğitim ve Değerlendirme](#eğitim-ve-değerlendirme)
- [Model Performansları](#model-performansları)


## Gereksinimler
- Python 3.x
- TensorFlow
- Keras-Tuner
- Scikit-Learn, Pandas, Matplotlib, Seaborn, OpenCV, TQDM

Gerekli kütüphaneleri aşağıdaki komutla kurabilirsiniz:
```bash
pip install tensorflow keras-tuner scikit-learn pandas matplotlib seaborn opencv-python tqdm
```


## Proje Yapısı  
- Veri Hazırlama: prepare_data fonksiyonu, eğitim ve test veri kümelerini oluşturur.
- Model Eğitimi ve Değerlendirme: Model eğitimi sırasında plot_training_history ve get_best_epoch_details fonksiyonları ile eğitim ve doğrulama performansı izlenir.
- Model Kaydetme ve Yükleme: Eğitim sonrası en iyi modeli kaydedip tekrar yükleyebilirsiniz
  
## Veri Seti  
Bu projede MNIST veri seti kullanılmıştır. Veri seti, 28x28 boyutunda gri ölçekli 60.000 eğitim ve 10.000 test görüntüsü içerir. MNIST veri setini TensorFlow kütüphanesi aracılığıyla indirebilirsiniz:
```
from keras.datasets import mnist
(x_train, y_train), (x_test, y_test) = mnist.load_data()
```
## Modeller  
Projede iki farklı model bulunmaktadır:

-LeNet 
-MobilNetV2 Gelişmiş CNN Modeli (Hyperparameter Tuning ile)
  MObilnetV2 modelinin karmaşıklığı azaltılıp MNIST veri setine uygun şekilde düzenlenmeye çalışılmıştır.

## Eğitim ve Değerlendirme  
Model eğitimi sırasında Early Stopping ve Model Checkpoint yöntemleri ile eğitim süreci optimize edilmektedir. Eğitim ve doğrulama kayıpları ve doğrulukları plot_training_history fonksiyonu ile görselleştirilir.

Eğitim sürecindeki adımlar:

- Veri hazırlığı: Veriyi normalize ederek ve belirli bir batch boyutunda işleyerek model eğitimi için optimize edilir.
- Model eğitimi: Her iki model eğitim sırasında doğrulama veri setiyle test edilir.
- Hiperparametre optimizasyonu: Gelişmiş model, Keras-Tuner ile en uygun parametreleri bulacak şekilde optimize edilmiştir.
  
### Performans Metrikleri
 Her iki modelin performansı doğruluk (accuracy) ve kayıp (loss) değerleri ile değerlendirilir. En iyi epoch değerleri get_best_epoch_details fonksiyonu ile elde edilmiştir. plot_training_history fonksiyonu, eğitim sürecinde model performansını görselleştirir.
 
## Model Performansları
Bu bölümde, her bir modelin doğruluk, eğitim süresi ve diğer metrikleri hakkında kısa notlar bırakabilirsiniz. Aşağıdaki tabloyu, kendi sonuçlarınıza göre doldurabilirsiniz:

| Model Adı              | Doğruluk (%) | Kayıp (Loss) | Eğitim Süresi | Notlar                         |
|------------------------|--------------|--------------|---------------|--------------------------------|
| LeNet                  | 98.3         | 0.05         | 10 dk         | Temel model                    |
| MobilNetV2             | 94.4         | 0.18         | 63 dk         | Hiperparametre optimizasyonu   |


