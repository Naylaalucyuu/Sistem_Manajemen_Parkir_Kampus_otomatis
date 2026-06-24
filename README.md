# Sistem Manajemen Parkir Kampus Otomatis
Proyek implementasi Basis Data relasional untuk Sistem Manajemen Parkir Kampus Otomatis

## NAMA ANGGOTA (Kelompok 6)
### Nayla Putri Zelfia (2501020091)
### Zahra Dea Amanda (2501020118)
### Muhammad Faisyar Rizqi (2501020119)
### Dara Puspitasari (2501020120)
---  
# PROGRESS 1
## STUDI KASUS
Sistem Manajemen Parkir Kampus Otomatis merupakan sistem berbasis basis data yang dirancang untuk membantu pengelolaan parkir kendaraan di lingkungan kampus secara digital dan otomatis. Sistem ini digunakan untuk mencatat aktivitas kendaraan mulai dari registrasi kendaraan, proses masuk dan keluar area parkir, hingga pemantauan ketersediaan slot parkir secara real-time.
Sistem ini melibatkan beberapa pengguna seperti mahasiswa, dosen, staf kampus, petugas parkir, admin, dan pengunjung. Setiap kendaraan yang menggunakan fasilitas parkir akan dicatat ke dalam basis data sehingga informasi kendaraan dapat dikelola dengan lebih teratur dan mudah diakses. Selain itu, sistem juga mampu menyimpan riwayat penggunaan parkir yang dapat digunakan untuk kebutuhan monitoring dan pelaporan.
Dengan adanya Sistem Manajemen Parkir Kampus Otomatis, proses pencatatan parkir menjadi lebih cepat, akurat, aman, dan mengurangi ketergantungan terhadap pencatatan manual.

##
## LATAR BELAKANG DAN TUJUAN SISTEM
### Latar Belakang
Pengelolaan parkir di kampus sering mengalami berbagai kendala seperti keterbatasan lahan parkir, pencatatan kendaraan yang masih dilakukan secara manual, sulit mengetahui jumlah slot yang tersedia, serta proses pengawasan kendaraan yang kurang efektif. Kondisi tersebut dapat menyebabkan antrean kendaraan dan menyulitkan pengguna saat mencari tempat parkir.
Untuk mengatasi permasalahan tersebut, diperlukan sistem berbasis basis data yang mampu mengelola seluruh informasi parkir secara terintegrasi. Dengan memanfaatkan SQL, data kendaraan, data pengguna, dan aktivitas parkir dapat disimpan serta dikelola secara otomatis sehingga proses operasional menjadi lebih efisien.
### Tujuan Sistem
1. Mempermudah pengelolaan data kendaraan masuk dan keluar.
2. Menyediakan informasi ketersediaan tempat parkir secara real-time.
3. Meningkatkan keamanan kendaraan di area kampus.
4. Mempermudah proses pelaporan data parkir.
5. Mengurangi kesalahan pencatatan data parkir.

##
## IDENTIFIKASI AKTOR
1. Admin = Mengelola seluruah data sistem parkir.
2. Mahasiswa = Menggunakan area parkir dan mendaftarkan kendaraan.
3. Dosen = Menggunakan area parkir dan mendaftarkan kendaraan.
4. Staf Kampus = Menggunakan area parkir.
5. Petugas Parkir = Memantau kendaraan masuk dan keluar.
6. Pengunjung = Menggunakan parkir sementara.

##
## KEBUTUHAN FUNGSIONAL
1. Sistem dapat melakukan login admin.
2. Sistem menambahkan data pengguna.
3. Sistem dapat mengubah data pengguna.
4. Sistem dapat menghapus data pengguna.
5. Sistem dapat mencatat data kendaraan.
6. Sistem dapat mencatat kendaraan masuk.
7. Sistem dapat mencatat kendaraan keluar.
8. Sistem dapat menghitung durasi parkir.
9. Sistem dapat menampilkan jumlah slot yang tersedia.
10. Sistem dapat menghasilkan laporan parkir harian.
11. Sistem dapat mencari data kendaraan berdasarkan nomor polisi.
12. sistem dapat menampilkan riwayat parkit kendaraan.

##
## KEBUTUHAN DATA
### Tabel User
1. id_user INT
2. nama VARCHAR (100)
3.	role ENUM 
4.	no_hp VARCHAR (15)


### Tabel Kendaraan 
1. id_kendaraan INT
2. no_polisi VARCHAR (15)
3. jenis_kendaraan VARCHAR (20)
4. id_user INT

### Tabel Area Parkir
1. id_area INT
2. id_kendaraan INT
3.	id_slot INT
4.	waktu_masuk DATETIME
5.	waktu_keluar DATETIME


### Tabel Slot Parkir
1. id_slot INT
2. nomor_slot VARCHAR (20)
3. status_slot ENUM

### Tabel Pembayaran
1.	id_pembayaran INT
2.	id_parkir
3.	durasi_jam INT
4.	biaya DECIMAL
5.	status_bayar ENUM

##
## DIAGRAM PROSES
<img width="485" height="2560" alt="image" src="https://github.com/user-attachments/assets/85e0c4bb-cf16-4aca-8a60-61dfeeb6dfa6" />

##
## PEMBAGIAN TUGAS ANGGOTA
1. Zahra Dea Amanda (2501020118) = Bertugas dalam membuat latar belakang dan tujuan sistem.
2. Nayla Putri Zelfia (2501020091) = Bertugas dalam membuat kebutuhan fungsional dan kebutuhan data.
3. Dara Puspitasari (2501020120) = Bertugas dalam membuat diagram proses atau flowchart.
4. Muhammad Faisyar Rizqi (2501020119) = Bertugas dalam membuat studi kasus dan identifikasi aktor.

##
## LINK RIPOSITORY GITHUB
https://github.com/Naylaalucyuu/Sistem_Manajemen_Parkir_Kampus_otomatis.git

--- 
# PROGRESS 2
## ERD (Entity Relationship Diagram)
### UNF (Unnormalized Form)
<img width="1852" height="929" alt="Untitled Diagram" src="https://github.com/user-attachments/assets/2d1f827b-1e7c-447e-a7cd-76e09318a883" />

##
## Penjelasan Entitas Dan Relasi
### Entitas 
1. User
   Digunakan Digunakan untuk menyimpan data seluruh pengguna sistem seperti admin, mahasiswa, dosen, staf kampus, petugas parkir, dan pengunjung.
2. Kendaraan
   Menyimpan data kendaraan yang terdaftar pada sistem parkir kampus.
3. Parkir
   Mencatat seluruh aktivitas kendaraan saat memasuki dan keluar area parkir termasuk waktu dan durasi parkir.
4. Slot_Parkir
   Digunakan untuk menyimpan informasi slot parkir beserta status ketersediaannya.
### Relasi
1. User → Kendaraan (1:M)
   Satu pengguna dapat mendaftarkan lebih dari satu kendaraan.
2. Kendaraan → Parkir (1:M)
   Satu kendaraan dapat melakukan parkir lebih dari satu kali.
3. Slot_Parkir → Parkir (1:M)
   Satu slot dapat digunakan berkali-kali pada transaksi parkir yang berbeda.

##
## Kamus Data (Data Dictionary)
### Tabel User
|   Field  |  Tipe Data   |     Keterangan    |
| -------- | ------------ | ----------------- |
| id_user  | INT          | Primary Key       |
| nama     | VARCHAR(100) | Nama pengguna     |
| username | VARCHAR(50)  | Username login    |
| password | VARCHAR(255) | Password pengguna |
| role     | VARCHAR(20)  | Jenis pengguna    |

### Tabel Kendaraan
|      Field      |   Tipe Data  |   Keterangan    |
| --------------- | ------------ | --------------- |
| id_kendaraan    | INT          | Primary Key     |
| no_polisi       | VARCHAR(15)  | Nomor polisi    |
| jenis_kendaraan | VARCHAR(20)  | Jenis kendaraan |
| pemilik         | VARCHAR(100) | Nama pemilik    |
| id_user         | INT          | Foreign Key     |

### Tabel Parkir
|     Field    |  Tipe Data  |       Keterangan       |
| ------------ | ----------- | ---------------------- |
| id_parkir    | INT         | Primary Key            |
| id_kendaraan | INT         | Foreign Key            |
| waktu_masuk  | DATETIME    | Waktu kendaraan masuk  |
| waktu_keluar | DATETIME    | Waktu kendaraan keluar |
| durasi       | INT         | Lama parkir            |
| status       | VARCHAR(20) | Status kendaraan       |
| id_slot      | INT         | Foreign Key            |

##
## Normalisasi (UNF → 1NF → 2NF → 3NF)
### UNF (Unnormalized Form)

| id_user | nama  | kendaraan       | parkir      | slot |
| ------- | ----- | --------------- | ----------- | ---- |
| 001     | Dea   | BP1234XX, Motor | Masuk 08.00 | A01  |

Masih terdapat data gabungan dan redundansi.

## 1NF (First Normal Form)
Data dipecah menjadi atribut tunggal.
| id_user | nama | no_polisi | jenis_kendaraan | nomor_slot |
| ------- | ---- | --------- | --------------- | ---------- |

Setiap kolom sudah memiliki satu nilai.

## 2NF (Second Normal Form)
Data dipisahkan berdasarkan ketergantungan terhadap primary key.
Tabel:
* User
* Kendaraan
* Parkir
* Slot_Parkir

Menghilangkan pengulangan data kendaraan dan slot.

## 3NF (Third Normal Form)
Menghilangkan ketergantungan transitif.
Struktur akhir:
1. User
   (id_user, nama, username, password, role)
2. Kendaraan
   (id_kendaraan, no_polisi, jenis_kendaraan, pemilik, id_user)
3. Parkir
   (id_parkir, id_kendaraan, waktu_masuk, waktu_keluar, durasi, status, id_slot)
4. Slot_Parkir
   (id_slot, nomor_slot, status_slot)

Seluruh atribut non-key hanya bergantung pada primary key masing-masing.

## Relevasi Analisis Kebutuhan
Berdasarkan hasil perancangan basis data dan normalisasi, terdapat beberapa revisi:
1. Menambahkan relasi antara tabel Parkir dan Slot_Parkir agar sistem dapat menampilkan ketersediaan slot secara real-time.
2. Menambahkan foreign key pada tabel Parkir untuk menghubungkan aktivitas parkir dengan slot yang digunakan.
3. Data kendaraan dipisahkan dari tabel User agar mendukung satu pengguna memiliki lebih dari satu kendaraan.
4. Struktur database disusun hingga bentuk 3NF untuk mengurangi redundansi data.
5. Sistem tetap mendukung kebutuhan fungsional seperti pencatatan kendaraan masuk, keluar, pencarian kendaraan, serta laporan parkir.

--- 
# PROGRESS 3
## 1. Script SQL DDL (CREATE DATABASE, CREATE TABLE)
<img width="1256" height="487" alt="image" src="https://github.com/user-attachments/assets/3cb7060e-0a0e-4a9e-adb6-e934c45e22d5" />
Perintah CREATE DATABASE sistem_manajemen_parkir_kampus_otomatis_klmpk6; digunakan untuk membuat sebuah database baru yang akan menjadi tempat penyimpanan seluruh data pada sistem parkir kampus, seperti data pengguna, kendaraan, slot parkir, aktivitas parkir, dan pembayaran, kemudian perintah USE sistem_manajemen_parkir_kampus_otomatis_klmpk6; digunakan untuk mengaktifkan database tersebut agar bisa digunakan; setelah itu, perintah CREATE TABLE dijalankan untuk membuat struktur tabel di dalam database, seperti tabel user, kendaraan, slot_parkir, parkir, dan pembayaran, di mana setiap tabel memiliki kolom dengan tipe data tertentu, primary key sebagai identitas unik, serta foreign key untuk menghubungkan antar tabel sehingga data menjadi terorganisir dan saling terintegrasi dengan baik dalam mendukung jalannya sistem manajemen parkir otomatis.

## 2. Constraint (PK, FK, UNIQUE, NOT NULL)
<img width="1111" height="835" alt="image" src="https://github.com/user-attachments/assets/55bcffa0-3fe3-4e38-aa5f-835ec6f59f6c" />

### Primary Key (PK)
Primary Key adalah kunci utama yang digunakan untuk mengidentifikasi setiap data agar tidak ada yang sama. Pada database ini, setiap tabel memiliki PK yaitu: id_user pada tabel user, id_kendaraan pada tabel kendaraan, id_slot pada tabel slot_parkir, id_parkir pada tabel parkir, dan id_pembayaran pada tabel pembayaran. Semua PK menggunakan AUTO_INCREMENT sehingga nilainya bertambah otomatis.

### Foreign Key (FK)
Foreign Key digunakan untuk menghubungkan antar tabel. Contohnya, id_user pada tabel kendaraan menjadi FK yang mengacu ke user(id_user), lalu id_kendaraan dan id_slot pada tabel parkir masing-masing mengacu ke tabel kendaraan dan slot_parkir, serta id_parkir pada tabel pembayaran mengacu ke tabel parkir. Dengan adanya FK ini, relasi antar data menjadi terjaga dan konsisten.

### UNIQUE
Constraint UNIQUE memastikan bahwa suatu nilai tidak boleh duplikat. Pada database ini, terdapat pada kolom no_polisi di tabel kendaraan, sehingga setiap kendaraan harus memiliki nomor polisi yang berbeda dan tidak boleh sama.

### NOT NULL
Constraint NOT NULL digunakan agar suatu kolom wajib diisi (tidak boleh kosong). Contohnya terdapat pada kolom nama, role di tabel user, no_polisi dan jenis_kendaraan di tabel kendaraan, lokasi dan status_slot di tabel slot_parkir, serta beberapa kolom lain seperti id_kendaraan, id_slot, dan waktu_masuk di tabel parkir. Ini memastikan data yang disimpan selalu lengkap dan tidak kosong.

## 3. Data uji (INSERT)
<img width="1600" height="787" alt="image" src="https://github.com/user-attachments/assets/559669f7-1624-4dcd-9a8d-fcbb237c1509" /> <img width="1600" height="880" alt="image" src="https://github.com/user-attachments/assets/363058dd-ab4d-4af3-90f9-6a16c5f8b6eb" /> <img width="1600" height="135" alt="image" src="https://github.com/user-attachments/assets/d6b9c7c7-589f-4603-9213-cd5565308e4a" />

### Bagian 1
Pada tahap pengujian sistem, dilakukan proses INSERT data ke tabel user sebanyak 13 record. Data yang dimasukkan terdiri dari beberapa kategori pengguna, yaitu Mahasiswa, Dosen, Staff, dan Pengunjung. Setiap pengguna memiliki atribut nama, role, dan nomor handphone. Untuk mahasiswa, dosen, dan staff, kolom nomor handphone diisi dengan nilai NULL, sedangkan data pengunjung memiliki nomor handphone yang diisi sebagai informasi tambahan. Data ini digunakan untuk mensimulasikan berbagai jenis pengguna yang dapat mengakses area parkir kampus.
### Bagian 2
Setelah data pengguna berhasil ditambahkan, dilakukan pengisian data pada tabel kendaraan sebanyak 13 record. Setiap kendaraan memiliki nomor polisi, jenis kendaraan, dan id pengguna sebagai foreign key yang menghubungkan kendaraan dengan pemiliknya pada tabel user. Jenis kendaraan yang digunakan dalam data uji terdiri dari Motor dan Mobil. Dengan adanya relasi ini, sistem dapat mengetahui kendaraan yang dimiliki oleh setiap pengguna yang terdaftar dalam database.
### Bagian 3
Selanjutnya dilakukan pengisian data pada tabel slot_parkir sebanyak 20 record. Data slot parkir diberi kode lokasi mulai dari A1 hingga D5. Setiap slot memiliki status yang menunjukkan kondisi ketersediaannya, yaitu Terisi atau Kosong. Data ini digunakan untuk mensimulasikan kondisi nyata area parkir kampus, di mana beberapa slot sedang digunakan oleh kendaraan dan sebagian lainnya masih tersedia untuk ditempati.
### Bagian 4
Tahap berikutnya adalah pengisian data pada tabel parkir sebanyak 13 record. Tabel ini menyimpan informasi transaksi parkir yang meliputi id kendaraan, id slot parkir, waktu masuk, dan waktu keluar. Sebagian besar data memiliki waktu masuk dan keluar yang lengkap untuk menggambarkan kendaraan yang telah selesai parkir. Namun, terdapat beberapa record yang memiliki nilai NULL pada kolom waktu keluar, yang menunjukkan bahwa kendaraan tersebut masih berada di area parkir dan belum melakukan proses keluar.

## 4. Minimal 10 Query SQL
<img width="1232" height="913" alt="image" src="https://github.com/user-attachments/assets/62ec7da8-f43b-4edf-ba3f-7598f6359980" />
<img width="1146" height="995" alt="image" src="https://github.com/user-attachments/assets/ceaaabec-9e84-42e2-a63d-001b0779edcc" />
<img width="1146" height="995" alt="image" src="https://github.com/user-attachments/assets/7192ba45-d495-4bfb-808a-61f8463ac4ea" />
<img width="1146" height="995" alt="image" src="https://github.com/user-attachments/assets/0f5528a3-da10-4e7e-b8c3-0726966d9456" />
<img width="1146" height="995" alt="image" src="https://github.com/user-attachments/assets/b9313fb9-cf17-42d5-a8a2-c7e71218ffce" />

## 5. Skenario pengujian
<img width="1135" height="626" alt="Cuplikan layar 2026-06-24 201552" src="https://github.com/user-attachments/assets/fd09cbe7-a584-4939-880c-7f7e2f3ad21c" />
Skenario pengujian pada gambar tersebut dilakukan dengan membuat sebuah VIEW bernama view_parkir yang menggabungkan data dari tiga tabel utama, yaitu user, kendaraan, dan parkir, menggunakan perintah JOIN. Setelah view berhasil dibuat (ditandai dengan “Query OK”), dilakukan pengujian dengan menjalankan perintah SELECT * FROM view_parkir untuk menampilkan seluruh data parkir secara terintegrasi. Hasil yang ditampilkan menunjukkan informasi lengkap berupa nama pengguna, peran (role), nomor polisi, jenis kendaraan, waktu masuk, dan waktu keluar. Dari hasil tersebut terlihat bahwa data berhasil digabungkan dengan benar, termasuk kondisi kendaraan yang sudah keluar (memiliki waktu_keluar) dan yang masih parkir (waktu_keluar bernilai NULL). Hal ini membuktikan bahwa relasi antar tabel berjalan dengan baik serta sistem mampu menampilkan data parkir secara menyeluruh dan akurat.

