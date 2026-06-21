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
3. username VARCHAR (50)
4. password VARCHAR (255)
5. role VARCHAR (20)

### Tabel Kendaraan 
1. id_kendaraan INT
2. no_polisi VARCHAR (15)
3. jenis_kendaraan VARCHAR (20)
4. pemilik VARCHAR (100)
5. id_user INT

### Tabel Parkir
1. id_parkir INT
2. id_kendaraan INT
3. waktu_masuk DATETIME
4. waktu_keluar DATETIME
5. durasi INT
6. status VARCHAR (20)

### Tabel Slot Parkir
1. id_slot INT
2. nomor_slot VARCHAR (10)
3. status_slot VARCHAR(20)

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
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/a8c48150-1eec-466c-bdae-ef9bc34ba06a" />

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
