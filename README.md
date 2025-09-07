# Proyek Capstone: Klasifikasi Tweet Bencana Alam

Proyek ini adalah tugas akhir untuk program **Student Development Initiative IBM X Hacktiv8**. Notebook `Capstone_IBM_x_Hacktiv8.ipynb` berisi implementasi lengkap dari proyek ini.

---

## Deskripsi Proyek (Overview)

Proyek ini bertujuan untuk membangun sebuah sistem cerdas yang mampu menganalisis dan mengklasifikasikan cuitan (tweet) di media sosial untuk mengidentifikasi laporan bencana alam yang relevan. Keunikan proyek ini terletak pada metodologinya yang sepenuhnya mengandalkan **AI Agent**. Agent ini dibangun menggunakan framework **LangChain** dan dirancang khusus untuk berinteraksi dengan data tabular (Pandas DataFrame), memungkinkannya menjalankan analisis kompleks melalui perintah bahasa natural.

---

## Dataset

Dataset yang digunakan dalam proyek ini adalah **"Natural Disasters Tweets"** dari platform Kaggle. Dataset ini menjadi dasar bagi agent untuk melakukan analisis dan klasifikasi.

* **Link Dataset:** [https://www.kaggle.com/datasets/vstepanenko/natural-disasters-tweets](https://www.kaggle.com/datasets/vstepanenko/natural-disasters-tweets)

---

## Proses Analisis (Analysis Process)

Alur kerja analisis yang diimplementasikan dalam notebook ini adalah sebagai berikut:
1.  **Konfigurasi Environment:** Menginstal semua library yang diperlukan, termasuk `langchain`, `langchain_experimental`, `pandas`, dan `replicate`.
2.  **Pemuatan Data:** Dataset `train.csv` dimuat ke dalam sebuah DataFrame Pandas, yang berfungsi sebagai "ruang kerja" utama bagi AI Agent.
3.  **Inisialisasi Agent:** Sebuah **Pandas DataFrame Agent** dibuat dengan `create_pandas_dataframe_agent`. Proses ini mengikat Large Language Model (IBM Granite) sebagai "otak" dengan DataFrame `df` sebagai konteksnya.
4.  **Interaksi & Analisis:** Setelah berhasil dibuat, agent siap menerima perintah dalam bahasa natural untuk melakukan tugas-tugas seperti eksplorasi data, visualisasi, dan klasifikasi teks.

---

## Penjelasan Dukungan AI (AI Support Explanation)

Peran AI dalam proyek ini adalah sebagai **analis data otonom** yang menjalankan seluruh alur kerja.
* **Model:** `ibm-granite/granite-3.3-8b-instruct`
* **Platform:** Replicate
* **Framework:** LangChain

Agent AI bertanggung jawab penuh untuk:
* **Memahami Perintah:** Menerjemahkan instruksi bahasa natural (misalnya, "buatkan grafik distribusi") menjadi langkah-langkah logis.
* **Menulis Kode:** Secara dinamis menghasilkan kode Python yang diperlukan untuk melakukan analisis pada DataFrame.
* **Mengeksekusi Kode:** Menjalankan kode yang telah ditulisnya menggunakan *Python REPL Tool* yang terintegrasi.
* **Menyajikan Hasil:** Merangkum output dari eksekusi kode menjadi jawaban yang mudah dipahami.

---

## Temuan & Wawasan (Insight & Findings)

Melalui interaksi dengan agent, beberapa wawasan kunci dapat diperoleh:
* **Insight 1: Dataset Cukup Seimbang untuk Klasifikasi:** Agent dapat diperintahkan untuk membuat visualisasi yang menunjukkan bahwa dataset memiliki distribusi kelas yang cukup seimbang antara cuitan 'Bencana' (3,271) dan 'Bukan Bencana' (4,342), kondisi yang ideal untuk tugas klasifikasi.

* **Insight 2: Kemampuan Penalaran dan Klasifikasi Zero-Shot yang Mendalam:** Tanpa perlu *fine-tuning*, agent tidak hanya berhasil mengklasifikasikan cuitan yang diberikan, tetapi juga mampu **menghasilkan dan mengklasifikasikan contoh-contoh baru secara mandiri** dalam proses berpikirnya. Hal ini menunjukkan kemampuan penalaran dan pemahaman konteks yang sangat kuat dari model IBM Granite.

* **Insight 3: Efisiensi Alur Kerja Analis:** Metodologi agent secara drastis mengurangi waktu yang dihabiskan untuk menulis kode repetitif untuk analisis dan visualisasi. Analis dapat fokus pada perumusan pertanyaan yang tepat untuk mendapatkan wawasan.

---

## Kesimpulan & Rekomendasi

### Kesimpulan
Proyek ini berhasil mengimplementasikan AI Agent untuk analisis data secara end-to-end. Pendekatan ini terbukti valid dan efisien, mengubah paradigma interaksi dengan data dari *coding* (menulis kode) menjadi *commanding* (memberi perintah).

### Rekomendasi
Sistem ini direkomendasikan untuk dikembangkan lebih lanjut menjadi sebuah **dashboard monitoring media sosial** bagi tim tanggap darurat. Agent dapat diintegrasikan untuk memproses data secara *real-time*, memberikan peringatan dini, dan membantu alokasi sumber daya saat terjadi bencana.
