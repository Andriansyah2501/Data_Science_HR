# Proyek Akhir: Menyelesaikan Permasalahan Human Resources

## Business Understanding
Jaya Jaya Maju adalah perusahaan multinasional yang telah berdiri sejak tahun 2000 dan kini memiliki lebih dari 1000 karyawan yang tersebar di seluruh penjuru negeri. Sebagai perusahaan yang sudah cukup besar, Jaya Jaya Maju menghadapi tantangan dalam mengelola sumber daya manusia (SDM) yang berdampak pada tingkat pergantian karyawan yang cukup tinggi.

### Permasalahan Bisnis
Walaupun perusahaan sudah berkembang pesat, Jaya Jaya Maju masih menghadapi masalah serius terkait attrition rate (rasio karyawan yang keluar). Tingkat pergantian karyawan ini telah melebihi 10%, yang dapat memengaruhi stabilitas operasional perusahaan.

Beberapa permasalahan yang perlu diidentifikasi dan diselesaikan adalah:

1. Tingginya Attrition Rate: Prosentase karyawan yang keluar terlalu tinggi, yang mengganggu kelangsungan operasional dan meningkatkan biaya rekrutmen serta pelatihan.

2. Faktor Penyebab Pergantian Karyawan: Perusahaan perlu mengetahui faktor-faktor spesifik yang mempengaruhi keputusan karyawan untuk meninggalkan perusahaan, seperti usia, jenis kelamin, departemen, peran pekerjaan, status pernikahan, dan lainnya.

3. Keterlibatan Karyawan: Perusahaan belum sepenuhnya memahami hubungan antara tingkat keterlibatan karyawan dengan pergantian karyawan.

4. Program Retensi yang Kurang Efektif: Strategi untuk mempertahankan karyawan mungkin belum optimal, dan perlu adanya evaluasi terhadap program retensi yang ada.

### Cakupan Proyek
Proyek ini bertujuan untuk membantu manajer HR Jaya Jaya Maju dalam mengidentifikasi faktor-faktor yang mempengaruhi tingginya attrition rate dan memberikan wawasan yang bisa digunakan untuk memperbaiki program retensi karyawan. Berikut adalah cakupan proyeknya:

1. Pengumpulan dan Persiapan Data: Mengumpulkan data karyawan yang relevan, seperti usia, jenis kelamin, departemen, jabatan, status pernikahan, dan status pergantian (attrition).
2. Analisis Faktor-faktor yang Mempengaruhi Attrition: Menggunakan analisis data untuk mengidentifikasi faktor-faktor yang paling berpengaruh terhadap tingkat pergantian karyawan.
3. Pembuatan Business Dashboard: Membuat dashboard interaktif di Metabase untuk memvisualisasikan data karyawan, seperti attrition rate berdasarkan usia, jenis kelamin, jabatan, departemen, dan faktor-faktor lainnya.
4. Rekomendasi Program Retensi: Berdasarkan hasil analisis, memberikan rekomendasi yang dapat membantu perusahaan mengurangi tingkat pergantian karyawan, seperti peningkatan program kesejahteraan, pengembangan karir, dan kebijakan kerja fleksibel.

### Persiapan
Sumber Data: [Link Sumber Data](https://github.com/dicodingacademy/dicoding_dataset/tree/main/employee)

Setup Lingkungan:
a. Menyiapkan Environment Conda:
Buat Environment Conda Baru:
1. Jalankan perintah untuk membuat environment baru dengan Python versi 3.12:
```
conda create --name myenv python=3.12
```

2. Aktifkan Environment Conda:

Untuk pengguna MacOS:
```
conda activate myenv
```
Untuk pengguna Windows:
```
conda activate myenv
```

3. Install Requirements:
Install semua dependensi yang terdaftar dalam file requirements.txt:
```
pip install -r requirements.txt
```

b. Menyiapkan Metabase:
1. Pull Image Docker Metabase:
Untuk mengunduh versi terbaru dari Metabase menggunakan Docker, jalankan perintah:
```
docker pull metabase/metabase:v0.46.4
```

2. Jalankan Metabase dengan Docker:
Untuk menjalankan Metabase di port 3000, gunakan perintah:
```
docker run -p 3000:3000 --name metabase metabase/metabase
```

3. Akses Metabase:
Buka browser dan akses Metabase pada alamat berikut:
```
http://localhost:3000/setup
```

4. Ikuti petunjuk untuk menyelesaikan proses setup Metabase.


c. Menyiapkan Database (Supabase):
1. Buat Akun dan Login ke Supabase:
- Daftarkan akun dan masuk ke dasbor Supabase melalui [tautan ini](https://supabase.com/dashboard/sign-in).
3. Buat Proyek Baru:
- Klik New Project untuk memulai proyek baru di Supabase.
5. Salin URI Database:
- Salin URI yang tersedia di pengaturan database Supabase Anda.
6. Kirim Dataset menggunakan SQLAlchemy:
Gunakan SQLAlchemy untuk mengirim dataset ke database dengan kode berikut:
```
from sqlalchemy import create_engine
URL = "postgresql://postgres.tadpufxfzfadhfpjacyh:qTGcarmeDOpns2h4@aws-0-ap-southeast-1.pooler.supabase.com:6543/postgres"
engine = create_engine(URL)
df.to_sql('employee', engine)
```

Dengan langkah-langkah ini, Anda dapat menyiapkan environment, Metabase, dan Supabase untuk mulai bekerja dengan data dan membuat dashboard interaktif.

## Business Dashboard
Dashboard ini dirancang untuk memberikan wawasan kepada tim HR mengenai faktor-faktor yang mempengaruhi keputusan karyawan untuk mengundurkan diri. Dengan visualisasi interaktif, dashboard ini memungkinkan tim HR untuk:
1. Melihat jumlah total karyawan dan karyawan aktif.
2. Menganalisis rata-rata usia karyawan yang keluar dan mengidentifikasi kelompok usia yang lebih rentan terhadap pergantian.
3. Menghitung attrition rate dan menganalisis distribusi pergantian berdasarkan usia, jenis kelamin, departemen, status pernikahan, dan peran pekerjaan.
4. Membantu tim HR untuk mengidentifikasi area dengan tingkat pergantian tinggi dan fokus pada strategi retensi yang lebih efektif.



![Dashboard Preview](./Dashboard%201.jpg)

Dashboard ini menyajikan visualisasi data karyawan untuk membantu pengambilan keputusan strategis dalam manajemen SDM. Fokus utama analisis adalah distribusi karyawan berdasarkan usia, gender, dan departemen, serta metrik attrition (pengunduran diri).

---

## ✅ Ringkasan Metrik

| Metrik                 | Nilai         |
|------------------------|---------------|
| Total Karyawan         | 1.058 orang   |
| Rata-rata Usia Keluar  | 37.06 tahun   |
| Komposisi Gender       | Male: 58.6% / Female: 41.4% |

---

## 🧠 Analisis dan Insight

### 1. **Total Karyawan**
Organisasi memiliki total **1.058** karyawan aktif. Ini mencerminkan organisasi dengan skala operasional menengah hingga besar, yang perlu strategi manajemen SDM terstruktur.

### 2. **Attrition by Age**
- Rata-rata usia karyawan yang mengundurkan diri adalah **37.06 tahun**.
- Ini menunjukkan attrition terjadi pada usia produktif, kemungkinan karena stagnasi karier atau daya tarik dari perusahaan lain.

### 3. **Distribusi Gender**
- **Male:** 58.6%
- **Female:** 41.4%
- Proporsi gender cukup seimbang namun menunjukkan sedikit dominasi laki-laki.
- Ini bisa menjadi referensi untuk memperkuat program kesetaraan dan keberagaman (diversity & inclusion).

### 4. **Distribusi Karyawan per Departemen**
- **Research & Development (R&D):** Departemen terbesar (sekitar 700 karyawan), menunjukkan fokus utama organisasi adalah inovasi.
- **Sales:** Departemen kedua terbesar, penting dalam mendukung pertumbuhan pasar.
- **Human Resources:** Ukuran kecil namun strategis, mungkin membutuhkan penguatan SDM untuk mendukung pertumbuhan internal.

---

## 📌 Kesimpulan

Dashboard ini menunjukkan:
- Area yang perlu diperhatikan dalam retensi karyawan.
- Komposisi SDM yang bisa digunakan untuk evaluasi keberagaman.
- Alokasi tenaga kerja per departemen yang bisa menjadi dasar pengembangan dan pelatihan internal.

---

## 📂 Dataset & Tools

- **Data Source:** `employee_data.csv` → dimigrasikan ke PostgreSQL
- **Tools:**
  - [Metabase](https://www.metabase.com/)
  - PostgreSQL
  - SQL Native Query
- **Visualisasi:** Metabase Dashboard Builder

---

## 💡 Rekomendasi Selanjutnya

- Tambahkan analisis berdasarkan **masa kerja** dan **lembur (OverTime)**
- Integrasi dengan data performa dan kepuasan kerja
- Bangun sistem peringatan dini untuk potensi attrition

---

## 👤 Author

**Andrian Syah**  



