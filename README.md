# 📊 Data Visualization — Analisis Data Gempa di Indonesia

## 📌 Project Overview

Project ini merupakan implementasi **pengolahan dan visualisasi data gempa di Indonesia** menggunakan **Apache Spark (PySpark)** dan **Python**.

Project dibuat untuk mengolah dataset gempa dalam jumlah besar, melakukan analisis menggunakan **Spark SQL**, kemudian menyajikan hasil analisis dalam bentuk visualisasi yang lebih mudah dipahami.

Fokus analisis diarahkan pada data gempa di **wilayah Sumbawa**, dengan melihat distribusi magnitudo, tren kejadian gempa berdasarkan waktu, serta hubungan antara magnitudo dan kedalaman gempa.

---

## 🎯 Objectives

Project ini bertujuan untuk:

* Mengolah dataset gempa menggunakan PySpark.
* Melakukan query dan agregasi data menggunakan Spark SQL.
* Menganalisis distribusi magnitudo gempa.
* Mengidentifikasi tren jumlah gempa berdasarkan waktu.
* Menganalisis hubungan antara magnitudo dan kedalaman gempa.
* Menyajikan hasil analisis dalam bentuk visualisasi yang informatif.

---

## 🗂️ Dataset

Dataset yang digunakan berisi informasi mengenai kejadian gempa, antara lain:

| Kolom    | Deskripsi                       |
| -------- | ------------------------------- |
| `tgl`    | Tanggal kejadian gempa          |
| `ot`     | Waktu kejadian                  |
| `lat`    | Latitude/lintang                |
| `lon`    | Longitude/bujur                 |
| `depth`  | Kedalaman gempa                 |
| `mag`    | Magnitudo gempa                 |
| `remark` | Keterangan/lokasi wilayah gempa |

Data kemudian difilter untuk melakukan analisis khusus pada **Sumbawa Region**.

---

## ⚙️ Data Processing Workflow

Proses pengolahan data dilakukan melalui beberapa tahapan:

```text
Raw Dataset
     ↓
Load Data with PySpark
     ↓
Data Selection & Filtering
     ↓
Spark SQL Query
     ↓
Aggregation & Analysis
     ↓
Convert Result to Pandas
     ↓
Data Visualization
     ↓
Insights
```

### 1. Data Loading

Dataset dibaca menggunakan **PySpark DataFrame** dengan struktur kolom dan tipe data yang sesuai.

### 2. Data Selection

Kolom yang relevan dipilih untuk mengurangi data yang tidak diperlukan dalam proses analisis.

### 3. Data Filtering

Data difilter berdasarkan wilayah dan karakteristik gempa yang ingin dianalisis, salah satunya adalah:

* Sumbawa Region
* Rentang magnitudo tertentu
* Rentang tahun tertentu

### 4. Data Aggregation

Agregasi dilakukan menggunakan **Spark SQL**, seperti:

* Menghitung jumlah kejadian gempa.
* Mengelompokkan gempa berdasarkan magnitudo.
* Mengelompokkan kejadian berdasarkan bulan/tahun.
* Membandingkan distribusi kejadian gempa.

### 5. Visualization

Hasil query kemudian dikonversi ke Pandas DataFrame untuk divisualisasikan menggunakan **Matplotlib**.

---

# 📈 Visualizations

## 1. Distribusi Magnitudo Gempa

Visualisasi pertama menunjukkan distribusi jumlah kejadian gempa berdasarkan magnitudo di wilayah Sumbawa.

**Tujuan:**

* Mengetahui magnitudo yang paling sering muncul.
* Membandingkan frekuensi kejadian berdasarkan magnitudo.
* Melihat karakteristik distribusi gempa di wilayah yang dianalisis.

**Metode:**

* `GROUP BY mag`
* `COUNT(*)`
* Sorting berdasarkan jumlah kejadian
* Visualisasi menggunakan bar chart

> **Insight:** Visualisasi membantu mengidentifikasi magnitudo yang paling sering terjadi sehingga distribusi kejadian gempa dapat dibandingkan dengan lebih mudah.

---

## 2. Tren Jumlah Gempa Berdasarkan Waktu

Visualisasi kedua menunjukkan perubahan jumlah kejadian gempa berdasarkan bulan dalam periode pengamatan.

**Tujuan:**

* Melihat pola atau perubahan jumlah kejadian gempa dari waktu ke waktu.
* Mengidentifikasi periode dengan jumlah kejadian yang relatif tinggi atau rendah.

Data tanggal diolah menjadi format **tahun-bulan (`YYYY-MM`)** sebelum dilakukan agregasi.

**Metode:**

* Konversi tanggal
* Grouping berdasarkan bulan
* `COUNT(*)`
* Visualisasi menggunakan line chart

Contoh periode analisis:

```text
2020 — 2024
```

> **Insight:** Line chart memberikan gambaran temporal sehingga perubahan jumlah kejadian gempa dapat diamati dari waktu ke waktu.

---

## 3. Hubungan Magnitudo dan Kedalaman Gempa

Visualisasi ketiga menggunakan **scatter plot** untuk melihat hubungan antara magnitudo dan kedalaman gempa.

**Sumbu X:** Magnitudo (`mag`)
**Sumbu Y:** Kedalaman (`depth`)

**Tujuan:**

* Melihat persebaran magnitudo berdasarkan kedalaman.
* Mengidentifikasi pola atau kecenderungan tertentu.
* Menemukan kemungkinan outlier pada data.

> **Insight:** Scatter plot membantu memberikan gambaran apakah terdapat pola tertentu antara besarnya magnitudo dan kedalaman kejadian gempa.

---

# 🛠️ Technologies & Tools

* **Python**
* **PySpark**
* **Apache Spark**
* **Spark SQL**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Jupyter Notebook**
* **CSV**

---

# 💡 Key Skills Demonstrated

Project ini menunjukkan kemampuan dalam:

### Data Processing

* Loading dataset
* Data filtering
* Data transformation
* Data aggregation
* Data cleaning dasar

### SQL & Big Data

* Spark SQL
* `GROUP BY`
* `COUNT`
* Filtering menggunakan `WHERE`
* Sorting dan aggregation

### Data Visualization

* Bar chart
* Line chart
* Scatter plot
* Pemilihan visualisasi berdasarkan jenis informasi yang ingin ditampilkan

### Data Analysis

* Analisis distribusi data
* Analisis tren waktu
* Analisis hubungan antarvariabel
* Interpretasi hasil visualisasi

---

# 📊 Project Highlights

| Analysis               | Visualization | Purpose                                      |
| ---------------------- | ------------- | -------------------------------------------- |
| Distribusi Magnitudo   | Bar Chart     | Membandingkan frekuensi magnitudo            |
| Tren Gempa             | Line Chart    | Melihat perubahan kejadian berdasarkan waktu |
| Magnitudo vs Kedalaman | Scatter Plot  | Melihat hubungan antarvariabel               |

---

# 🔎 Analysis Approach

Project ini menerapkan pendekatan:

**Data → Processing → Query → Analysis → Visualization → Insight**

Penggunaan **PySpark dan Spark SQL** memungkinkan proses pengolahan data dilakukan menggunakan framework yang dirancang untuk pemrosesan data skala besar, sementara **Matplotlib dan Pandas** digunakan untuk membantu menyajikan hasil analisis secara visual.

---

# 🚀 Future Improvements

Beberapa pengembangan yang dapat dilakukan:

* Membuat dashboard interaktif menggunakan **Power BI** atau **Tableau**.
* Menambahkan visualisasi berdasarkan lokasi geografis menggunakan peta.
* Menambahkan analisis berdasarkan wilayah di Indonesia.
* Membuat analisis tren tahunan dan bulanan yang lebih detail.
* Menambahkan analisis korelasi antarvariabel.
* Mengembangkan pipeline data processing yang lebih otomatis.

---

# 👨‍💻 Author

**Hendra Ahmad Yani**

S1 Teknik Informatika — Universitas Mataram

**Interests:**
Data Analytics · Data Science · Machine Learning · Software Development

---

## 📌 Project Summary

> **Analyzed Indonesian earthquake data using PySpark and Spark SQL, then transformed the analysis results into visualizations to identify magnitude distribution, temporal trends, and the relationship between earthquake magnitude and depth.**
