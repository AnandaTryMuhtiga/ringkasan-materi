📘 **Rangkuman Lengkap Bab 1 – Bab 2

Modul Praktikum Basis Data (MySQL)**

---------------------------------------------
BAB 1 — Review Konversi ER Diagram ke Skema Relasi

Bab ini menjelaskan proses penting dalam perancangan basis data, yaitu bagaimana mengubah Entity Relationship Diagram (ERD) menjadi skema relasi, lalu meneruskannya menjadi struktur tabel fisik pada basis data.

🎯 Tujuan Pembelajaran

Memahami konsep dasar dalam ERD:

Entitas, atribut, primary key, relasi, kardinalitas.

Mampu melakukan proses transformasi:

ERD → Diagram Relationship → Tabel Relasional.

Mempersiapkan praktikan untuk proses pembuatan database di level fisik.

🔍 Konsep Dasar
1. Entitas

Objek nyata yang menjadi pusat data (misal: Mahasiswa, Pegawai, Buku).
Setiap entitas memiliki atribut, dimana salah satu harus menjadi primary key (PK).

2. Relasi

Hubungan antar entitas, memiliki kardinalitas seperti:

1 : 1 (One to One)

1 : N (One to Many)

N : M (Many to Many)

3. Atribut

Jenis atribut dalam ERD:

Simple atribut

Composite atribut

Multivalue atribut

Derived atribut

🧭 Aturan Konversi ERD ke Skema Relasi

Konversi dilakukan menggunakan aturan berikut:

1. Entitas Kuat → 1 Tabel

Atribut menjadi kolom.

PK menjadi primary key tabel.

2. Composite Atribut

Dipecah menjadi kolom-kolom individual.
Contoh: alamat {jalan, kota, kode_pos}.

3. Multivalue Atribut → Tabel Baru

Contoh: Atribut hobby pada entitas Karyawan → tabel baru Hobby_Karyawan.

4. Derived Atribut

Tetap disimpan sebagai kolom jika diperlukan oleh aplikasi.

5. Entitas Lemah

Menjadi tabel baru dan memperoleh foreign key dari entitas kuat.

6. Relasi 1–1

Foreign key diletakkan pada salah satu entitas berdasarkan kebutuhan.

7. Relasi 1–N

Foreign key disimpan pada entitas N (many).

8. Relasi N–N

Harus dibuatkan tabel baru yang menyimpan minimal dua FK dan atribut relasi.

9. Relasi dengan atribut

Jika relasi memiliki atribut, maka relasi menjadi tabel baru.

10. Unary Relationship (Self-Relationship)

Menghasilkan tabel yang tetap sama tetapi ditambah FK yang menunjuk dirinya sendiri.

11. Ternary Relationship

Menghasilkan satu tabel relasi tambahan dengan FK ke semua entitas.

12. Generalisasi / Spesialisasi

Dapat menggunakan dua pendekatan:

Superclass–Subclass (Tabel induk → tabel anak)

Hanya tabel subclass, dimana tabel tersebut menyimpan atribut superclass.

13. Agregasi

Relasi kompleks (misalnya relasi dari relasi) menghasilkan tabel baru yang mengacu pada entitas terkait.

🧪 Studi Kasus: Skema Pembayaran Apotik

ERD apotik memiliki entitas seperti:

Pasien, Pegawai, Obat, Resep, Pembayaran, Kategori_Obat, Retur, dll.

Dikonversi menjadi 13 tabel, misalnya:

PASIEN

RESEP

OBAT

DETAIL_OBAT

PEGAWAI

PEMBAYARAN

RETUR

DETAIL_RETUR

KATEGORI_OBAT

dan lainnya.

Semua tabel memiliki hubungan yang digambarkan menggunakan foreign key dan tanda panah referensi.

---------------------------------------------
BAB 2 — Pengantar Basis Data & DDL

Bab ini membahas pengenalan database, DBMS, MySQL, cara instalasi, serta penggunaan perintah dasar DDL untuk membuat database.

🎯 Tujuan Pembelajaran

Memahami konsep dasar basis data dan DBMS.

Mengetahui aplikasi pendukung MySQL seperti XAMPP.

Mampu mengakses MySQL server & client.

Memahami tipe data MySQL.

Dapat menggunakan DDL untuk membuat database.

📚 Apa itu Database & DBMS?
Database

Kumpulan data yang:

Terorganisir,

Terstruktur,

Disimpan secara sistematis dalam tabel,

Dikelola oleh DBMS.

DBMS (Database Management System)

Aplikasi pengelola database, contoh:

MySQL

PostgreSQL

Oracle

SQL Server

MariaDB

🛠️ MySQL

MySQL adalah DBMS yang:

Cepat dan reliable

Open source

Mendukung multithread

Mendukung multiuser

Dapat dijalankan di berbagai OS

Alasan menggunakan MySQL:

Gratis

Banyak komunitas

Banyak digunakan di web development

Terintegrasi dengan PHP dan XAMPP

⚙️ Instalasi MySQL

Direkomendasikan menggunakan XAMPP, karena sudah termasuk:

Apache

MariaDB/MySQL

PHP

phpMyAdmin

🖥️ Mengakses MySQL

Melalui CMD:

cd C:\xampp\mysql\bin
mysql -u root -p


Jika password belum dibuat, cukup tekan enter.

📁 Struktur File Database MySQL
OS	Lokasi Database	Lokasi Web
Windows	C:\xampp\mysql\data	C:\xampp\htdocs
Linux	/opt/lampp/var/mysql	/opt/lampp/htdocs
🧷 MySQL Client

Aplikasi CLI (Command Line Interface) bernama:

mysql.exe


Semua perintah harus diakhiri titik koma (;).

🔤 Tipe Data MySQL

Beberapa tipe data penting:

Tipe	Deskripsi
INT	Bilangan bulat
FLOAT	Desimal
CHAR	Panjang tetap
VARCHAR	Panjang dinamis
DATE	Format tanggal YYYY-MM-DD
DATETIME	Tanggal & waktu
BLOB	Data biner
📐 DDL (Data Definition Language)

DDL digunakan untuk membuat atau mengubah struktur database.

1. Membuat Database
CREATE DATABASE praktikum;

2. Melihat Daftar Database
SHOW DATABASES;

3. Menggunakan Database
USE praktikum;

4. Menghapus Database
DROP DATABASE praktikum;
