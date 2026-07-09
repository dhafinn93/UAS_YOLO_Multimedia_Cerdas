# Deteksi Jalan Berlubang (Pothole Detection) menggunakan YOLOv8

Proyek ini adalah implementasi *Computer Vision* menggunakan model YOLOv8 untuk mendeteksi jalan berlubang, dibuat untuk memenuhi Ujian Akhir Semester (UAS) mata kuliah Multimedia Cerdas.

### 1. Fungsi/Fitur
* Mendeteksi keberadaan jalan berlubang (*pothole*) pada citra gambar.
* Memberikan penanda berupa kotak (*bounding box*) pada lokasi lubang.
* Menampilkan nilai probabilitas/akurasi keyakinan AI terhadap lubang yang dideteksi.

### 2. Cara Menjalankan (Instalasi)
Jika ingin menjalankan ulang proyek ini di Google Colab atau komputer lokal, Anda membutuhkan pustaka `ultralytics`.

Langlah 1: Silahkan Download Repo ini kemudian ekstrak atau di clone

Langkah 2: Persiapan Dataset
Tahap pertama adalah mengekstrak file `Dataset.zip` yang sudah saya kasih ke drive lalu diunggah ke dalam Google Colab agar gambar dapat dibaca oleh sistem.
!unzip -q Dataset.zip -d dataset_pothole --- ini digunakan untuk mengekstrak dataset dari zip.

Langkah 3: Instalasi Library
Menginstal pustaka `ultralytics` yang berisi algoritma YOLOv8 untuk kebutuhan *Computer Vision*.
!pip install ultralytics --- jalankan ini

Langkah 4: Melatih Model AI (Training)
Pada tahap ini, model dasar YOLOv8 (versi Nano) dilatih menggunakan dataset jalan berlubang selama 20 *epochs* untuk mempelajari pola visual dari jalan berlubang. Hasil dari proses ini adalah file "otak AI" bernama `best.pt`.

Langkah 5: Pengujian Model (Testing)
Setelah AI selesai dilatih, kita akan mengujinya menggunakan gambar-gambar jalan berlubang yang belum pernah ia lihat sebelumnya (di dalam folder *test*).

Langkah 6: Saya memakai dataset dari kaggle untuk lebih lengkapnya bisa klik link drive ini
https://drive.google.com/drive/folders/15rKBdk4JLd7YPPmAlG0r37sN83NupUSj?usp=drive_link

### 3. Cara Kerja
1. **Pengumpulan Data:** Menggunakan dataset gambar jalan berlubang (*pothole*) berformat YOLO.
2. **Pelatihan Model:** Model dasar YOLOv8 dilatih (*training*) menggunakan dataset tersebut untuk mempelajari pola visual dari jalan berlubang.
3. **Prediksi:** Skrip akan memuat bobot model hasil latihan (`best.pt`) dan membaca gambar baru. YOLO memproses piksel gambar tersebut dan mengembalikan koordinat lokasi yang dicurigai sebagai lubang beserta label akurasinya.

### 4. Tampilan Hasil
Berikut adalah bukti visual model AI berhasil mendeteksi jalan berlubang saat diuji coba:
<img width="736" height="416" alt="tes3" src="https://github.com/user-attachments/assets/1fd590b7-21d9-497d-8ad2-8fa773add19d" />

<img width="516" height="387" alt="tes2" src="https://github.com/user-attachments/assets/fe964887-af54-4b7c-803c-ba5b857a8102" />
