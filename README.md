# MONAI 2D/3D Object Segmentation

Bu repo, MONAI kütüphanesi ile 2D ve 3D nesne segmentasyonu yapmayı amaçlayan bir başlangıç rehberidir. Model eğitimi, test ve segmentasyon işlemleri için PyTorch ve CUDA kullanılacaktır.

## Başlangıç

Bu bölüm, projeyi nasıl başlatacağınız ve gerekli ortamı nasıl kuracağınız konusunda rehberlik edecektir.

### Gereksinimler

Bu proje, PyTorch ve MONAI kütüphanesini kullanarak segmentasyon modelleri oluşturmanıza olanak sağlar. Aşağıdaki yazılımlar ve kütüphaneler gereklidir:

- Python 3.x (Python 3.6 ve sonrası)
- PyTorch (CUDA destekli, GPU kullanımı için)
- MONAI
- NumPy
- Matplotlib (Opsiyonel, görselleştirme için)

## Ortam Kurulumu

Projeyi çalıştırmak için önce bir Python sanal ortamı oluşturmanız gerekecek. Adım adım nasıl kurulacağı aşağıda belirtilmiştir.

### 1. Python Ortamı Oluşturun:

```bash
python -m venv monai-segmentation-env
```

### 2. Ortamı Aktive Edin:

**Windows:**

```bash
monai-segmentation-env\Scripts\activate
```

**Linux:**

```bash
monai-segmentation-env/bin/activate
```

### 3. Gerekli Kütüphaneleri Yükleyin:

```bash
pip install torch torchvision torchaudio
pip install monai
pip install matplotlib numpy
```
### 4. CUDA Destekli PyTorch Yüklemek İçin (GPU Kullanımı):

CUDA destekli versiyonları yüklemek için [PyTorch İndirme Sayfası](https://pytorch.org/get-started/locally/) üzerinden uygun versiyonu seçebilirsiniz.

## Kullanım

Bu bölümde, verisetlerini nasıl kullanabileceğiniz, eğitim ve test işlemleri hakkında bilgi verilecektir.

### Verisetleri

Bu projede, 2D ve 3D segmentasyon modelleri eğitilebilir. Segmentasyon işlemi için kullanacağınız verisetinin uygun formatta olması gerekmektedir. Yaygın formatlar şunlardır:

- **2D segmentasyon:** .png, .jpg gibi resim dosyaları.
- **3D segmentasyon:** NIfTI formatında .nii veya .nii.gz dosyaları.

### Örnek Verisetleri

MONAI'nin sağladığı örnek verisetleri için [MONAI Datasets](https://monai.io/datasets) adresini ziyaret edebilirsiniz. Burada, medikal görüntüler gibi çeşitli segmentasyon verisetleri mevcuttur.

Verisetini indirip, uygun formatta olduğundan emin olduktan sonra, eğitim ve test işlemleri için kullanabilirsiniz.
