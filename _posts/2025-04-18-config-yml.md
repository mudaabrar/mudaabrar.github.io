---
layout: post
title: "config.yml"
---

penjelasan tentang config.yml



config.yml jekyll

Dalam konteks Jekyll, config.yml (biasanya bernama _config.yml) adalah file konfigurasi utama yang mengatur bagaimana situs Jekyll dibangun dan dijalankan.

---

1.Fungsi _config.yml di Jekyll

File ini berisi pengaturan untuk:

-Nama dan deskripsi situs

-Struktur direktori

-Plugin yang digunakan

-Tema

-Variabel global yang bisa digunakan di layout atau post

-Pengaturan build (seperti URL base, exclude/include file, dll.)

---

2.Contoh _config.yml Sederhana


title: My Blog
description: A blog about tech and life
baseurl: "" # contoh: "/blog" jika disimpan di subdirektori
url: https://mudaabrar.github.io/
theme: minima

author:
  name: John Doe
  email: Abrar@example.com

plugins:
  - jekyll-feed
  - jekyll-seo-tag

exclude:
  - node_modules
  - README.md

---

3.Plugin dan Gemfile


Kalau kamu menambahkan plugin ke _config.yml, pastikan juga kamu tambahkan ke Gemfile:

_config.yml:

plugins:
  - jekyll-feed

  - jekyll-seo-tag

Gemfile:
  - gem "jekyll-feed"

   -gem "jekyll-seo-tag"


Tips Tambahan:


_config.yml bisa dibaca sebagai objek site di Liquid: site.title, site.description, dll.

Jangan simpan data sensitif (seperti API key) di sini jika repositori kamu publik.

Gunakan indentasi spasi, bukan tab. YAML sangat sensitif terhadap ini!

---

Kesimpulan tentang _config.yml di Jekyll



   -_config.yml adalah file konfigurasi utama Jekyll yang mengatur perilaku situs selama proses build.

   -Berisi informasi penting seperti: judul situs, URL, tema, plugin, variabel global, dan lainnya.

Bisa digunakan untuk:

   -Menentukan pengaturan dasar situs

   -Mengelola plugin dan tema

   -Membuat variabel kustom yang bisa digunakan di layout atau halaman

   -Mengatur koleksi konten khusus (seperti proyek, galeri, dsb.)

  -Formatnya YAML, yang mudah dibaca dan ditulis (gunakan spasi, bukan tab).

  -Bisa digabung dengan file konfigurasi tambahan (--config) untuk keperluan development vs production.

  -Semua nilai di dalamnya dapat diakses dengan tag Liquid ({{ site.nama_variabel }}) di template HTML.