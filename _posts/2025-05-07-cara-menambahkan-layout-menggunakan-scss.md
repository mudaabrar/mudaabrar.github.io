---
layout: post
title: "Cara membuat layout menggunakan scss"
---

penjelasan tentang SCSS

**SASS dan SCSS**

SASS dan SCSS adalah dua sintaks dari preprocessor SASS (Syntactically Awesome Stylesheets),

yang masing-masing menawarkan fitur-fitur tambahan untuk memperluas kemampuan dari CSS tradisional.

Meskipun keduanya memiliki fungsi yang sama, sintaksnya berbeda untuk menyesuaikan preferensi berbagai pengembang.

---

## **Apa itu scss?**

SCSS (Sassy CSS) adalah salah satu sintaks dari SASS yang menggunakan struktur mirip dengan CSS.

Hal ini memudahkan pengembang yang sudah terbiasa dengan CSS untuk beralih menggunakan fitur-fitur canggih yang ditawarkan SASS,

seperti variabel, mixin, dan nesting. File SCSS memiliki ekstensi .

scss dan sepenuhnya kompatibel dengan CSS standar, yang berarti Anda bisa menggunakan CSS yang valid di dalam file SCSS.

---

### Fitur Utama SCSS

- **Variabel**  
  Menyimpan nilai-nilai yang dapat digunakan kembali seperti warna dan font untuk memastikan konsistensi dalam styling.

- **Nesting**  
  Menyusun selector CSS secara hierarkis untuk meningkatkan keterbacaan kode.

- **Mixins**  
  Membuat blok gaya yang dapat digunakan kembali untuk menghindari pengulangan kode.

- **Inheritance (Pewarisan)**  
  Menggunakan `@extend` untuk berbagi gaya antar selector, sehingga menyederhanakan kode.

- **Partials dan Importing**  
  Memodulasi CSS dengan `@import` untuk menjaga agar gaya tetap terorganisir dan mudah dikelola.

---

### 1. Variabel
Gunakan variabel untuk menyimpan nilai yang sering digunakan, seperti warna dan font.

```scss
$primary-color: #3498db;

.button {
  background-color: $primary-color;
}
```
---

## 3.2 What is SASS?

SASS (Syntactically Awesome Stylesheets) adalah preprocessor utama yang memperluas CSS. SASS menyediakan alat yang kuat seperti variabel, aturan bertingkat (nested rules), mixin, dan fungsi, memungkinkan stylesheet yang lebih efisien dan terorganisir. 

SASS menggunakan sintaks berbasis indentasi, artinya tidak ada tanda kurung kurawal `{}` atau titik koma `;`, tidak seperti CSS biasa. File SASS menggunakan ekstensi `.sass`.

---

### Fitur Utama SASS:

- **Variables**: Mendefinisikan nilai yang dapat digunakan kembali seperti warna dan font.
- **Nesting**: Mengatur CSS dalam struktur visual yang hierarkis.
- **Partials**: Membagi file stylesheet besar menjadi file kecil menggunakan `@import`.
- **Mixins**: Menggunakan kembali aturan CSS di beberapa selector.
- **Inheritance**: Menggunakan `@extend` untuk berbagi style antar selector.

---

### Contoh SASS File:

```sass
/* .sass file */
$bgcolor: blue
$textcolor: red
$fontsize: 25px

/* Gunakan variabel */
body
  background-color: $bgcolor
  color: $textcolor
  font-size: $fontsize
```

output:

```SASS
body {
  background-color: blue;
  color: red;
  font-size: 25px;
}
```

---

## Use SCSS for Styling Layout

Untuk praktikum kali ini kita akan mengubah layout website agar lebih rapi dan menarik. Ikuti langkah-langkah berikut ini.

### 1. Update file `navigation.html`

Edit file `navigation.html` yang berada dalam folder `_includes` dengan kode berikut:

```html
<ul>
  {% for item in site.data.navigation %}
    <li>
      <a href="{{ item.link }}" 
         {% if page.url == item.link %} class="active"{% endif %}>
         {{ item.name }}
      </a>
    </li>
  {% endfor %}
</ul>
```

### 2.Update kode SCSS

Perbarui file main.scss dengan menambahkan kode SCSS sesuai kebutuhan styling-nya.

(Instruksi atau kodenya belum ditampilkan di gambar, namun kamu bisa lanjutkan bagian ini dengan contoh seperti di bawah jika dibutuhkan):

### SCSS Styling Layout

Berikut adalah contoh kode SCSS untuk mempercantik layout dasar website:

```scss
$primary-color: #3b7b3a;
$secondary-color: #fbcb05;
$font-stack: Helvetica, sans-serif;

body,
h1,
h2,
p {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: $font-stack;
  line-height: 1.6;
  background-color: #f4f4f4;
}

header {
  text-align: center;
  padding: 24px;
  color: #fff;
  background-color: $primary-color;
}

main {
  padding: 24px;
  margin-top: 24px;
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.1);
  background-color: #fff;
}

footer {
  text-align: center;
  padding: 8px;
  margin-top: 24px;
  color: #fff;
  background-color: $primary-color;
}

h2 {
  color: #333;
  margin-bottom: 8px;
}

nav {
  margin: 24px 0;

  ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    overflow: hidden;
    background-color: $primary-color;
  }

  li {
    float: left;

    a {
      display: block;
      color: white;
      text-align: center;
      padding: 8px 16px;
      text-decoration: none;

      &:hover:not(.active) {
        background-color: $secondary-color;
      }
    }
  }
}

.container {
  width: 80%;
  margin: auto;
  overflow: hidden;
}

.profile-picture {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  margin: 24px auto;
  background-color: $secondary-color;
}

.active {
  background-color: $secondary-color;
}
```

---

### Keunggulan SASS/SCSS:
- **Variabel**: Menyimpan nilai seperti warna, ukuran font, dsb.
- **Nesting**: Menyusun selector secara hierarkis agar lebih mudah dibaca.
- **Partials & Import**: Memecah file CSS menjadi bagian-bagian kecil.
- **Mixins**: Mengelompokkan kumpulan properti agar bisa digunakan ulang.
- **Inheritance**: Menggunakan `@extend` untuk mewarisi gaya dari selector lain.
- **Fungsi**: Mendukung fungsi bawaan dan pembuatan fungsi kustom.

---

### Kesimpulan:

SASS dan SCSS sangat membantu dalam pengembangan web modern dengan membuat stylesheet lebih modular, mudah dibaca, dan mudah dikelola.
SCSS lebih populer karena kompatibilitas sintaksisnya dengan CSS biasa, sehingga lebih mudah dipelajari oleh pemula.

