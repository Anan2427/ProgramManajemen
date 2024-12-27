
Kode di atas adalah sebuah aplikasi manajemen inventaris sederhana berbasis Swing yang menggunakan SQLite sebagai basis data. Berikut adalah penjelasan bagian demi bagian:

1. Pendahuluan
Aplikasi ini mencakup:

Basis data SQLite untuk menyimpan data inventaris.
Antarmuka pengguna grafis (GUI) dengan Swing.
Operasi CRUD (Create, Read, Update, Delete).
2. Struktur Utama
main Method
Fungsi utama memanggil dua metode:

createTable() untuk memastikan tabel inventory ada di basis data.
createGUI() untuk membangun antarmuka pengguna.
3. Basis Data
Tabel inventory
Kolom:
id (INTEGER, PRIMARY KEY, AUTOINCREMENT): Identifikasi unik untuk setiap item.
name (TEXT): Nama item.
quantity (INTEGER): Jumlah item.
description (TEXT): Deskripsi item.
created_at dan updated_at (TEXT): Tanggal pembuatan dan pembaruan.
Operasi CRUD
createTable(): Membuat tabel jika belum ada.
addItem(String name, int quantity, String description): Menambahkan item baru.
updateItem(int id, String name, int quantity, String description): Memperbarui item berdasarkan id.
deleteItem(int id): Menghapus item berdasarkan id.
refreshTable(): Membaca data dari basis data dan menampilkannya di tabel.
Koneksi Basis Data
Semua operasi basis data menggunakan Connection dan PreparedStatement untuk menghindari serangan SQL Injection.

4. Antarmuka Pengguna (GUI)
Komponen Utama
Panel Input:

Teks input untuk id, name, quantity, dan description.
Tombol: Add Item, Update Item, dan Delete Item.
Tabel:

Menampilkan data dari tabel inventory.
Menggunakan DefaultTableModel untuk mengelola data.
Event Handling
Add Item:
Mengambil input dari pengguna.
Menyimpan data ke basis data menggunakan addItem().
Update Item:
Mengambil input termasuk id.
Memperbarui data di basis data dengan updateItem().
Delete Item:
Menghapus data berdasarkan id menggunakan deleteItem().
5. Utility
showInfo(String message) dan showError(String message)
Menampilkan pesan informasi atau kesalahan menggunakan JOptionPane.
getCurrentDate()
Mengembalikan tanggal dan waktu saat ini dalam format yyyy-MM-dd HH:mm:ss.
6. Alur Kerja
Aplikasi diluncurkan, tabel inventory dibuat jika belum ada.
GUI ditampilkan:
Pengguna dapat menambahkan, memperbarui, atau menghapus item.
Tabel memperlihatkan data terkini setelah setiap operasi.
Semua interaksi dengan basis data dilakukan secara dinamis.
