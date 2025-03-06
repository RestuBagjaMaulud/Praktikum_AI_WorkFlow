# Deskripsi Singkat tentang Proyek
Proyek ini bertujuan untuk mengembangkan model AI yang dapat membantu mengotomatisasi pekerjaan di toko kelontong, seperti mengecek penjualan dan menentukan produk yang perlu di-restock. Proyek ini mengikuti tahapan pengembangan AI, yaitu:
    ### 1. Digitalise & Collect – Mengumpulkan dan mendigitalisasi data penjualan.
    ### 2. Transform – Membersihkan dan mempersiapkan data.
    ### 3. Train – Melatih model AI menggunakan algoritma Machine Learning.
    ### 4. Execute – Menggunakan model untuk melakukan prediksi restock.
    ### 5. Provide Insights – Menganalisis hasil menggunakan visualisasi data.

Proyek ini berhasil menerapkan AI untuk menganalisis data penjualan dan stok di Google Colab. Data telah dikumpulkan, diproses, dan digunakan untuk melatih model Decision Tree guna memprediksi kebutuhan restock. Evaluasi model memastikan akurasinya, sementara visualisasi scatter plot membantu mengidentifikasi pola penjualan dan keuntungan. Hasilnya, AI terbukti dapat meningkatkan efisiensi manajemen stok dan mendukung pengambilan keputusan bisnis yang lebih akurat.

# Instruksi Cara Menjalankan Kode
Persiapan
    1. Buka Google Colab – Pergi ke Google Colab dan buat notebook baru.
    2. Upload Dataset – Jika belum ada dataset, buat file CSV bernama data_penjualan.csv dengan format:
        - Kolom: Tanggal, Produk, Jumlah Terjual, Stok, Harga Satuan
        - Minimal 10 baris data

Langkah-langkah
    1. Baca Data di Google Colab
        Pada tahap ini, data penjualan yang dikumpulkan dalam format CSV akan dibaca menggunakan library pandas. Data ini akan ditampilkan untuk memastikan bahwa pembacaan berhasil.
    2. Membersihkan dan Mengolah Data
        Langkah ini bertujuan untuk membersihkan data, mengonversi format tanggal, serta menambahkan kolom baru yang diperlukan untuk analisi.
    3. Melatih Model AI (Decision Tree)
        Pada tahap ini, model AI dilatih menggunakan algoritma Decision Tree Classifier untuk memprediksi apakah suatu produk perlu di-restock.
       - Menentukan fitur dan target
       - Membagi data untuk training dan testing
       - Melatih model
       - Evaluasi model
    4. Memprediksi Restock Produk
        Setelah model AI selesai dilatih, model dapat digunakan untuk memprediksi apakah suatu produk perlu di-restock berdasarkan jumlah terjual dan stok saat ini.
    5. Visualisasi Data
        Tahap terakhir adalah menganalisis hasil prediksi menggunakan visualisasi data untuk memahami pola hubungan antara jumlah terjual, stok, dan keuntungan.
