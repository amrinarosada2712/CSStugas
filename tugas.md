# SOAL PRAKTIKUM HTML & CSS

## Tema: Kartu Produk Toko Online

### Tujuan Praktikum

Mahasiswa mampu:

*   Memahami **Box Model**
*   Menggunakan **display: inline-block** untuk membuat card sejajar
*   Menggunakan **position: relative dan absolute**
*   Membuat tampilan **kartu produk sederhana seperti toko online**

---

# Tugas Praktikum

## 1\. Membuat Struktur HTML

Buat file bernama **produk.html**.

Buat halaman dengan judul:

```
Produk Toko Online
```

Di dalam halaman tersebut buat sebuah container dengan class:

```
product-wrap
```

Di dalamnya terdapat **3 kartu produk**.

Setiap card harus berisi:

*   **Label diskon / status produk**
*   **Gambar produk**
*   **Nama produk**
*   **Deskripsi singkat**
*   **Harga produk**

Contoh produk:

1.  Headphone Wireless
2.  Smart Watch
3.  Keyboard Gaming

---

# 2\. Menggunakan BOX MODEL

Terapkan **Box Model** pada setiap card.

Card harus memiliki:

*   `padding` agar isi tidak menempel
*   `border`
*   `margin`
*   `border-radius`
*   `background` putih

Tambahkan juga:

```
* {
  box-sizing: border-box;
}
```

agar ukuran card tetap stabil.

---

# 3\. Membuat Card Sejajar

Agar ketiga produk tampil **sejajar**, gunakan:

```
display: inline-block;
vertical-align: top;
```

Setiap card memiliki **lebar sekitar 250px**.

---

# 4\. Menghilangkan Spasi Antar Card

Gunakan teknik berikut agar jarak antar card lebih rapi:

```
.product-wrap {
  font-size: 0;
}

.card {
  font-size: 14px;
}
```

---

# 5\. Menambahkan Label Produk (POSITION)

Tambahkan label di pojok card seperti:

*   **DISKON**
*   **BEST SELLER**
*   **BARU**

Gunakan konsep **position**.

Contoh:

```
.card {
  position: relative;
}

.label {
  position: absolute;
  top: 10px;
  right: 10px;
}
```

Label harus memiliki:

*   background warna menarik
*   teks putih
*   padding kecil
*   border-radius

---

# 6\. Menambahkan Gambar Produk

Tambahkan gambar produk pada setiap card.

Gunakan gambar dari internet seperti:

```
https://picsum.photos/400/300
```

Atur gambar dengan CSS:

```
width: 100%;
height: 160px;
object-fit: cover;
border-radius: 10px;
```

---

# Output yang Diharapkan

Halaman web menampilkan **3 kartu produk toko online** yang tersusun sejajar.

Setiap card memiliki:

*   gambar produk
*   label status produk
*   nama produk
*   deskripsi
*   harga

### [**Contoh Tampilan Lihat disini**](https://github.com/amrinarosada2712/CSStugas/blob/main/contoh.png)

#### [**Kembali**](index.md)