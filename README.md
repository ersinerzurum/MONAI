# 2D Nesne Segmentasyonu

Bu proje, 2D görüntülerdeki nesneleri segmentlemek için derin öğrenme kullanarak bir model eğitmek ve test etmek için geliştirilmiştir. Model, MONAI kütüphanesi ve PyTorch kullanılarak oluşturulmuş bir U-Net yapısını temel alır. Kullanıcı, farklı şekillerde nesneler oluşturabilir (daire, kare, dikdörtgen, üçgen, elips) ve bu nesneleri segmentlemek için modelin tahminlerini alabilir.

## Proje Adımları

1. **Gerekli Kütüphanelerin Yüklenmesi**:
   Projeyi çalıştırmadan önce, gerekli Python kütüphanelerini yüklemeniz gerekmektedir. Aşağıdaki adımları izleyerek gerekli kütüphaneleri yükleyebilirsiniz.

    ```bash
    pip install -r requirements.txt
    ```

2. **Veri Üretimi ve Eğitimi**:
   - Modeli eğitmek için sentetik veriler üretilir. Bu veriler, kullanıcı tarafından belirtilen şekillere (daire, kare, dikdörtgen, vb.) sahip rastgele görüntülerden oluşur.
   - Kullanıcıdan alınan nesne türüne göre etiketlenmiş veri setleri oluşturulur.
   
3. **Model Yapısı**:
   - **U-Net** tabanlı bir model, her iki şekilde de (görüntü ve etiket) eğitilmek üzere kullanılır.
   - **Dice Loss** fonksiyonu, modelin segmentasyon doğruluğunu artırmak için kullanılır.
   - Eğitilmiş model, her epokta kaydedilir.

4. **Tahmin ve Görselleştirme**:
   - Model eğitildikten sonra, belirtilen nesne türüne ait görüntüler üzerinde tahminler yapılır.
   - Tahminler, `tmp` klasöründe sıralı bir şekilde kaydedilir (örneğin, `img0.png`, `label0.png`, `pred0.png` gibi).
   - Sonuçlar görselleştirilir ve kaydedilen görüntülerle karşılaştırılır.

## Kullanım

1. **Nesne Türünü Seçme**:
   Proje, aşağıdaki şekiller için segmentasyon sağlar:
   - daire
   - kare
   - dikdörtgen
   - üçgen
   - elips

   Kullanıcıdan bu nesne türlerinden birini girerek işlem başlatılır. Model dosyasının yolu dinamik olarak oluşturulur.

2. **Modelin Eğitilmesi ve Kaydedilmesi**:
   Model, belirtilen nesne türüne göre eğitilir. Eğitim tamamlandıktan sonra model dosyası kaydedilir:
   
    ```python
    torch.save(model.state_dict(), "def_model.pth")
    ```

3. **Tahmin Yapma ve Sonuçların Kaydedilmesi**:
   Model eğitildikten sonra, her bir nesne türü için tahminler yapılır ve `tmp` klasörüne sıralı bir şekilde kaydedilir.

## Kurulum

### Gereksinimler:
- Python 3.7+
- PyTorch
- MONAI
- NumPy
- OpenCV
- Matplotlib

### Yükleme:

1. Projeyi kendi bilgisayarınıza klonlayın:

    ```bash
    git clone https://github.com/kullanici_adiniz/2D_Segmentation.git
    cd 2D_Segmentation
    ```

2. Gerekli kütüphaneleri yükleyin:

    ```bash
    pip install -r requirements.txt
    ```

### Modeli Eğitme

Modeli eğitmek için aşağıdaki kodu çalıştırabilirsiniz:

```python
python train.py
