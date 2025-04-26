# Alzheimer MRI Classification

## Deskripsi
Proyek ini bertujuan untuk membangun model klasifikasi untuk mendeteksi penyakit Alzheimer menggunakan data pemindaian otak MRI. Model ini mengklasifikasikan data ke dalam empat kategori:

1. **Penyakit Alzheimer (AD)**
2. **Normal Kognitif (CN)**
3. **Gangguan Kognitif Ringan Awal (EMCI)**
4. **Gangguan Kognitif Ringan Akhir (LMCI)**

## Alat

- **Python**
- **TensorFlow & Keras**: Untuk pembangunan model dan pelatihan.
- **OpenCV**: Untuk pemrosesan gambar.
- **Matplotlib & Seaborn**: Untuk visualisasi data dan hasil model.
- **Kaggle API**: Untuk mengunduh dataset dari Kaggle.
- **Google Colab**: Untuk pelatihan model menggunakan GPU/TPU.

## Instalasi

1. Install dependency yang dibutuhkan:

    ```bash
    pip install -r requirements.txt
    ```

2. Unduh dataset dari Kaggle:
   - Salin file `kaggle.json` ke folder `~/.kaggle/`.
   - Gunakan perintah berikut untuk mengunduh dataset:

        ```bash
        !kaggle datasets download -d abdullahtauseef2003/adni-4c-alzheimers-mri-classification-dataset
        !unzip adni-4c-alzheimers-mri-classification-dataset.zip
        ```

3. Tentukan path dataset di folder yang sesuai untuk digunakan dalam pemrosesan dan pelatihan model.

## Penggunaan

1. Persiapkan data: gunakan `ImageDataGenerator` untuk memuat dan menyiapkan data pelatihan, validasi, dan pengujian.
   
2. Pelatihan model:
   - Menyusun model klasifikasi menggunakan **EfficientNetB4** yang di-tune sebagai base model kemudian ditambahkan dengan Conv2D dan Pooling Layer.
   - Latih model menggunakan data yang telah disiapkan dan simpan model terbaik menggunakan callback **EarlyStopping** dan **ModelCheckpoint**.
   - Membuat plot akurasi dan loss model selama masa training.

3. Evaluasi model pada data uji menggunakan metrik akurasi.

4. Simpan model terbaik ke dalam format lain yaitu SavedModel, TF-Lite dan TFJS.

4. Inferensi atau menggunakan model untuk memprediksi kategori pada gambar MRI yang belum pernah dilihat sebelumnya.

## Struktur Proyek

```
submission
├───tfjs_model
| ├───group1-shard1of1.bin
| └───model.json
├───tflite_model
| ├───model.tflite
| └───label.txt
├───saved_model
| ├───saved_model.pb
| └───variables
├───Proyek_Klasifikasi_Gambar.ipynb
├───README.md
└───requirements.txt          

```

## Hasil Model

- **Akurasi pelatihan**: 95.2% 
- **Akurasi validasi**: 97.7%
- **Akurasi pengujian**: 99.1%


## Lisensi

Proyek ini dilisensikan di bawah [MIT License](LICENSE).