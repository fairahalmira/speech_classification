---

# 🎧 Klasifikasi Suara Hewan dengan CNN

Proyek ini membangun dan melatih sebuah **Convolutional Neural Network (CNN)** untuk mengklasifikasikan suara hewan yang ditiru manusia ke dalam 5 kategori.
Model dilatih menggunakan fitur **MFCC** yang diekstrak dari rekaman audio, dan diimplementasikan dengan **PyTorch**.

---

## 🐾 Kategori Suara

* 🐄 **Sapi** — *moo*
* 🐈 **Kucing** — *meow*
* 🐕 **Anjing** — *woof*
* 🐐 **Kambing** — *mbee*
* 🐦 **Burung** — *tweet*

---

## 📁 Dataset

Dataset diperoleh dari **rekaman suara manusia** yang meniru suara hewan-hewan di atas.
Setiap kelas memiliki **15 rekaman audio**, masing-masing dengan:

* **10 rekaman** untuk training
* **5 rekaman** untuk testing

Semua rekaman disimpan di dalam folder `./data/` dengan struktur:

```
data/
├── moo/
├── meow/
├── woof/
├── mbee/
├── tweet/
```

Setiap file adalah `.wav` berdurasi 2 detik, disimpan dengan nama sesuai label.

---

## 🔄 Preprocessing Data

- ✅ **Voice Activity Detection:** menghapus bagian diam  
- ✅ **Normalisasi amplitudo:** menyeragamkan skala amplitudo  
- ✅ **Padding/Cropping:** menyeragamkan panjang rekaman  
- ✅ **Ekstraksi fitur MFCC:** menghasilkan 40 koefisien per frame  
- ✅ **Membuat dataset custom:** menyesuaikan format untuk PyTorch  
- ✅ **Membagi data:** menjadi data train dan test
---

## 🏗️ Model

Model CNN sederhana dengan arsitektur:

* 2 blok Conv2D + ReLU + MaxPooling
* Flatten layer
* Fully Connected Layer → output 5 kelas
* Loss: CrossEntropyLoss
* Optimizer: Adam
* Epochs: 100

---

## 📈 Hasil Pelatihan

* Model mencapai akurasi **100%** pada dataset kecil ini (train & test).
* Visualisasi loss & akurasi selama training juga disertakan dalam notebook.
* Laporan klasifikasi (precision, recall, f1-score) ditampilkan.

📌 *Catatan:*
Akurasi tinggi ini wajar karena dataset sangat kecil dan tidak bervariasi. Untuk aplikasi nyata, diperlukan dataset yang lebih besar dan beragam.

---

## 🚀 Uji Coba Model

Setelah dilatih, model dapat digunakan untuk mengklasifikasikan **rekaman suara baru** secara langsung:

* Merekam audio dengan mikrofon.
* Mengekstrak fitur MFCC.
* Mengeluarkan prediksi label dengan confidence untuk masing-masing kelas.

Contoh output:

```
moo: 0.00%
meow: 0.00%
woof: 99.87%
mbee: 0.00%
tweet: 0.13%

Prediksi: woof
```

---

## 📦 File Penting

```
.
├── vocal.ipynb              # Notebook berisi seluruh proses
├── data/                    # Folder dataset audio
├── vowel_cnn.pth            # Model terlatih (disimpan)
├── vowel_formants_comparison.png  # Visualisasi formant
├── README.md                # Penjelasan proyek ini
```

---

## 📝 Cara Menjalankan

### Persyaratan

* Python 3.13.3
* PyTorch
* librosa
* sounddevice
* soundfile
* matplotlib
* scikit-learn
* Jupyter Notebook

### Langkah

1️⃣ Clone repo & masuk ke folder:

```bash
git clone <link-repo>
cd speech_classification
```

2️⃣ Install dependencies:

```bash
pip install -r requirements.txt
```

3️⃣ Jalankan notebook:

```bash
jupyter notebook vocal.ipynb
```

4️⃣ Ikuti langkah-langkah di dalam notebook untuk melatih & menguji model.

---

## 📚 Referensi

* [PyTorch documentation](https://pytorch.org/docs/stable/index.html)
* [Librosa documentation](https://librosa.org/doc/latest/index.html)
* [Formant frequency reference](https://biomed.papers.upol.cz/pdfs/bio/2007/02/31.pdf)

---

## 👨‍💻 Kontributor

* Nama: \[FairahAlmira]
* Univ: \[Institut Teknologi Padang]
* Program: \[AI Development @ Infinite Learning]

---

