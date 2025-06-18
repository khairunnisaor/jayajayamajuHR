# Proyek Pertama: Menyelesaikan Permasalahan Perusahaan Human Resource

## Business Understanding
Jaya Jaya Maju adalah perusahaan multinasional yang telah beroperasi sejak tahun 2000, dengan jumlah karyawan lebih dari 1000 orang yang tersebar di seluruh Indonesia. Meskipun telah mencapai skala yang signifikan, perusahaan menghadapi tantangan besar dalam pengelolaan sumber daya manusia, khususnya terkait dengan tingginya tingkat attrition rate. Saat ini, rasio karyawan yang keluar dibandingkan dengan total karyawan keseluruhan telah melampaui 10%, sebuah angka yang mengkhawatirkan dan dapat berdampak negatif pada operasional, produktivitas, serta stabilitas organisasi secara keseluruhan.

Tingginya attrition rate ini menunjukkan adanya isu fundamental dalam kepuasan, keterlibatan, atau retensi karyawan yang belum teridentifikasi dan tertangani secara efektif. Jika dibiarkan berlanjut, kondisi ini berpotensi menyebabkan kerugian finansial akibat biaya rekrutmen dan pelatihan karyawan baru yang tinggi, penurunan moral karyawan yang tersisa, serta hilangnya keahlian dan pengetahuan institusional.

Menyadari urgensi masalah ini, manajer Departemen Sumber Daya Manusia (HR) Jaya Jaya Maju memandang perlu adanya intervensi segera. Oleh karena itu, proyek ini diinisiasi dengan dua tujuan utama: pertama, untuk mengidentifikasi secara komprehensif berbagai faktor yang berkontribusi terhadap tingginya attrition rate; dan kedua, untuk mengembangkan business dashboard yang intuitif dan informatif. Dashboard ini akan berfungsi sebagai alat pemantauan berkelanjutan bagi Departemen HR, memungkinkan mereka untuk melacak faktor-faktor kunci yang memengaruhi retensi karyawan dan mengambil keputusan strategis yang lebih tepat waktu untuk menekan angka attrition. Dengan demikian, proyek ini diharapkan dapat membantu Jaya Jaya Maju menciptakan lingkungan kerja yang lebih stabil dan kondusif bagi seluruh karyawannya.

### Permasalahan Bisnis

Berdasarkan latar belakang, masalah utama yang dihadapi Jaya Jaya Maju adalah tingginya attrition rate karyawan yang mencapai lebih dari 10%. Ini mengindikasikan adanya isu mendalam pada kondisi perusahaan yang mendorong turunnya retensi karyawan dan berpotensi menimbulkan dampak negatif signifikan, antara lain:
* Tingginya turnover-rate karyawan berdampak pada peningkatan biaya operasional HR seperti biaya rekrutmen, orientasi, dan pelatihan karyawan baru.
* Turunnya produktivitas karena perusahaan kehilangan karyawan berpengalaman. Hal ini berarti hilangnya pengetahuan mendalam tentang perusahaan dan karyawan baru pun akan membutuhkan waktu yang tidak sebentar untuk dapat memiliki performa yang sama seperti karyawan senior.
* Turunnya produktivitas karyawan yang tersisa, karena beban kerja yang bertambah sehingga dapat menyebabkan meningkatnya burnout rate.

Berdasarkan hal ini, HR team membutuhkan pemahaman yang lebih dalam terkait faktor-faktor yang mendorong terjadinya attrition agar dapat mengembangkan strategi terbaik untuk menyelesaikan permasalahan ini. Dengan dibuatnya Business Dashboard sebagai alat monitoring karyawan berdasarkan indikator krusial yang menyebabkan attrition, diharapkan perusahaan dapat lebih mudah melalukan data-driven policy making untuk menekan angka attrition.

### Cakupan Proyek
1. Analisis Faktor Pendorong Attrition
* Mengidentifikasi key variables yang secara signifikan mempengaruhi terjadinya attrition dengan menganalisis dataset yang tersedia untuk menemukan pola dan korelasi antara berbagai faktor karyawan dengan status attrition.
* Melakukan segmentasi karyawan yang berisiko tinggi berdasarkan karakteristik karyawan, seperti departemen, jabatan, usia, tingkat kepuasan, atau pendapatan.
* Menentukan faktor eksternal karyawan yang menyebabkan mereka meninggalkan perusahaan, seperti rendahnya kepuasan kerja, beban kerja berlebih, gaji, atau kurangnya kesempatan promosi.

2. Pengembangan Business Dashboard Interaktif
* Membuat visualisasi yang jelas dan mudah dipahami mengenai tren attrition rate secara keseluruhan, berdasarkan key dimensions (misalnya, attrition rate per jabatan atau per rentang usia).
* Mengeksplorasi Faktor Pendorong dengan menyajikan insight dalam bentuk grafik atau widget yang memungkinkan tim HR menelusuri data dan memahami dampak dari masing-masing faktor terhadap attrition.
* Menentukan Key Performance Indicator (KPI) untuk mempertahankan karyawan, seperti
  * Tingkat attrition kumulatif
  * Tingkat lembur kumulatif
  * Rata-rata gaji bulanan berdasarkan tahun kerja di perusahaan
  * Distribusi karyawan dalam kepuasan faktor eksternal dan OverTime untuk mengidentifikasi potensi risiko
* Memastikan dashboard dirancang secara intuitif agar mudah digunakan oleh tim HR tanpa memerlukan keahlian teknis yang mendalam.

3. Rekomendasi untuk Action Items
<br>Memberikan insight terkait action items yang dapat dilakukan berdasarkan analisis, seperti: 
* Mengurangi Over Time Rate di posisi (job role) yang memiliki over time rate dan attrition rate tinggi
* Mengevaluasi ulang seluruh sistem gaji dan fasilitas karyawan
* Memperhatikan kepuasan lingkungan kerja karyawan

Proyek ini akan menghasilkan dashboard yang bermanfaat sebagai alat bantu strategis bagi Departemen HR Jaya Jaya Maju untuk memonitor, menganalisis, dan pada akhirnya, merumuskan intervensi yang tepat guna mengurangi attrition rate dan meningkatkan retensi karyawan.

### Persiapan

Sumber data: [Attrition Karyawan Jaya Jaya Maju](https://github.com/dicodingacademy/dicoding_dataset/blob/main/employee/employee_data.csv)

Pada proyek ini, pembuatan dashboard dilakukan dengan menggunakan Tableau, sehingga persiapan yang dibutuhkan adalah membersihkan dan merapikan dataset untuk siap divisualisasikan.
Proses persiapan dataset yang dilakukan adalah:

1. Pengecekan dan Penanganan Nilai Hilang (Missing Values)
<br>Untuk dapat menangani missing values, dilakukan pengecekan pada setiap kolom terlebih dahulu.
```python
missing_values = df_employee.isnull().sum()
missing_values[missing_values > 0]
```
Output:
```
Attrition:	412
```
Didapatkan bahwa missing values hanya terjadi pada kolom `Attrition`, oleh karena itu diputuskan untuk menghapus baris yang memiliki missing values. Hal ini dipilih karena `Attrition` adalah variabel dependen dalam studi kasus ini, sehingga tidak ada acuan yang dapat digunakan untuk melakukan imputasi data missing values tersebut.
```python
df_employee = df_employee.dropna()
```


2. Memeriksa Data Duplikat
<br>Penting untuk memastikan tidak ada data yang redundan dalam dataset. Maka, dilakukan pengecekan data yang terduplikat dengan cara:
```python
duplicates = df_employee.duplicated()

print("Baris duplikat:")
print(df_employee[duplicates])
```
Output:
```
Baris duplikat:
[0 rows x 35 columns]
```
Didapatkan bahwa tidak ada baris yang terduplikasi.


3. Konversi Nilai Ordinal Kembali Menjadi Data Kategorikal
```python
# Membuat fungsi konversi data ordinal ke kategorikal
def ord_to_cat(df, col, cat_mapping):
    df[col] = df[col].astype(int)
    df[col] = df[col].map(cat_mapping)
    
    return df[col]

# Contoh konversi pada variabel Education (hal ini juga dilakukan pada variabel ordinal lainnya)
education_map = {1: 'Below College', 2: 'College', 3: 'Bachelor', 4: 'Master', 5: 'Doctor'}
df_data['Education'] = ord_to_cat(df_data, 'Education', education_map)
```

4. Export dataset yang sudah rapi dan bersih ke format `CSV` untuk kemudian digunakan pada pembuatan dashboard dengan Tableau.
```python
df_data.to_csv('employee_cleaned.csv', index=False)
```


## Business Dashboard
Hasil analisis disajikan dalam bentuk dashboard interaktif untuk membantu tim HR Jaya Jaya Maju melakukan monitoring dan evaluasi attrition rate. Pada studi kasus ini, key variables terjadinya attrition diidentifikasi dari correlation matrix yang menunjukkan hubungan signifikan antara variabel lain dengan `Attrition`. 
Visualisasi yang disertakan dalam dashboard yaitu:

1. Rangkuman Indikator Attrition
<br>Top bar ini memberikan overview mengenai indikator yang harus ditekan oleh perusahaan, seperti:
* Attrition Rate
* Jumlah Karyawan
* Over Time Rate untuk karyawan yang masih tinggal

2. Faktor Internal Karyawan
<br>Bagian ini menjelaskan faktor internal karyawan yang mempengaruhi terjadinya attrition.
* Jumlah karyawan yang meninggalkan perusahaan berdasarkan umur
* Rata-rata gaji bulanan dibandingkan dengan durasi kerja di perusahaan Jaya Jaya Maju
* Attrition rate berdasarkan job level

3. Faktor Eksternal Karyawan
<br>Bagian ini menjelaskan faktor eksternal karyawan yang mempengaruhi terjadinya attrition.
* Kepuasan karyawan terhadap lingkungan perusahaan
* Kepuasan karyawan terhadap pekerjaannya
* Tingkat keikutsertaan karyawan pada pekerjaannya
* Tingkat work-life balance karyawan

4. Analisis Over Time rate berdasarkan posisi pekerjaan
<br>Lebih dari 50% karyawan yang meminggalkan perusahaan ternyata mengalami Over Time. Berdasarkan hal ini, dilakukan pemantauan khusus untuk kebiasaan kerja lembur di setiap job role sehingga tim HR dapat memberikan perhatian khusus jika job role tertentu memiliki angka overtime yang tinggi.

Link Business Dashboard: [Jaya Jaya Maju HR Attrition Monitoring Dashboard](https://public.tableau.com/app/profile/khairunnisa.oryza/viz/AttritionDashboardforJayaJayaMajuHR/Dashboard1)

## Conclusion

Dari proses analisa, didapatkan bahwa Over Time merupakan satu faktor krusial yang mempengaruhi terjadinya tingkat attrition yang tinggi di perusahaan Jaya Jaya Maju. Dari 17% karyawan yang meninggalkan perusahaan, lebih dari 50% mengalami over time. Hingga saat ini pun, persentase kerja lembur dari karyawan yang masih bekerja di Jaya Jaya Maju adalah 24%.

Analisa faktor internal menunjukkan bahwa kebanyakan dari karyawan yang banyak meninggalakan karyawan berada pada rentang umur produktif (25-37 tahun) dan memiliki gaji bulanan rata-rata yang rendah, terlepas dari lamanya mereka bekerja di perusahaan. Faktor job level pun berpengaruh. 60% dari karyawan yang meninggalkan perusahaan berasal dari job level terbawah. Berdasarkan hal ini, selanjutnya dilakukan analisis berdasarkan faktor eksternal seperti kepuasan lingkungan kerja, kepuasan terhadap pekerjaan, tingkat keikutsertaan pada pekerjaan, dan work-life balance. Faktanya, 32% dari karyawan yang meninggalkan perusahaan memang miliki kepuasan lingkungan kerja yang rendah, walaupun mereka memiliki kepuasan kerja dan keikutsertaan dalam pekerjaan yang tinggi. Dari 17% karyawan yang keluar, 35% dan 51% dari mereka memiliki Job Satisfaction dan Involvement yang tinggi, dimana hal ini menunjukkan mereka memiliki passion dan semangat yang baik dalam melakukan pekerjaannya. Dari sisi work-life balance pun, lebih dari 50% memiliki work-life balance yang sangat baik, yang mengindikasikan mereka adalah karyawan-karyawan yang high performing namun tidak merasa diapresiasi dengan cukup, tidak hanya dari sisi benefit, namun juga dari kesehatan lingkungan kerja.

### Rekomendasi Action Items
Beberapa rekomendasi action items yang harus dilakukan adalah:
1. Menurunkan tingkat over time, terutama pada job role yang memiliki tingkat over time tinggi
2. Melakukan survey kepuasan lingkungan kerja, untuk mengidentifikasi faktor-faktor lain yang menyebabkan high-valued employee meninggalkan perusahaan.
3. Tambahkan program-program yang dapat mendukung kepuasan kerja, seperti skill mentoring, sertifikasi, dan grup hobi agar karyawan tetap berkembang walaupun pemberian kompensasi dan tunjangan masih belum bisa maksimal.
