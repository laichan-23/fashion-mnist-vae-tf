# Fashion-MNIST Variational Autoencoder (VAE) with TensorFlow

Proyek ini adalah implementasi **Variational Autoencoder (VAE)** menggunakan **TensorFlow** dan **Keras**. Model ini dilatih menggunakan dataset **Fashion-MNIST** untuk mempelajari representasi latent (tersembunyi) dari gambar pakaian dan merekonstruksinya kembali.

## 📋 Deskripsi Proyek

Variational Autoencoder (VAE) adalah jenis model generatif yang belajar memetakan input ke dalam distribusi probabilitas di ruang latent, kemudian mengambil sampel dari distribusi tersebut untuk merekonstruksi data asli.

Dalam notebook ini, kita melakukan:
1.  **Preprocessing Data:** Normalisasi dan reshaping dataset Fashion-MNIST.
2.  **Membangun Arsitektur VAE:**
    * **Encoder:** Menggunakan Convolutional Neural Network (Conv2D) untuk memetakan gambar ke `z_mean` dan `z_log_var`.
    * **Sampling Layer:** Menggunakan *reparameterization trick* untuk memungkinkan backpropagation.
    * **Decoder:** Menggunakan Conv2DTranspose untuk mengembalikan vektor latent menjadi gambar.
3.  **Custom Training Loop:** Mengimplementasikan `train_step` kustom untuk menangani KL Divergence loss dan Reconstruction loss.
4.  **Visualisasi:** Menampilkan hasil rekonstruksi gambar dan plot distribusi *Latent Space*.

## 🛠️ Teknologi yang Digunakan

* **Python 3.x**
* **TensorFlow 2.x / Keras**
* **NumPy**
* **Matplotlib** (untuk visualisasi)

## 📂 Struktur Model

* **Input:** Gambar Grayscale 32x32x1 (setelah padding).
* **Latent Dimension:** 2 (memungkinkan visualisasi 2D yang mudah).
* **Encoder:** 3 Layer Conv2D -> Flatten -> Dense.
* **Decoder:** Dense -> Reshape -> 3 Layer Conv2DTranspose.

## 🚀 Cara Menjalankan

1.  Clone repositori ini:
    ```bash
    git clone [https://github.com/username-kamu/fashion-mnist-vae-tf.git](https://github.com/username-kamu/fashion-mnist-vae-tf.git)
    ```
2.  Pastikan library yang dibutuhkan sudah terinstall:
    ```bash
    pip install tensorflow numpy matplotlib
    ```
3.  Jalankan file notebook `VAE_1.ipynb` menggunakan Jupyter Notebook atau Google Colab.

## 📊 Hasil Visualisasi

### 1. Rekonstruksi Gambar
Model mampu merekonstruksi gambar pakaian dari dataset validasi dengan cukup baik setelah 30 epoch.

### 2. Latent Space (Ruang Latent)
Visualisasi scatter plot dari `z_means` menunjukkan bagaimana model mengelompokkan berbagai jenis pakaian (seperti sepatu, baju, tas) di dalam ruang 2D.

![Latent Space](path_to_your_image_if_you_have_one.png)

## 📝 Catatan
Model encoder dan decoder disimpan dalam format `.h5` di akhir eksekusi:
* `vae_fashion_encoder.h5`
* `vae_fashion_decoder.h5`

## 👤 Author
Dibuat oleh [Nama Kamu]
