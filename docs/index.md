--- 
title: "Belajar QGIS Mandiri"

author:
 - Dr. Firman Hadi^[Teknik Geodesi-Universitas Diponegoro, firmanhadi@me.com]
    
date: "2021-05-04"
site: bookdown::bookdown_site
documentclass: book
bibliography: [book.bib, packages.bib]
biblio-style: apalike
link-citations: yes
description: "Belajar sendiri Sistem Informasi Geografis"
cover-image: cover.png
favicon: "favicon.ico"

---

# Pengantar {-}

Sistem Informasi Geografis (SIG) mulai banyak digunakan di Indonesia sejak awal tahun 2000-an dan saat ini, istilah SIG relatif tidak asing lagi. SIG telah banyak digunakan sebagai alat untuk melakukan analisis dan menyajikan informasi terkait lokasi, seperti sebaran penyakit, sebaran titik api, dan lain sebagainya.

Salah satu pertanyaan yang seringkali diajukan kepada saya terkait penerapan aplikasi SIG untuk bidang ilmu Biologi adalah, "Apakah SIG dapat digunakan oleh bidang ilmu Biologi?". 

Jawabnya adalah bisa. Berikut ini adalah beberapa contoh penerapan SIG untuk aplikasi di bidang Biologi:

1. Memetakan sebaran populasi gajah di Sumatera.
2. Memperkirakan habitat yang cocok untuk reintroduksi satwa terancam punah.
3. Memetakan wilayah yang terkena epidemi demam berdarah

Hey, yang nomor tiga itu kan aplikasi di bidang kesehatan atau kedokteran? 

Loh, vektor penyakit demam berdarah itu apa? 

Nyamuk, kan? 

Nyamuk termasuk hewan dan orang-orang yang memahami bagaimana nyamuk ini berkembang biak, habitat seperti apa yang menunjang populasi nyamuk dan lainnya adalah orang Biologi. Benar tidak?

Masih banyak aplikasi lain yang tidak mungkin saya tuliskan satu-per-satu di sini. Yang jelas, SIG dapat digunakan sebagai alat untuk menganalisis permasalahan di bidang Biologi.

SIG adalah sebuah bidang ilmu yang bersifat interdisiplin. Idealnya, ketika ada permasalahan yang spesifik, maka diperlukan ahli yang mengerti tentang permasalahan tersebut dan seorang ahli yang dapat memetakan dan menganalisisnya secara spasial, apabila diperlukan. Namun, kondisi ideal ini jarang ditemukan. Seringkali seorang ahli Biologi harus mengkaji permasalahan tersebut sendirian, dan ia harus menggunakan SIG agar dapat mengikutsertakan variabel spasial dalam analisisnya. Dengan kondisi tersebut, ia akan "kelimpungan" karena harus belajar SIG dari nol, tanpa bantuan siapa-siapa. 

Dengan latar belakang tersebut, buku ini ditulis untuk membantu mereka yang memiliki latar belakang Biologi (juga bidang ilmu alamiah lain) untuk belajar bagaimana menggunakan SIG. Buku disusun dengan struktur mulai dari pendefinisian masalah hingga melakukan layout peta. Dengan adanya buku ini, diharapkan peneliti Biologi mampu memahami konsep dasar penginderaan jauh (inderaja) dan SIG serta mampu menerapkan aplikasi inderaja dan SIG untuk bidang yang dikajinya.

Sebagai catatan, walaupun judul buku ini hanya menyebutkan Sistem Informasi Geografis, isinya juga menjelaskan tentang Penginderaan Jauh (Inderaja) dan Global Positioning System (GPS). Inderaja, SIG dan GPS dikenal sebagai tiga serangkai yang tidak dapat dipisahkan ketika kita melakukan analisis spasial.

Oh ya, walaupun tujuannya adalah untuk membantu mahasiswa Biologi belajar SIG, Anda yang tertarik dengan SIG secara umum, tidak dilarang untuk membaca buku ini. 

Mudah-mudahan bermanfaat bagi kita semua.





