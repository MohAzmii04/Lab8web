# Lab8web

Nama : Mohammad Azmi Abdussyukur

NIM  : 312210109

Kelas : TI.22.A1

## DAFTAR ISI <br>
| No | Description | Link |
|-----|------|-----|
|1|Instruksi Praktikum|[Click Here](#instruksi-praktikum)|
|2|Langkah-langkah Praktikum|[Click Here](#langkah-langkah-praktikum)|
|3|Result|[Click Here](#result)|

## Instruksi Praktikum
1. Persiapkan text editor misalnya VSCode.
2. Buat folder baru dengan nama lab8_php_database pada docroot webserver (htdocs)
3. Ikuti langkah-langkah praktikum yang akan dijelaskan berikutnya.

## Langkah-langkah Praktikum
1. Persiapan Untuk memulai membuat aplikasi CRUD sederhana, yang perlu disiapkan adalah database server menggunakan MySQL. Pastikan MySQL Server sudah dapat dijalankan melalui XAMPP.

2. Menjalankan MySQL Server Untuk menjalankan MySQL Server dari menu XAMPP Control.

3. Membuat Database: Studi Kasus Data Barang
```
CREATE DATABASE latihan1;
```
```
CREATE TABLE data_barang (
    id_barang int(10) auto_increment Primary Key,
    kategori varchar(30),
    nama varchar(30),
    gambar varchar(100),
    harga_beli decimal(10,0),
    harga_jual decimal(10,0),
    stok int(4)
);
```

<img width="960" alt="phpadmin" src="https://github.com/MohAzmii04/Lab8web/assets/115864496/6d926fa3-fb0c-4905-9142-ba5b0ceb427a">

4. Menambah Data
```
INSERT INTO data_barang (kategori, nama, gambar, harga_beli, harga_jual, stok)
VALUES ('Elektronik', 'HP Samsung Android', 'hp_samsung.jpg', 2000000, 2400000, 5),
('Elektronik', 'HP Xiaomi Android', 'hp_xiaomi.jpg', 1000000, 1400000, 5),
('Elektronik', 'HP OPPO Android', 'hp_oppo.jpg', 1800000, 2300000, 5);
```

![Screenshot (150)](https://github.com/syifaaurellia/Lab8web/assets/115867244/db3281b0-e06c-4461-98e6-33821fedf087)


5. Membuat Program CRUD, Buat folder lab8_php_database pada root directory web server (d:\xampp\htdocs)

6. Membuat file koneksi database, Buat file baru dengan nama `koneksi.php`
```
<?php
$host = "localhost";
$user = "root";
$pass = "";
$db = "latihan1";
$conn = mysqli_connect($host, $user, $pass, $db);
if ($conn == false)
{
    echo "Koneksi ke server gagal.";
    die();
} #else echo "Koneksi berhasil";
?>
```

> Buka melalui browser untuk menguji koneksi database untuk menyampilkan pesan koneksi berhasil, ***uncomment*** pada perintah echo “koneksi berhasil”;

<img width="960" alt="koneksi" src="https://github.com/MohAzmii04/Lab8web/assets/115864496/d0cb9d41-5653-4618-a414-ad151e4aa3fb">

7. Membuat file index untuk menampilkan data (Read), buat file baru dengan nama `index.php`

> **Akses File-->>**[index.php](index.php)

<img width="960" alt="index" src="https://github.com/MohAzmii04/Lab8web/assets/115864496/b4e1cc41-d2fe-4965-af46-e849a2c3e147">

8. Menambah Data (Create), buat file baru dengan nama `tambah.php`

> **Akses File-->>**[tambah.php](tambah.php)

<img width="960" alt="tambah" src="https://github.com/MohAzmii04/Lab8web/assets/115864496/31db3a2e-167c-4dd1-9b8c-b5a906014d99">

9. Mengubah Data (Update), buat file baru dengan nama `ubah.php`

> **Akses File-->>**[ubah.php](ubah.php)

<img width="960" alt="Cuplikan layar 2023-11-28 202906" src="https://github.com/MohAzmii04/Lab8web/assets/115864496/2998a460-2584-4eb5-afda-85da40c4838f">

10. Menghapus Data (Delete), buat file baru dengan nama `hapus.php`
```
<?php
include_once 'koneksi.php';
$id = $_GET['id'];
$sql = "DELETE FROM data_barang WHERE id_barang = '{$id}'";
$result = mysqli_query($conn, $sql);
header('location: index.php');
>
```

## Result



https://github.com/syifaaurellia/Lab8web/assets/115867244/d6c5e596-e0e8-40cc-bdf3-c917d7c9292f


## Finish, Terima kasih
