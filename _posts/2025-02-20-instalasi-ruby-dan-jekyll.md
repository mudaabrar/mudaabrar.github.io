---
layout: post
title: "instalasi Ruby dan Jekyll"
---

penjelasan tentang instalasi ruby dan jekyll

![markdown](/assets/images/move.jpg)

sumber:kickli.my.id

1.2 Instalasi 


a) instalasi Ruby dan Jekyll

1). cek apakah ruby dan jekyll 

buka terminal atau command prompt,lalu ketik:

ruby -v 

cek ruby sudah terpasang, maka akan muncul versi ruby.

2). cek RubyGems

ketik perintah berikut:

gem -varian

3). cek GCC dan make

ketik perintah berikut:

gcc -v

g++ -v

make -v

jika belum terpasang,install terlebih dahulu MingGW (untuk Windows) atau gunakan package manager seperti apt (linux)

1. Download ruby installer

buka link berikut: https://rubyinstaller.org

pilih versi ruby2.7.0 atau lebih tinggi.

ikuti arahan untuk instalasi hingga selesai.

2. install jekyll dan bundler

setelah ruby terpasang,instal jekyll dan bundler dan perintah:

gem instal jekyll bundler

b) install Git

1). Download Git installer

buka link berikut: https://git-scm.com

pilih installer yang sesuai dengan sistem operasi (contoh: 64-bit untuk Windows).

2). lakukan instalasi

ikuti instruksi instalasi hingga selesai.

Setelah selesai, cek apakah Git sudah terpasang dengan perintah:

git --version

c) install Visual Studio code 

1). Download VSCode installer

Buka link berikut: https://code.visualstudio.com

Pilih installer sesuai dengan sistem operasi (contoh: 64-bit untuk Windows).

2). Lakukan Instalasi

Ikuti instruksi sampai selesai. 

d) install Google Chrome

1). Download Chrome Installer                            

Buka link berikut: https://www.google.com/ chrome

Klik tombol Download Chrome.

Ikuti instruksi instalasi hingga selesai.

1.3 personal web dengan jekyll dan GitHub Pages

1). Buat Akun GitHub

Buka https://github.com dan daftar akun.

2). Buat Repository GitHub

Buat repository baru dengan nama:

 username.github.io

 contoh : jika username github kamu mudaa, maka repository-nya adalah:

 mudaa.github.io

3). clone Repository ke lokal

Buka terminal atau Command Prompt, lalu jalankan:

git clone https://github.com/username/username.github.io.git

(Ganti username dengan username GitHub kamu)

4). Inisialisasi Jekyll di Folder Repository

Masuk ke folder repository:

cd username.github.io

Inisialisasi Jekyll:

bundle init

Perintah ini akan membuat file Gemfile di dalam folder proyek.

5). Edit Gemfile

Buka file Gemfile di VSCode, lalu tambahkan kode berikut:

source "https://rubygems.org"

gem "jekyll"

Lalu jalankan perintah:

bundle install

6). Buat File index.html

Buat file baru bernama index.html di dalam folder proyek, lalu isi dengan kode berikut:


7). Build dan Jalankan Jekyll

Jalankan perintah berikut untuk build website:

jekyll build

Untuk menjalankan server Jekyll:

jekyll serve

Cek di browser:

http://localhost:4000

8). Edit Gemfile.lock untuk Platform Linux

Buka file Gemfile.lock, lalu tambahkan platform linux pada bagian PLATFORMS:

PLATFORMS

  ruby
  x86_64-linux

9). Push Repository ke GitHub

Setelah berhasil dijalankan secara lokal, upload ke GitHub dengan perintah:

git add .

git commit -m "Initial commit"

git push origin main

10). Buat GitHub Actions untuk CI/CD

  - didalam repository github,buat folder .github/workflow.

  - buat file baru jekyll.yml di dalam folder tersebut,lalu tambahkan kode berikut:
     ''yaml name: Jekyll Deploy

on: push: branches: - main

jobs: build-deploy: runs-on: ubuntu-latest steps: - name: Checkout repository uses: actions/checkout@v2

  - name: Setup Ruby
    uses: ruby/setup-ruby@v1
    with:
      ruby-version: '2.7'

  - name: Install dependencies
    run: bundle install

  - name: Build site
    run: JEKYLL_ENV=production bundle exec jekyll build

  - name: Deploy to GitHub Pages
    uses: peaceiris/actions-gh-pages@v3
    with:
      github_token: $
      publish_dir: ./_site ```

1.Commit dan push ke GitHub:
git add .

git commit -m "Add GitHub Actions for 

Jekyll deployment"

git push origin main

✅ Selesai!

Sekarang website kamu bisa diakses di:

https://username.github.io

(Ganti username dengan username GitHub kamu).