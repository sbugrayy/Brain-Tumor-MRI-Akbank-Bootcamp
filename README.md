# Akbank Derin Öğrenme Bootcamp: Brain Tumor MRI Classification

## Proje Özeti  
Bu proje, MRI görüntüleri kullanarak beyin tümörlerini sınıflandırmayı amaçlar. CNN tabanlı bir model geliştirilmiş; modelin kararları Grad-CAM ile görselleştirilerek açıklanabilirlik sağlanmıştır.

## Veri Seti  
- **Ad:** masoudnickparvar / brain-tumor-mri-dataset  
- **Link:** https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset  
- **Sınıflar:** Glioma, Meningioma, Pituitary, No Tumor  
- **Toplam Görüntü:** Yaklaşık 7.000 civarı (train + test)  

## Kullanılan Yöntemler  
1. **Veri Ön İşleme & Augmentation**  
   - `ImageDataGenerator` ile rescale, rotation, shift, zoom, flip, brightness dönüşümleri  
   - Train / Validation split ile modelin genelleme kabiliyeti test edildi  

2. **Model Mimarisi**  
   - Baseline CNN: Conv → Pool → Dropout → Dense katmanlar  
   - Opsiyonel: Transfer learning (EfficientNetB0) ile fine-tuning  

3. **Eğitim & Hiperparametre Ayarı**  
   - Callbacks: ModelCheckpoint, EarlyStopping, ReduceLROnPlateau  
   - Denenen parametreler: learning rate, batch size, dropout oranı, optimizer  

4. **Değerlendirme**  
   - Accuracy & Loss grafikleri  
   - Confusion matrix & classification report  
   - Grad-CAM ile modelin hangi bölgeleri dikkate aldığı  

## Sonuçlar  
- **En iyi validation accuracy:** *(buraya kendi değerini yaz)*  
- Confusion matrix ve classification report ile sınıf bazlı performans analizi yapılmıştır.  
- Grad-CAM görselleştirmeleri modelin görüntülerdeki tümör bölgelerini tespit etmede mantıklı bölgeleri kullandığını göstermektedir / göstermemektedir.  

## Gelecekteki Geliştirmeler  
- Daha güçlü transfer learning modelleri ile fine-tuning  
- Class imbalance var ise oversampling / class weights uygulama  
- Segmentasyon + sınıflandırma birleşik modeller (örneğin U-Net + CNN)  

## Çalıştırma Talimatları  
1. Kaggle üzerinde yeni bir notebook aç.  
2. “Add data” kısmından **brain-tumor-mri-dataset** dataset’ini ekle.  
3. Yukarıdaki `project_notebook.ipynb` dosyasını yükle ya da hücreleri yapıştırarak çalıştır.  
4. Model eğitiminden sonra sonuçları ve Grad-CAM görsellerini incele.

## Kaggle Linki
[brain-tumor-mri-classification](https://www.kaggle.com/code/bugrayildirim/brain-tumor-mri-classification)

## Lisans & Teşekkür  
- Bu proje sadece eğitim amaçlıdır.  
- Veri seti için [Masoud Nickparvar](https://www.kaggle.com/masoudnickparvar) ve Kaggle topluluğuna teşekkürler.  
