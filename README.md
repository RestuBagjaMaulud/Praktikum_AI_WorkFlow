Deskripsi Singkat tentang Proyek
Proyek ini bertujuan untuk mengembangkan model AI yang dapat membantu mengotomatisasi pekerjaan di toko kelontong, seperti mengecek penjualan dan menentukan produk yang perlu di-restock. Proyek ini mengikuti tahapan pengembangan AI, yaitu:
1. Digitalise & Collect – Mengumpulkan dan mendigitalisasi data penjualan.
2. Transform – Membersihkan dan mempersiapkan data.
3. Train – Melatih model AI menggunakan algoritma Machine Learning.
4. Execute – Menggunakan model untuk melakukan prediksi restock.
5. Provide Insights – Menganalisis hasil menggunakan visualisasi data.

Instruksi Cara Menjalankan Kode
Persiapan
1. Buka Google Colab – Pergi ke Google Colab dan buat notebook baru.
2. Upload Dataset – Jika belum ada dataset, buat file CSV bernama data_penjualan.csv dengan format:
    - Kolom: Tanggal, Produk, Jumlah Terjual, Stok, Harga Satuan
    - Minimal 10 baris data

Langkah-langkah
1. Baca Data di Google Colab
import pandas as pd

df = pd.read_csv("data_penjualan.csv")
print(df.head())

2. Membersihkan dan Mengolah Data
df['Tanggal'] = pd.to_datetime(df['Tanggal'])
df['Total Penjualan'] = df['Jumlah Terjual'] * df['Harga Satuan']
df['Keuntungan'] = (df['Jumlah Terjual'] * df['Harga Satuan']) - (df['Jumlah Terjual'] * 10000)
print(df.head())

3. Melatih Model AI (Decision Tree)
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score

# Menentukan fitur dan target
X = df[['Jumlah Terjual', 'Stok']]
y = (df['Stok'] < 5).astype(int)  # 1 jika perlu restock, 0 jika tidak

# Membagi data untuk training dan testing
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Melatih model
model = DecisionTreeClassifier()
model.fit(X_train, y_train)

# Evaluasi model
y_pred = model.predict(X_test)
print("Akurasi:", accuracy_score(y_test, y_pred))

4. Memprediksi Restock Produk
new_data = [[8, 3]]  # Jumlah Terjual = 8, Stok = 3
prediction = model.predict(new_data)
print("Perlu Restock" if prediction[0] == 1 else "Tidak Perlu Restock")

5. Visualisasi Data
import matplotlib.pyplot as plt

plt.scatter(df['Jumlah Terjual'], df['Stok'], c=df['Keuntungan'], cmap='coolwarm')
plt.xlabel("Jumlah Terjual")
plt.ylabel("Stok")
plt.colorbar(label="Keuntungan")
plt.show()
