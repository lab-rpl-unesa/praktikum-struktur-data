# Praktikum 1
<div align="justify">
Pada minggu ini untuk menerapkan linked list dan basic operasinya pada program. Pada program linked list untuk menyimpan data supir yang terdaftar. Berikut adalah struktur nodenya :
</div>

```
Data Supir {
    Id        : Number
    Nama      : String
    Tgl Lahir : Date
    Kelamin   : Char
    Alamat    : String
}
```

## Admin Privileges
<div align="justify">
Pada sisi admin mampu untuk menambahkan dan mengubah data. Operasi yang dapat dilakukan antara lain menambahkan, mengubah, menghapus serta menampilkan data supir. Untuk menampilkan data supir seperti berikut :
</div>

```
|-------------------------|
|Nama     : Kim Jatim Park|
|Id       : 01234         |
|Tgl Lahir: 12-02-2001    |
|Kelamin  : Laki-Laki     |
|Alamat   : Surabaya      |
|-------------------------|
1. Next
2. Previous
3. Exit
```
<div align="justify">
Pada kasus ini diharapkan sebagai admin mampu untuk melakukan iterasi terhadap data supir, arah iterasi dikontrol menggunakan command 'next' atau 'previous' untuk mengakses data. Untuk data awal dapat dimulai pada index-0. Opsi 'exit' diberikan bila ingin kembali ke menu admin. Apabila saat menampilkan daftar supir sudah mencapai index terakhir, maka saat ingin melanjutkan daftar selanjutnya index akan kembali ke daftar supir pertama (index-0)
</div>

</br>

<div align = "justify">
Untuk menambahkan data, input yang tersedia harus sesuai dengan struktur object yang diberikan (lihat di bawah).

</br>

```
Nama : > (Masukkan Nama)
Tgl Lahir : > (Masukkan Tgl Lahir dengan format dd-mm-yy)
Kelamin (l/p) : > (Masukkan kelamin berdasarkan pilihan)
Alamat : > Surabaya

Data berhasil ditambahkan !
```

Untuk Id akan ter-generate oleh program dengan pola seperti berikut :
- Id terdiri dari 5 digit
- 2 digit pertama merupakan urutan huruf pertama dan huruf terakhir yang dikurangi dari nama supir dan bernilai mutlak. Contoh nama "Sugeng Pangestu" karena huruf awal merupakan 'S' dan huruf terakhir merupakan 'U' maka 2 digit pertamanya adalah 19 - 21 maka hasilnya adalah 02
- Digit ke 3 hanya akan bernilai 1 atau 0, ini berdasarkan dari nilai pada variabel kelamin. Bila supir merupakan seorang pria maka digit ke 3 adalah 1, dan bila sebaliknya maka digit ke 3 adalah 0. Contoh supir Sugeng Pangestu merupakan seorang pria, maka 3 digit pertama Idnya adalah 021.
- Digit ke 4 didapatkan berdasarkan tgl lahir supir. Digit terakhir pada tanggal, bulan dan tahun dijumlahkan dan di modulus dengan 9. Misal Pak Sugeng memiliki tgl lahir 21-02-1999 maka 4 digit pertamanya adalah 0213
- Digit ke 5 akan bernilai 0 bila seandainya tidak ada Id yang sama. Namun bila terdapat kasus duplikasi Id pada 2 supir yang ada maka nilai digit ke 5 akan di increment dari nilai awalnya, dan bila masih terdapat duplikasi, nilainya akan terus di Increment. Bila nilai digit sudah mencapai angka 9 maka digitnya akan bertambah 1 yang semula 5 digit menjadi 6 digit. Hal ini akan terus dilakukan selama terjadi duplikasi Id.

Untuk mengedit identitas supir, admin dapat melakukan perubahan terhadap ke semua data supir kecuali Id, dan bila ada data supir yang mempengaruhi Id supir tersebut berubah maka Id tersebut juga ikut berubah. Proses pengubahan bisa dilakukan dengan mencari berdasarkan Id seperti berikut
```
Masukkan Id Supir yang ingin diubah > 02130

- Mengubah supir dengan Id 02130 -
1. Ubah Nama
2. Ubah Kelamin
3. Ubah Alamat
4. Ubah Tgl Lahir
> 1

Masukkan Nama yang baru > Sugeng Cihuy

Data Id 02130 telah berubah !
Nama      : Sugeng Cihuy
Id        : 16130
Kelamin   : Laki-laki
Tgl Lahir : 21-02-1999
Alamat    : Surabaya
```

Ketika admin ingin menghapus data juga dapat dilakukan dengan menggunakan Id supir.
```
Id yang ingin dihapus > 16130

Supir dengan data berikut akan dihapus :
Nama      : Sugeng Cihuy
Id        : 16130
Kelamin   : Laki-laki
Tgl Lahir : 21-02-1999
Alamat    : Surabaya
Lanjutkan ? (y/n) > y

Supir dengan Id 16130 berhasil dihapus !
```

Setelah menambahkan, mengubah ataupun menghapus sebuah data pastikan program akan langsung kembali ke dashboard admin.


</div>

## User Privileges
<div align="justify">
Pada bagian user mampu untuk menampilkan data dari supir yang tersedia. Untuk menampilkan data sama seperti yang admin lakukan.

</br>

```
|-------------------------|
|Nama     : Kim Jatim Park|
|Id       : 01234         |
|Tgl Lahir: 12-02-2001    |
|Kelamin  : Laki-Laki     |
|Alamat   : Surabaya      |
|-------------------------|
1. Next
2. Previous
3. Order
4. Exit
```
Pada kasus ini diharapkan sebagai user mampu untuk melakukan iterasi terhadap data supir, arah iterasi dikontrol menggunakan command 'next' atau 'previous' untuk mengakses data. Untuk data awal dapat dimulai pada index-0. Opsi 'exit' diberikan bila ingin kembali ke menu user.  Opsi order diberikan agar user dapat melakukan order taxi dengan sopir yang tampil pada display (lebih lengkapnya akan ada pada pertemuan berikutnya untuk sementara fungsi ini tidak perlu melakukan order). Apabila saat menampilkan daftar supir sudah mencapai index terakhir, maka saat ingin melanjutkan daftar selanjutnya index akan kembali ke daftar supir pertama (index-0)

<div>