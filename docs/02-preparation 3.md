

# Persiapan {#persiapan}

## Perangkat lunak


### Instalasi

QGIS berjalan pada Windows, berbagai distribusi Linux, Unix, Mac OS X, dan Android. Proyek QGIS menyediakan paket siap pakai serta instruksi untuk membangun dari kode sumber di https://qgis.org/en/site/forusers/download.html .

Pada bagian ini, kami akan menjelaskan tentang cara menginstal QGIS pada Windows, Ubuntu dan Mac OS X, serta bagaimana cara menghindari kesalahan yang paling umum.


    Instruksi pemasangan lebih lanjut untuk sistem operasi lain   yang didukung 
    tersedia di http://www.qgis.org/en/site/forusers/alldownloads.html .

Salah satu hal bagus dari proyek open source adalah kita memiliki pilihan di antara rilis yang berbeda. Itu sama dengan QGIS. Opsi-opsi berikut tersedia, kita dapat memilih satu atau dapat memilih semua versi.

- Rilis terbaru (LR) : Ini adalah versi yang mencakup fitur yang baru dikembangkan dan diuji. Saat ini dirilis setiap empat bulan (kecuali ketika versi LTR dirilis sebagai gantinya). Jika kita ingin tetap mengikuti perkembangan terbaru tetapi tidak nyaman menggunakan versi pengembangan, kita dapat menggunakan versi ini.

- Rilis jangka panjang (LTR) : Versi LTR direkomendasikan untuk penggunaan perusahaan dan akademis. Saat ini dirilis sekali per tahun pada akhir Februari. Ia menerima pembaruan perbaikan bug selama setidaknya satu tahun, dan fitur dan antarmuka pengguna tetap tidak berubah. Ini menjadikannya pilihan terbaik untuk materi pelatihan yang tidak boleh usang setelah beberapa bulan.

- Versi pengembang (DEV, master, atau pengujian): Versi DEV yang mutakhir berisi perkembangan terbaru dan terhebat, tetapi berhati-hatilah bahwa dalam beberapa hari, versi ini mungkin tidak akan berfungsi dengan andal seperti yang kita inginkan.

#### Instalasi di MS Windows

Di Windows, ada dua opsi berbeda untuk menginstal QGIS , _standalone installer_ dan _OSGeo4W installer_ :

- _Standalone installer_ adalah satu file besar untuk diunduh (sekitar 280 MB); file berisi rilis QGIS, Geographic Analyss Support System (GRASS), serta System for Automated Geoscientific Analyses (SAGA) dalam satu paket. Proses instalasi untuk file ini mudah, seperti instalasi program MS Windows pada umumnya.

- _OSGeo4W installer_ adalah alat instalasi kecil, fleksibel yang memungkinkan untuk mengunduh dan menginstal QGIS serta banyak lagi _tool_ OSGeo dengan semua dependensi mereka. Keuntungan utama dari penginstal ini dari _standalon installer_ adalah kemudahan dalam melakukan pembaruan (_update_) QGIS dan dependensinya. kita selalu dapat memiliki akses ke versi rilis saat ini dan versi pengembang jika kita mau, tetapi tentu saja, kita tidak pernah dipaksa untuk memperbarui. 

Kita dapat mengunduh installer OSGeo4W 32-bit dan 64-bit dari http://osgeo4w.osgeo.org (atau langsung dari http://download.osgeo.org/osgeo4w/osgeo4w-setup-x86.exe untuk 32- versi bit atau http://download.osgeo.org/osgeo4w/osgeo4w-setup-x86_64.exe untuk versi Windows 64-bit). Unduh versi yang cocok dengan sistem operasi yang kita miliki dan simpan! Nanti, setiap kali kita ingin mengubah atau memperbarui sistem, jalankan saja lagi.

Ketika pemasang OSGeo4W dimulai, kita dapat memilih antara Express Desktop Install , Express Web-GIS Install , dan Advanced Install .

Untuk menginstal versi QGIS LR , kita cukup memilih opsi Instal Desktop Express , dan dialog berikutnya akan mendaftar aplikasi desktop yang tersedia, seperti QGIS, uDig, dan GRASS GIS. Kita cukup memilih QGIS, klik __Next__ , dan konfirmasikan dependensi yang diperlukan dengan mengklik __Next__ lagi. Kemudian unduhan dan instalasi akan dimulai secara otomatis. Ketika instalasi selesai, akan ada pintasan desktop dan entri menu mulai untuk OSGeo4W dan QGIS .

Untuk menginstal QGIS LTR (atau DEV), kita harus melalui opsi Instalasi Lanjutan, seperti yang ditunjukkan pada Gambar \@ref(fig:fig01).

<div class="figure" style="text-align: center">
<img src="img/fig01.png" alt="Advanced Install" width="70%" />
<p class="caption">(\#fig:fig01)Advanced Install</p>
</div>





Jalur instalasi ini menawarkan banyak opsi, seperti __Download Without Installing__ dan __Install from Local Directory__ , yang dapat digunakan untuk mengunduh semua paket yang diperlukan pada satu mesin dan kemudian menginstalnya pada mesin tanpa akses Internet. Kita hanya memilih __Install from Internet__ , seperti yang ditunjukkan pada Gambar \@ref(fig:fig02) .

<div class="figure" style="text-align: center">
<img src="img/fig02.png" alt="Install from Internet" width="70%" />
<p class="caption">(\#fig:fig02)Install from Internet</p>
</div>



Saat memilih __Root Directory__, seperti yang ditunjukkan pada screenshot berikut, hindari karakter khusus seperti umlaut Jerman atau huruf dari huruf selain yang Latin default di jalur instalasi (seperti yang disebutkan sebelumnya), karena mereka dapat menyebabkan masalah di kemudian hari, untuk contoh, selama instalasi plugin, seperti yang ditunjukkan pada Gambar \@ref(fig:fig03).


<div class="figure" style="text-align: center">
<img src="img/fig03.png" alt="Pilih direktori root" width="70%" />
<p class="caption">(\#fig:fig03)Pilih direktori root</p>
</div>






Kemudian kita tentukan folder (__Local Package Directory__) di mana proses setup akan menyimpan file instalasi serta menyesuaikan nama menu Start. Kita biarkan pengaturan default seperti terlihat pada Gambar \@ref(fig:fig04).

<div class="figure" style="text-align: center">
<img src="img/fig04.png" alt="Memilih direktori untuk local package" width="70%" />
<p class="caption">(\#fig:fig04)Memilih direktori untuk local package</p>
</div>


Dalam pengaturan koneksi Internet, biasanya tidak perlu mengubah pengaturan default, tetapi jika mesin, misalnya, tersembunyi di belakang proxy, kita akan dapat menentukannya di sini.

<div class="figure" style="text-align: center">
<img src="img/fig05.png" alt="Memilih tipe koneksi internet" width="70%" />
<p class="caption">(\#fig:fig05)Memilih tipe koneksi internet</p>
</div>

Kemudian kita dapat memilih situs unduhan. Pada saat penulisan buku ini, ada tiga server unduh yang tersedia, seperti terlihat pada Gambar \@ref(fig:fig06). Dalam tutorial ini, kita memilih http://download.osgeo.org .

<div class="figure" style="text-align: center">
<img src="img/fig06.png" alt="Memilih alamat download" width="70%" />
<p class="caption">(\#fig:fig06)Memilih alamat download</p>
</div>


Setelah installer mengambil informasi paket terbaru dari server OSGeo, kita dapat memilih paket untuk instalasi. QGIS LTR terdaftar dalam kategori desktop sebagai qgis-ltr (dan versi DEV terdaftar sebagai qgis-dev). Untuk memilih versi LTR untuk instalasi, klik pada teks yang bertuliskan Lewati , dan itu akan mengubah dan menampilkan nomor versi, seperti yang ditunjukkan pada Gambar \@ref(fig:fig07).

<div class="figure" style="text-align: center">
<img src="img/fig07.png" alt="Memilih paket yang akan diinstal" width="70%" />
<p class="caption">(\#fig:fig07)Memilih paket yang akan diinstal</p>
</div>


Seperti yang Anda lihat pada tangkapan layar berikut, penginstal akan secara otomatis memilih semua dependensi yang diperlukan (seperti GDAL , SAGA , OTB , dan GRASS ), jadi tidak perlu khawatir tentang ini.

<div class="figure" style="text-align: center">
<img src="img/fig08.png" alt="Mencentang pilihan untuk dependensi" width="70%" />
<p class="caption">(\#fig:fig08)Mencentang pilihan untuk dependensi</p>
</div>


Setelah mengeklik __Next__ , unduhan dan pemasangan dimulai secara otomatis, seperti pada versi Express . Kita mungkin memperhatikan paket-paket QGIS lain yang tersedia yang disebut qgis-ltr-dev dan qgis-rel-dev . Ini berisi perubahan terbaru (ke versi LTR dan LR , masing-masing), yang akan dirilis sebagai versi perbaikan bug sesuai dengan jadwal rilis. Ini membuat paket-paket ini pilihan yang baik jika kita mengalami masalah dengan rilis yang telah diperbaiki baru-baru ini tetapi rilis versi perbaikan bug belum keluar.




#### Instalasi di Ubuntu

Di Ubuntu , proyek QGIS menyediakan paket untuk versi LTR , LR , dan DEV . Pada saat penulisan buku ini, versi Ubuntu Bionic , Artful , Xenial , dan Trusty didukung, tetapi kita dapat menemukan informasi terbaru di http://www.qgis.org/en/site/forusers/alldownloads.html# debian-ubuntu . Perlu diketahui, bahwa kita hanya dapat menginstal satu versi pada satu waktu.

Pada bagian ini, proses untuk menginstal QGIS 3 ( LR ) di Ubuntu 18,04 Bionic Beaver akan dijelaskan. Kita dapat merujuk ke tautan sebelumnya untuk menginstal versi QGIS LTR atau DEV .

1. Pertama, Kita tambahkan repositori QGIS 3 pada file sources.list pada mesin Bionic Beaver Ubuntu 18.04.

Edit file /etc/apt/sources.list dengan perintah berikut:

```
    $ sudo nano /etc/apt/sources.list
```

2. Kita tambahkan repositori spesifik QGIS 3 Ubuntu 18.04. Nama kode Ubuntu Bionic Beaver adalah bionic.

Tambahkan baris berikut ke bagian atas atau bawah file /etc/apt/sources.list:

```
    deb https://qgis.org/debian bionic main
```

Gambar berikut menunjukkan tampilannya setelah baris apt QGIS 3 ditambahkan ke file /etc/apt/sources.list.

<div class="figure" style="text-align: center">
<img src="img/fig4.png" alt="Menambahkan repository di sources.list" width="60%" />
<p class="caption">(\#fig:fig4)Menambahkan repository di sources.list</p>
</div>




Jika menggunakan nano cukup tekan Ctrl + o sekali untuk menyimpan baris apt QGIS 3 ke file /etc/apt/sources.list, dan simpan dengan menekan Enter .

3. Selanjutnya adalah mengimpor kunci GPG dari QGIS 3 dengan perintah berikut:

```
    $ wget -O - https://qgis.org/downloads/qgis-2017.gpg.key | gpg --import
```

GPG key harus ditambahkan ke mesin Ubuntu 18.04 Bionic Beaver.

GPG key dapat diverifikasi apakah telah diimpor dengan benar menggunakan perintah berikut:

```
    $ gpg --fingerprint CAEB3DC3BDF7FB45
```

<div class="figure" style="text-align: center">
<img src="img/fig5.png" alt="Verifikasi GPG key" width="60%" />
<p class="caption">(\#fig:fig5)Verifikasi GPG key</p>
</div>



4. Proses penambahan kunci GPG QGIS 3 ke manajer paket apt ini sangat penting, apabila tidak dilakukan atau tidak berhasil, cache repositori paket apt dari repositori QGIS 3 tidak akan dapat diperbaharui. Ini berarti kita tidak akan dapat mengunduh dan menginstal QGIS 3 di Ubuntu 18.04 .

Untuk menambahkan GPG key ke manajer paket apt, jalankan perintah berikut:

```
    $ gpg --export --armor CAEB3DC3BDF7FB45 | sudo apt-key add -
```

GPG key harus ditambahkan ke manajer paket apt.


<div class="figure" style="text-align: center">
<img src="img/fig6.png" alt="Menambahkan GPG key" width="60%" />
<p class="caption">(\#fig:fig6)Menambahkan GPG key</p>
</div>


5. Sekarang perbaharui cache repositori paket apt dari Ubuntu 18.04 Bionic Beaver dengan perintah berikut:

```
    $ sudo apt-get update
```

6. Selanjutnya kita dapat menginstal QGIS 3 dengan perintah berikut:

```
$ sudo apt-get install qgis python-qgis qgis-plugin-grass
```

Proses pengunduhan dan pemasangan QGIS 3 harus dimulai. Ini akan membutuhkan waktu.

Setelah instalasi selesai, kita dapat menemukan Menu Aplikasi denganlogo QGIS Desktop seperti yang ditunjukkan pada tangkapan layar di bawah ini. Klik pada logo Desktop QGIS.

<div class="figure" style="text-align: center">
<img src="img/fig7.png" alt="Menjalankan QGIS Desktop di Ubuntu" width="60%" />
<p class="caption">(\#fig:fig7)Menjalankan QGIS Desktop di Ubuntu</p>
</div>



#### Instalasi di Mac OS X

Langkah-langkah umum untuk menginstal QGIS pada Mac adalah sebagai berikut:

1. Sebagai langkah awal, ubah preferensi keamanan Mac Mengizinkan aplikasi yang diunduh dari mana saja .

2. Mac OS X QGIS file instalasi yang tersedia dari https://www.qgis.org/en/site/forusers/download.html. Ada dua versi yang tersedia, Latest release (QGIS 3.12) dan Long-term release (QGIS 3.10). Kita dapat memilih salah satu, tidak ada perbedaan signifikan antara kedua rilis tersebut.


<div class="figure" style="text-align: center">
<img src="img/mac.png" alt="Pilihan file instalasi untuk Mac OS X" width="70%" />
<p class="caption">(\#fig:figmac)Pilihan file instalasi untuk Mac OS X</p>
</div>


### Setting QGIS

#### Environment

Ketika kita menginstal QGIS, akan ada dua aplikasi: QGIS Desktop dan QGIS Browser. Apabila kita terbiasa dengan ArcGIS, Browser QGIS adalah aplikasi yang mirip dengan ArcCatalog. Ini adalah aplikasi kecil yang digunakan untuk melihat pratinjau data spasial dan metadata terkait. 

Secara default, QGIS akan menggunakan bahasa default sesuai sistem operasi. Untuk mengikuti tutorial dalam buku ini, disarankan untuk mengubah bahasa ke bahasa Inggris dengan masuk ke __Pengaturan | Opsi | Lokal__ .

Saat menjalankan QGIS untuk pertama kali, toolbar mungkin tersusun tidak seperti yang diinginkan. Agar dapat bekerja secara efisien, disarankan untuk mengatur ulang toolbar (demi kelengkapan, kita aktifkan semua toolbar di Toolbars, yang ada di menu View). Tempatkan beberapa toolbar di perbatasan layar kiri dan kanan untuk menghemat tampilan layar vertikal, terutama pada tampilan layar lebar.

Selain itu, kita akan mengaktifkan browser file dengan menavigasi ke __View | Panel | Panel Browser __. Ini akan membuat akses cepat ke data spasial. Pada akhirnya, jendela QGIS di layar akan terlihat mirip dengan tangkapan layar berikut:

<div class="figure" style="text-align: center">
<img src="img/qgis.png" alt="Tampilan QGIS" width="70%" />
<p class="caption">(\#fig:qgis)Tampilan QGIS</p>
</div>


#### Plugin

Untuk mulai menggunakan plugin, kita harus tahu cara mengunduh, menginstal, dan mengaktifkannya. Untuk melakukan ini, kita akan belajar cara menggunakan __Plugin Installer__ dan __Plugin Manager__.

##### Mengatur plugin

- Untuk membuka __Plugin Manager__ , klik pada item menu __Plugins → Manage__ dan __Install Plugins__.

<div class="figure" style="text-align: center">
<img src="img/qgis2.png" alt="Menu untuk instal plugin" width="70%" />
<p class="caption">(\#fig:qgis2)Menu untuk instal plugin</p>
</div>


- Pilih menu __Settings__, centang __Show alos experimental plugins__ dan klik __Reload Repository__.

<div class="figure" style="text-align: center">
<img src="img/qgis3.png" alt="Setting repositori untuk plugin" width="70%" />
<p class="caption">(\#fig:qgis3)Setting repositori untuk plugin</p>
</div>

<div class="figure" style="text-align: center">
<img src="img/qgis4.png" alt="Plugin yang tersedia di QGIS" width="70%" />
<p class="caption">(\#fig:qgis4)Plugin yang tersedia di QGIS</p>
</div>





##### Menginstal Plugin

- Untuk menginstal Plugin gunakan menu pencarian, ketik "Classification", pilih __Semi Automatic Classification Plugin__ dan klik __Install Plugin__.

<div class="figure" style="text-align: center">
<img src="img/qgis5.png" alt="Instalasi plugin Semi-Automatic Classification Plugin" width="70%" />
<p class="caption">(\#fig:qgis5)Instalasi plugin Semi-Automatic Classification Plugin</p>
</div>

<div class="figure" style="text-align: center">
<img src="img/qgis6.png" alt="Plugin Semi-Automatic Classification Plugin telah terinstal" width="70%" />
<p class="caption">(\#fig:qgis6)Plugin Semi-Automatic Classification Plugin telah terinstal</p>
</div>


##### Plugin penting

Setiap pengguna QGIS memiliki preferensi dalam pengaturan plugin. Dari 600-an plugin QGIS, ada beberapa plugin yang sering mungkin sering digunakan, yaitu (1) __OpenLayers__, (2) __QuickMapServices__, dan  (3) __Temporal/Spectral Profile Tool__. Silahkan instal ketiga plugin ini, kita akan menggunakannya dalam tutorial di bagian yang lain.


## Data

Data citra satelit yang akan digunakan untuk mendapatkan informasi tutupan lahan adalah citra Landsat (Landsat 5 TM, Landsat 7 ETM+ dan Landsat 8). Data citra akan diunduh melalui Semi Automatic Classification Plugin (SCP Plugin). SCP Plugin akan mencari arsip data di tiga situs Earth Resources Observation and Science / EROS (https://ers.cr.usgs.gov), Earthdata (https://urs.earthdata.nasa.gov) dan Sentinel Data Hub (https://scihub.copernicus.eu/apihub). Untuk mengakses ketiga situs tersebut, Anda harus melakukan registrasi terlebih dahulu.

### EROS


Tahapan membuat akun di EROS adalah sebagai berikut :

1. Membuat Username yang unik dan mengisikan password sesuai dengan ketentuan yang ada.

<div class="figure" style="text-align: center">
<img src="img/eros1.png" alt="Registrasi user EROS" width="70%" />
<p class="caption">(\#fig:eros1)Registrasi user EROS</p>
</div>


2. Pilih sektor pekerjaan dan jawab pertanyaan lainnya seperti pada gambar, kemudian klik __Continue__.

<div class="figure" style="text-align: center">
<img src="img/eros2.png" alt="Registrasi user EROS - 2" width="70%" />
<p class="caption">(\#fig:eros2)Registrasi user EROS - 2</p>
</div>

<div class="figure" style="text-align: center">
<img src="img/eros3.png" alt="Registrasi user EROS - 3" width="70%" />
<p class="caption">(\#fig:eros3)Registrasi user EROS - 3</p>
</div>

3. Pada tahap ini, isikan bagian-bagian seperti pada gambar, plus Zip/Postal Code dan Telephone. Klik __Continue__ setelah selesai.

<div class="figure" style="text-align: center">
<img src="img/eros4.png" alt="Registrasi user EROS - 4" width="70%" />
<p class="caption">(\#fig:eros4)Registrasi user EROS - 4</p>
</div>

<div class="figure" style="text-align: center">
<img src="img/eros5.png" alt="Registrasi user EROS - 5" width="70%" />
<p class="caption">(\#fig:eros5)Registrasi user EROS - 5</p>
</div>





4. Pada tahapan ini, silahkan review apa yang telah Anda isikan. Klik __Submit Registration__ untuk melanjutkan.

<div class="figure" style="text-align: center">
<img src="img/eros6.png" alt="Registrasi user EROS - 6" width="70%" />
<p class="caption">(\#fig:eros6)Registrasi user EROS - 6</p>
</div>



5. Gambar berikut menunjukkan proses registrasi telah selesai.

<div class="figure" style="text-align: center">
<img src="img/eros7.png" alt="Registrasi user EROS - 7" width="70%" />
<p class="caption">(\#fig:eros7)Registrasi user EROS - 7</p>
</div>


6. Cek email Anda dan klik tautan yang ada untuk konfirmasi proses registrasi.

<div class="figure" style="text-align: center">
<img src="img/eros8.png" alt="Cek email dari EROS" width="70%" />
<p class="caption">(\#fig:eros8)Cek email dari EROS</p>
</div>


7. Isikan Username yang telah didaftarkan sebelumnya dan klik __Submit__.

<div class="figure" style="text-align: center">
<img src="img/eros9.png" alt="Konfirmasi registrasi user EROS" width="70%" />
<p class="caption">(\#fig:eros9)Konfirmasi registrasi user EROS</p>
</div>



8. Proses pendaftaran telah selesai dan Anda dapat login.

<div class="figure" style="text-align: center">
<img src="img/eros10.png" alt="User telah aktiff" width="70%" />
<p class="caption">(\#fig:eros10)User telah aktiff</p>
</div>


9. Apabila _login_ berhasil, Anda dapat mengakses halaman [https://earthexplorer.usgs.gov](https://earthexplorer.usgs.gov).

<div class="figure" style="text-align: center">
<img src="img/eros11.png" alt="Akses EarthExplorer dengan user yang telah terdaftar" width="70%" />
<p class="caption">(\#fig:eros11)Akses EarthExplorer dengan user yang telah terdaftar</p>
</div>


### Earthdata

Tahapan membuat akun di Earthdata adalah sebagai berikut :

1. Klik __Register for a profile__

<div class="figure" style="text-align: center">
<img src="img/earth1.png" alt="Registrasi user Earthdata" width="70%" />
<p class="caption">(\#fig:earth1)Registrasi user Earthdata</p>
</div>



2. Masukkan username yang unik dan password sesuai dengan ketentuan yang dijelaskan pada kotak sebelah kanan.

<div class="figure" style="text-align: center">
<img src="img/earth2.png" alt="Registrasi user Earthdata - 2" width="70%" />
<p class="caption">(\#fig:earth2)Registrasi user Earthdata - 2</p>
</div>


3. Isi informasi yang diminta 


<div class="figure" style="text-align: center">
<img src="img/earth3.png" alt="Registrasi user Earthdata - 3" width="70%" />
<p class="caption">(\#fig:earth3)Registrasi user Earthdata - 3</p>
</div>


<div class="figure" style="text-align: center">
<img src="img/earth4.png" alt="Registrasi user Earthdata - 4" width="70%" />
<p class="caption">(\#fig:earth4)Registrasi user Earthdata - 4</p>
</div>


4. Centang bagian persetujuan yang ada


<div class="figure" style="text-align: center">
<img src="img/earth5.png" alt="Registrasi user Earthdata - 5" width="70%" />
<p class="caption">(\#fig:earth5)Registrasi user Earthdata - 5</p>
</div>

<div class="figure" style="text-align: center">
<img src="img/earth6.png" alt="Registrasi user Earthdata - 6" width="70%" />
<p class="caption">(\#fig:earth6)Registrasi user Earthdata - 6</p>
</div>


5. Pastikan mencentang pilihan persetujuan dan I'm not a robot dan klik __REGISTER FOR EARTHDATA LOGIN__

<div class="figure" style="text-align: center">
<img src="img/earth7.png" alt="Registrasi user Earthdata - 7" width="70%" />
<p class="caption">(\#fig:earth7)Registrasi user Earthdata - 7</p>
</div>


6. Proses registrasi selesai yang ditandai dengan pesan _'Your Earthdata Login Proffile has been successfully created and automatically activated'_

<div class="figure" style="text-align: center">
<img src="img/earth8.png" alt="Registrasi user Earthdata - 8" width="70%" />
<p class="caption">(\#fig:earth8)Registrasi user Earthdata - 8</p>
</div>



7. Cek email Anda dan klik tautan yang ada di dalam email untuk melakukan konfirmasi

<div class="figure" style="text-align: center">
<img src="img/earth9.png" alt="Cek email dari Earthdata" width="70%" />
<p class="caption">(\#fig:earth9)Cek email dari Earthdata</p>
</div>

<div class="figure" style="text-align: center">
<img src="img/earth10.png" alt="Registrasi user Earthdata telah berhasil" width="70%" />
<p class="caption">(\#fig:earth10)Registrasi user Earthdata telah berhasil</p>
</div>


### Copernicus

1. Registrasi akun Copernicus dapat dilakukan di tautan  https://scihub.copernicus.eu/dhus/. Klik Sign up yang muncul ketika Anda mengklik ikon User di pojok kanan atas.

<div class="figure" style="text-align: center">
<img src="img/esa1.png" alt="Registrasi user Copernicus Scihub" width="70%" />
<p class="caption">(\#fig:esa1)Registrasi user Copernicus Scihub</p>
</div>


2. Isikan informasi yang diminta dan klik __REGISTER__

<div class="figure" style="text-align: center">
<img src="img/esa2.png" alt="Registrasi user Copernicus Scihub - 2" width="70%" />
<p class="caption">(\#fig:esa2)Registrasi user Copernicus Scihub - 2</p>
</div>


3. Proses registrasi berhasil ketika Anda melihat pesan seperti pada gambar.

<div class="figure" style="text-align: center">
<img src="img/esa3.png" alt="Registrasi user Copernicus Scihub- 3" width="70%" />
<p class="caption">(\#fig:esa3)Registrasi user Copernicus Scihub- 3</p>
</div>


4. Buka email Anda dan klik tautan yang ada di dalam pesan kiriman dari SciHub.


<div class="figure" style="text-align: center">
<img src="img/esa4.png" alt="Cek email dari Copernicus Scihub" width="70%" />
<p class="caption">(\#fig:esa4)Cek email dari Copernicus Scihub</p>
</div>


5. Aktivasi akun Copernicus berhasil.

<div class="figure" style="text-align: center">
<img src="img/esa5.png" alt="Registrasi user Copernicus Scihub telah berhasil" width="70%" />
<p class="caption">(\#fig:esa5)Registrasi user Copernicus Scihub telah berhasil</p>
</div>


<!-- You can label chapter and section titles using `{#label}` after them, e.g., we can reference Chapter \@ref(intro). If you do not manually label them, there will be automatic labels anyway, e.g., Chapter \@ref(methods). -->

<!-- Figures and tables with captions will be placed in `figure` and `table` environments, respectively. -->

<!-- ```{r nice-fig, fig.cap='Here is a nice figure!', out.width='80%', fig.asp=.75, fig.align='center'} -->
<!-- par(mar = c(4, 4, .1, .1)) -->
<!-- plot(pressure, type = 'b', pch = 19) -->
<!-- ``` -->

<!-- Reference a figure by its code chunk label with the `fig:` prefix, e.g., see Figure \@ref(fig:nice-fig). Similarly, you can reference tables generated from `knitr::kable()`, e.g., see Table \@ref(tab:nice-tab). -->

<!-- ```{r nice-tab, tidy=FALSE} -->
<!-- knitr::kable( -->
<!--   head(iris, 20), caption = 'Here is a nice table!', -->
<!--   booktabs = TRUE -->
<!-- ) -->
<!-- ``` -->

<!-- You can write citations, too. For example, we are using the **bookdown** package [@R-bookdown] in this sample book, which was built on top of R Markdown and **knitr** [@xie2015]. -->
