# Tugas-2-Kecerdasan-Artifisial-2208107010064  

## Jenis Kasus  
**Klasifikasi Gambar**  

## Dataset yang Digunakan  
Dataset yang digunakan adalah **Cats vs Dogs Dataset**, yang berisi gambar-gambar kucing dan anjing yang sudah dipisahkan ke dalam direktori `train` dan `validation`. Dataset ini tersedia di [Cats and Dogs Dataset](https://www.tensorflow.org/datasets/catalog/cats_vs_dogs).  

### Informasi Dataset  
- **Jumlah Fitur:**  
  Setiap gambar diproses menjadi dimensi 160x160 piksel dengan 3 saluran warna (RGB), sehingga jumlah fitur (input) untuk setiap gambar adalah: **76,800 fitur**.  

- **Jumlah Label:**  
  Dataset ini memiliki **2 kelas**, yaitu:  
  1. Kucing  
  2. Anjing  

## Jenis Jaringan Saraf Tiruan yang Digunakan  
Model ini menggunakan **Convolutional Neural Network (CNN)**, yang sangat efektif untuk tugas klasifikasi gambar.  

## Jenis Optimisasi  
Model ini menggunakan **Adam optimizer**, sebuah algoritma optimisasi adaptif yang populer dalam pelatihan jaringan saraf.  

## Jenis Fungsi Aktivasi yang Digunakan  
- **Lapisan Konvolusi & Dense Pertama:** Menggunakan fungsi aktivasi **ReLU (Rectified Linear Unit)**.  
- **Lapisan Output:** Menggunakan fungsi aktivasi **Softmax**, yang mengubah output menjadi probabilitas untuk klasifikasi dua kelas.  

## Jumlah Hidden Layer  
- **Lapisan Konvolusi Pertama:** 32 filter  
- **Lapisan Konvolusi Kedua:** 64 filter  
- **Lapisan Konvolusi Ketiga:** 128 filter  
- **Lapisan Konvolusi Keempat:** 256 filter  
- **Lapisan Dense Pertama:** 512 node  

## Jumlah Total Hidden Node per Layer  
Total jumlah node (termasuk output) pada model ini adalah: **514 node**.  

## Jumlah Total Bobot (Weight)  
Jumlah total bobot (weights) yang digunakan dalam model ini adalah **sekitar 1.2 juta parameter**.  

## Deskripsi Model  
Model CNN ini terdiri dari empat lapisan konvolusi yang dilanjutkan dengan lapisan Dense untuk klasifikasi 2 kelas gambar (Kucing dan Anjing). Setiap lapisan konvolusi diikuti dengan lapisan pooling untuk mengurangi dimensi data, dan lapisan Dense digunakan untuk menghubungkan hasil ekstraksi fitur ke kelas output.  

- **Fungsi Aktivasi:**  
  - ReLU digunakan di lapisan tersembunyi untuk memperkenalkan non-linearitas.  
  - Softmax digunakan di lapisan output untuk klasifikasi multi-kelas.  
- **Pooling:**  
  Setiap lapisan konvolusi diikuti oleh lapisan pooling untuk mereduksi dimensi data secara efisien.  
- **Optimizer:**  
  Menggunakan Adam optimizer untuk pelatihan model yang stabil dan cepat.  

## Langkah-Langkah Eksperimen  
1. **Download Dataset:** Dataset diunduh dan diekstraksi secara otomatis.  
2. **Data Augmentation:** Data gambar diperbesar dengan `RandomFlip`, `RandomRotation`, dan `RandomZoom`.  
3. **Membangun Model:** Model CNN dengan 4 lapisan konvolusi dan lapisan Dense.  
4. **Training Model:** Model dilatih selama 15 epoch dengan callback Early Stopping untuk mencegah overfitting.  
5. **Evaluasi Model:** Akurasi dan loss model divisualisasikan untuk memantau performa.  
6. **Prediksi Gambar Baru:** Model digunakan untuk memprediksi gambar baru.  


## Saved Model  
Model yang telah dilatih disimpan dalam format `.h5` dan dapat digunakan kembali untuk inferensi. File model: `cats_and_dogs_cnn_model.h5`.  

## Dependencies  
- TensorFlow 2.x  
- NumPy  
- Matplotlib  
- Python 3.x  
