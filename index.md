## 1) BOX MODEL (Wajib dipahami untuk bikin “card” rapi)

Box model itu struktur “kotak” elemen HTML:

**content**: isi (teks/gambar)

**padding**: jarak isi ke border

**border**: garis tepi

**margin**: jarak antar elemen (jarak antar card)

Contoh penerapan di card:

`padding` biar isi tidak nempel

`border` biar keliatan “kartu”

`margin` biar antar card ada jarak

`box-sizing: border-box;` biar ukuran card stabil (padding+border ikut dihitung)

---

## 2) DISPLAY (kunci: card sejajar pakai inline-block)

Karena diminta **inline-block**, kita pakai:

`display: inline-block;` → elemen bisa **sejajar** tapi masih bisa punya **width/height**

Tambahkan `vertical-align: top;` supaya atasnya sejajar rapi

Trik penting: inline-block biasanya ada “spasi” antar elemen dari whitespace HTML. Solusi gampang:

rapatkan tag HTML, atau

set `font-size: 0;` di container lalu balikin `font-size` di card.

---

## 3) POSITION (untuk badge/label di dalam card)

Paling gampang untuk card:

Card: `position: relative;`

Badge/label: `position: absolute; top: ...; right: ...;`

Ini bikin label “PROMO” nempel di pojok card tanpa ganggu layout utama.

Tahap 1 — Buat struktur HTML dasar (3 menu)

Buat file `index.html`, isi dulu HTML-nya (tanpa CSS dulu):

```
<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Menu Makanan</title>
</head>
<body>
  <h1>Menu Makanan</h1>

  <div class="menu-wrap">
    <div class="card">
      <span class="badge">PROMO</span>
      <h3>Nasi Goreng Spesial</h3>
      <p class="desc">Nasi goreng dengan ayam, telur, dan sayuran segar.</p>
      <p class="price">Rp 25.000</p>
    </div>

    <div class="card">
      <span class="badge">BEST</span>
      <h3>Mie Ayam Bakso</h3>
      <p class="desc">Mie kenyal dengan ayam bumbu, bakso, dan kuah gurih.</p>
      <p class="price">Rp 22.000</p>
    </div>

    <div class="card">
      <span class="badge">NEW</span>
      <h3>Sate Ayam</h3>
      <p class="desc">Sate ayam bumbu kacang, disajikan dengan lontong.</p>
      <p class="price">Rp 30.000</p>
    </div>
  </div>
</body>
</html>
```

Hasilnya: masih teks biasa, belum seperti card.

---

## Tahap 2 - Tambahkan CSS dasar (font + background)

Di `<head>`, tambahkan `<style>`:

```
<style>
  body {
    font-family: Arial, sans-serif;
    background: #f5f5f5;
    margin: 0;
    padding: 24px;
  }

  h1 { margin: 0 0 16px; }
</style>
```

Hasil: halaman lebih rapi, ada padding.

---

## Tahap 3 - Bentuk “card” dengan BOX MODEL

Tambahkan ini di `<style>`:

```
* { box-sizing: border-box; }   /* BOX MODEL: ukuran stabil */

.card {
  width: 260px;
  padding: 14px;                /* BOX MODEL: ruang dalam */
  margin: 10px;                 /* BOX MODEL: jarak antar card */
  border: 1px solid #ddd;       /* BOX MODEL: tepi card */
  border-radius: 12px;
  background: white;
}
.desc { color: #555; line-height: 1.4; }
.price { font-weight: bold; }
```

Hasil: sudah terlihat seperti kartu, tapi masih turun ke bawah (belum sejajar).

---

## Tahap 4 - Buat card sejajar pakai DISPLAY: inline-block

Masih di CSS, ubah/tambah:

```
.card {
  display: inline-block;   /* DISPLAY: sejajarkan card */
  vertical-align: top;     /* biar atasnya sejajar */
}
```

Hasil: card mulai sejajar.

---

## Tahap 5 -Hilangkan “spasi aneh” antar inline-block (trik umum)

Kadang inline-block ada jarak karena spasi di HTML. Cara gampang:

.menu-wrap { font-size: 0; }  
.card { font-size: 14px; } /\* balikin ukuran teks card \*/

Hasil: jarak jadi lebih konsisten (hanya dari margin).

---

## Tahap 6 - Tambahkan POSITION untuk badge pojok card

Agar badge nempel pojok kanan atas:

```
.card { position: relative; } /* wadah */

.badge {
  position: absolute; /* POSITION: nempel di pojok */
  top: 10px;
  right: 10px;
  background: #ff4757;
  color: white;
  padding: 6px 10px;
  border-radius: 999px;
  font-size: 12px;
  font-weight: bold;
}
```

Hasil: label PROMO/BEST/NEW muncul di pojok card.

---

## Tahap 7 — (Opsional) Tambahkan gambar biar lebih “menu makanan”

Tambahkan di HTML **di dalam card**, taruh sebelum `<h3>`:

```
<img src="https://picsum.photos/400/300?random=11" alt="Nasi Goreng" />
```

Untuk card lain ganti `random=12`, `random=13`.

Lalu tambahkan CSS:

```
.card img {
  width: 100%;
  height: 150px;
  object-fit: cover;
  border-radius: 10px;
  display: block;
  margin-bottom: 10px;
}
```

# [**Kerjakan Tugas**](tugas.md)