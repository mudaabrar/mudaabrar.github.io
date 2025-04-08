---
layout: post
title: "html link dan list"
---

penjelasan tentang html link dan lists pada html

![html link dan lists](/assets/images/move.jpg)

sumber:kickli.my.id


1). HTML Link (Hyperlink)

HTML link digunakan untuk membuat tautan ke halaman web lain, file, email, atau bagian tertentu dalam halaman yang sama.

Tag utama: <a> (anchor tag)

Atribut penting dalam <a>:

-href → Menentukan tujuan tautan.

-target="_blank" → Membuka tautan di tab baru.

-title → Menampilkan teks ketika kursor diarahkan ke link.

-mailto: → Membuka email client dengan alamat email tujuan.

2). HTML Lists

List dalam HTML adalah fungsi yang digunakan untuk menampilkan data secara berurutan ke bawah.
Penulisan list menggunakan tag dan terdapat dua jenis tampilan list yang bisa digunakan, yaitu ordered list dan unordered list.
Ordered list adalah list yang terurut, sedangkan unordered list adalah list yang tidak terurut. Terdapat tiga macam list di HTML, yaitu ordered list, unordered list, dan description list.

HTML menyediakan dua jenis daftar utama:

a. Ordered List (<ol>)
Daftar dengan urutan angka atau huruf.

Contoh:

```html
<ol>
  <li>Pertama</li>
  <li>Kedua</li>
  <li>Ketiga</li>
</ol>
```

Atribut:

-type="A" → Menggunakan huruf besar.

-type="a" → Menggunakan huruf kecil.

-type="I" → Menggunakan angka Romawi besar.

-type="i" → Menggunakan angka Romawi kecil.

b. Unordered List (<ul>)

Daftar dengan tanda bullet (•).

Contoh:

```html
<ul>
  <li>Apel</li>
  <li>Pisang</li>
  <li>Jeruk</li>
</ul>
```

Atribut:

-type="circle" → Bullet berbentuk lingkaran.

-type="square" → Bullet berbentuk kotak.

-type="disc" → Bullet default berbentuk titik.

Ringkasan Perbedaan:

-HTML Link (<a>): Digunakan untuk membuat tautan ke halaman atau sumber daya lain.

-HTML Lists (<ul>, <ol>, <li>): Digunakan untuk menampilkan daftar item, baik yang terurut maupun tak terurut.