# Prinsip dasar penginderaan jauh

OK, di bagian ini saya akan mengkombinasikan antara praktek dan teori. Seperti pesan yang masih saya ingat betul dari Prof. Hasan Z. Abidin, _"There is nothing as practical as a good theory"_. Catatan: pesan ini aslinya dipopulerkan oleh Lewin (1943, 1944, 1945), namun menurut saya masih berlaku hingga saat ini.

Kembali ke data yang telah diunduh menggunakan SCP Plugin di QGIS. Proses yang dijalankan dengan SCP Plugin membuat dua untuk menyimpan data Landsat, (1) LT05_L1TP_122065_19900709_20170129_01_T1_1990-07-09, (2) LT05_L1TP_122065_19900709_20170129_01_T1_1990-07-09_converted. 

<div class="figure" style="text-align: center">
<img src="img/c4_001.png" alt="Struktur folder" width="50%" />
<p class="caption">(\#fig:figc4001)Struktur folder</p>
</div>




Folder pertama menyimpan data yang direkam oleh citra ( _raw data_ ),sedangkan folder kedua berisi berkas (file) yang sudah dilakukan prapengolahan (_Masih ingat kan tadi kita memilih __Pre-process images__ ?_)

Kedua folder memiliki 8 berkas TIF dan 1 berkas teks (untuk folder pertama). Kedelapan berkas TIF terdiri dari hasil perekaman dari tujuh (7) _band_ dan satu (1) file Quality Assurance (QA). Satu berkas teks (\_MTL.txt) adalah berkas metadata. 


<div class="figure" style="text-align: center">
<img src="img/c4_002.png" alt="Raw data citra Landsat 5" width="70%" />
<p class="caption">(\#fig:figc4002)Raw data citra Landsat 5</p>
</div>


<div class="figure" style="text-align: center">
<img src="img/c4_003.png" alt="File citra Landsat 5 yang sudah dilakukan pre-processing" width="70%" />
<p class="caption">(\#fig:figc4003)File citra Landsat 5 yang sudah dilakukan pre-processing</p>
</div>

Penamaan berkas untuk setiap _band_ mengikuti pola tertentu. Sebagai contoh, band 1 memiliki nama berkas LT05_L1TP_122065_19900709_20170129_01_T1_1990-07-09_B1.TIF, yang dapat dijelaskan sebagai berikut :

```
- LT05 : Menunjukkan berkas tersebut adalah berkas data Landsat 5

- L1TP : Level pengolahan, Tier 1 Level 1 Precision and Terrain.  
Tier 1 memiliki kualitas data yang paling tinggi dan cocok digunakan untuk analisis 
time series. Data telah dikalibrasi untuk ragam instrumen 
Landsat dan memiliki tolerasi kesalahan geometrik (RMSE) <= 12 meter.

- 122065 : Nomor Path : 122 dan nomor Row : 065

- 1990709 : Tanggal perekaman

- 20170129 : Tanggal ingestion

- 1990-07-09 : Tanggal perekaman

- B1 : Band 1
```

__Path-Row__ merupakan istilah yang digunakan oleh satelit Landsat untuk akuisisi citra berbasis Worldwide Reference System (WRS). __Path__ mengacu pada salah satu dari 251 trek timur-barat yang dibuat oleh satelit saat mengikuti orbitnya, yang berada 440 hingga 570 mil ke arah Utara dan cenderung ke garis khatulistiwa. __Row__ mengacu pada _side-to-side scan_ di sepanjang jalur orbit, dengan nomor __Row__ mengacu pada garis tengah garis lintang setiap frame. Ada 119 row,  dari 80 derajat Lintang Selatan ke 80 derajat Lintang Utara. __Scene__ adalah serangkaian row lengkap, yang mencakup 24 detik waktu perjalanan satelit, sehingga dalam orbit lengkap, 248 __scene__ diperoleh selama 6196 detik (1,72 jam) untuk Landsat 1. Gambar berikut merupakan contoh cakupan Scene Landsat 8 di Indonesia. Bagian yang diberi tanda kotak merah adalah Path-Row 122-065.

<div class="figure" style="text-align: center">
<img src="img/landsat_pathrow.png" alt="Path-row Landsat di Indonesia" width="70%" />
<p class="caption">(\#fig:figc4004)Path-row Landsat di Indonesia</p>
</div>



Berkas _MTL.txt berisi metadata dari scene Landsat yang diunduh. Isi dari metadata Landsat termasuk waktu perekaman, posisi satelit, konstanta dan lainnya yang diperlukan untuk melakukan koreksi radiometrik. Apabila kita melakukan koreksi radiometrik secara manual, maka kita harus membaca metadata dan menggunakan informasi di dalamnya. Untuk tahapan yang kita lakukan, berkas metadata digunakan oleh SCP Plugin untuk proses koreksi radiometrik.

Adapun untuk folder converted, pola nama berkasnya hampir sama dengan di atas, perbedaannya terletak pada awalan (RT), yang menunjukkan bahwa data sudah dalam format _reflectance_. Apa itu _reflectance_? _Sabar kawan, nanti kita akan belajar tentang itu_.

Supaya otak kita tidak terlalu panas, saya cukupkan dahulu penjelasan mengenai struktur data Landsat. Sekarang kita akan melihat dan bermain-main dengan data citra Landsat yang telah kita unduh. 

_"Are you ready? Let's get it on!"_







## Spectral signature

___Spectral signature___ adalah prinsip #1 dalam memahami konsep inderaja. __Spektral signature__ menampilkan semua variasi reflektansi radiasi spektrum gelombang sebagai fungsi dari panjang gelombang. Gambar di bawah memperlihatkan __spectral signature__ untuk vegetasi. 

<div class="figure" style="text-align: center">
<img src="img/spectral-signatures.png" alt="Pola spektral air dan vegetasi" width="70%" />
<p class="caption">(\#fig:figc4005)Pola spektral air dan vegetasi</p>
</div>



Istilah __spectral signature__ memberikan makna bahwa obyek-obyek di permukaan bumi memiliki karakteristik tersendiri dalam memantulkan gelombang elektromagnetik. Seperti terlihat pada gambar berikut air, rumput kering, vegetasi dan salju memiliki karakteristik yang berbeda.

<div class="figure" style="text-align: center">
<img src="img/spectral-signatures-2.png" alt="Pola spektral air, rumput kering, vegetasi dan salju" width="70%" />
<p class="caption">(\#fig:figc4006)Pola spektral air, rumput kering, vegetasi dan salju</p>
</div>




Dengan data yang sudah diunduh dan bermodalkan QGIS, kita akan belajar lebih lanjut tentang prinsip ini.

Gunakan panel __Browser__ di QGIS, buka folder data. Sebagai contoh, folder data saya ada di /home/firmanhadi/00_qgis. 


<div class="figure" style="text-align: center">
<img src="img/0qgis_001.png" alt="Browser Panel" width="70%" />
<p class="caption">(\#fig:qgis001)Browser Panel</p>
</div>



Di __Panel Layers__, klik __Add Group__ untuk membuat grup layer yang baru, ubah namanya menjadi _rawdata_ dengan klik kanan dan pilih __Rename Group__.

<div class="figure" style="text-align: center">
<img src="img/0qgis_002.png" alt="Add group" width="50%" />
<p class="caption">(\#fig:qgis002)Add group</p>
</div>


Pastikan grup _rawdata_ tersorot dan pilih tujuh (7) band rawa data yang ada di dalam folder LT05_L1TP_122065_19900709_20170129_01_T1_1990-07-09. Setelah terpilih, klik kanan dan pilih __Add selected layers to project__.

<div class="figure" style="text-align: center">
<img src="img/0qgis_003.png" alt="Menampilkan file di Main Display" width="50%" />
<p class="caption">(\#fig:qgis003)Menampilkan file di Main Display</p>
</div>


Band 7 secara otomatis akan terpilih di __Panel Layers__ dan ditampilkan di __Map Display__




Tahapan yang seringkali dilupakan setelah membuka data citra adalah memahami informasi terkait data (metadata). Di QGIS, untuk mengetahui metadata citra, kita dapat klik dua kali nama band di __Panel Layers__. Kita dapat membaca metadata seperti Name, Path, CRS, Extent dan lainnya di tab __Information__. Berhubung sub bagian ini adalah tentang __Spectral Signature__, penjelasan tentang isi dari metadata akan ditulis di sub bagian yang lain.


<div class="figure" style="text-align: center">
<img src="img/0qgis_004.png" alt="Menampilkan metadata" width="50%" />
<p class="caption">(\#fig:qgis004)Menampilkan metadata</p>
</div>


<div class="figure" style="text-align: center">
<img src="img/0qgis_005.png" alt="Metadata file citra" width="50%" />
<p class="caption">(\#fig:qgis005)Metadata file citra</p>
</div>


Selanjutnya, tambahkan Layer OpenStreetMap dengan memilih menu __Web -> OpenLayers Plugin -> OpenStreetMap -> OpenStreetMap__. Fokuskan di wilayah Kota Bandung seperti terlihat pada gambar. 


<div class="figure" style="text-align: center">
<img src="img/0qgis_006.png" alt="OpenStreetMap sebagai basemap" width="50%" />
<p class="caption">(\#fig:qgis006)OpenStreetMap sebagai basemap</p>
</div>



Selanjutnya sembunyikan layer OpenStreetMap sehingga yang ditampilkan di Map Display adalah Band 7. 



<div class="figure" style="text-align: center">
<img src="img/0qgis_007.png" alt="Menon-aktifkan basemap" width="50%" />
<p class="caption">(\#fig:qgis007)Menon-aktifkan basemap</p>
</div>

Nama _band_ di __Panel Layers__ bagi saya terlalu panjang, makan tempat, _ya tidak_? Untuk mengemat ruang tampilan, kita dapat mengubah namanya menjadi lebih singkat seperti Band 7 atau B7. Caranya? Klik kanan pada nama band dan pilih __Rename Layer__. Setelah proses pengubahan nama, kita akan mendapatkan tampilan dengan porsi __Map Display__ yang lebih luas.


<div class="figure" style="text-align: center">
<img src="img/0qgis_008.png" alt="Menampilkan Band 7" width="50%" />
<p class="caption">(\#fig:qgis008)Menampilkan Band 7</p>
</div>


Apa yang dapat Anda lihat dari Band 7? Gelap? Bandingkan dengan gambar selanjutnya, terlihat lebih jelas bukan?

<div class="figure" style="text-align: center">
<img src="img/0qgis_012.png" alt="Menampilkan Band 7 dengan tampilan lebih jelas" width="50%" />
<p class="caption">(\#fig:qgis012)Menampilkan Band 7 dengan tampilan lebih jelas</p>
</div>



Untuk membuat visualisasi citra lebih jelas, yang perlu dilakukan adalah mengaktifkan __Raster Toolbar__, klik menu __View -> Toolbars -> Raster Toolbar__. 

<div class="figure" style="text-align: center">
<img src="img/0qgis_013.png" alt="Mengaktiffkan Raster Toolbal" width="50%" />
<p class="caption">(\#fig:qgis013)Mengaktiffkan Raster Toolbal</p>
</div>




Untuk membuat citra menjadi lebih jelas, klik ikon seperti pada gambar. Ikon ini akan melakukan perentangan nilai sehingga citra menjadi lebih kontras.

<div class="figure" style="text-align: center">
<img src="img/0qgis_014.png" alt="Merentangkan nilai Band 7 sesuai display" width="50%" />
<p class="caption">(\#fig:qgis014)Merentangkan nilai Band 7 sesuai display</p>
</div>



Mengapa citra satelit yang diunduh nampak gelap? Untuk menjawab pertanyaan ini, kita dapat melihat histogram Band 7. Klik dua kali pada nama _band_, pilih __Histogram__. 

<div class="figure" style="text-align: center">
<img src="img/0qgis_015.png" alt="Menampilkan histogram" width="50%" />
<p class="caption">(\#fig:qgis015)Menampilkan histogram</p>
</div>



Histogram memperlihatkan nilai digital dari Band 7 lebih banyak berada di sebelah kiri histogram, di bawah nilai 50. Apa dampaknya? Citra akan terlihat gelap. Sebaliknya, apabila data lebih banyak berada di sebelah kanan histogram, maka citra akan terlihat terang. Citra dengan visualisasi yang kontras dan jelas itu akan dapat dicapai apabila datanya terdistribusi normal. Cara yang telah kita praktekkan itu pada dasarnya meregangkan nilai sehingga data terdistribusi normal, secara visual. 

Setiap band Landsat disimpan dalam berkas terpisah dalam format TIFFF. Untuk melihat profil reflektansi dari data yang kita miliki, _band_ yang ada harus digabungkan menjadi satu berkas dengan fungsi __Merge__ di QGIS. 

Cara melakukan penggabungan _band_ di QGIS adalah sebagai berikut :

1. Klik __Raster -> Miscellaneous -> Merge__.


<div class="figure" style="text-align: center">
<img src="img/0qgis_016.png" alt="Menggabungkan file (merge)" width="60%" />
<p class="caption">(\#fig:qgis016)Menggabungkan file (merge)</p>
</div>


2. Klik tiga titik di bagian kanan __Input Layers__. Pilih B1, B2, B3, B4, B5 dan B7.  Pastikan urutan band mulai dari B1 hingga ke B7, bukan sebaliknya. 

<div class="figure" style="text-align: center">
<img src="img/0qgis_017.png" alt="Mengurutkan band yang akan digabungkan" width="50%" />
<p class="caption">(\#fig:qgis017)Mengurutkan band yang akan digabungkan</p>
</div>


Tips untuk mendapatkan posisi seperti ini adalah dengan menampilkan setiap layer di Map Display dengan B1 di urutan bagian bawah, dan B7 di bagian paling atas.

<div class="figure" style="text-align: center">
<img src="img/0qgis_019.png" alt="Mengurutkan band di Layers Panel" width="50%" />
<p class="caption">(\#fig:qgis019)Mengurutkan band di Layers Panel</p>
</div>


3. Centang bagian __Place each input file into a separate band__

4. Pilih Byte untuk __Output data type__

5. Pilih berkas untuk menyimpan hasil.

6. Pastikan pilihan yang ada sudah diisi sebelum mengklik __Run__.

<div class="figure" style="text-align: center">
<img src="img/0qgis_018.png" alt="Proses merging" width="50%" />
<p class="caption">(\#fig:qgis018)Proses merging</p>
</div>


7. Apabila tidak ada pesan kesalahan, berarti file gabungan telah berhasil dibuat.


<div class="figure" style="text-align: center">
<img src="img/0qgis_020.png" alt="Proses merging telah selesai" width="70%" />
<p class="caption">(\#fig:qgis020)Proses merging telah selesai</p>
</div>
<div class="figure" style="text-align: center">
<img src="img/0qgis_021.png" alt="Citra hasil merging" width="70%" />
<p class="caption">(\#fig:qgis021)Citra hasil merging</p>
</div>


Proses _merging_ sudah selesai. Citranya kali ini terdiri dari banyak _band_. Tapi kok masih terlihat gelap? Apakah kita dapat melakukan cara yang sama untuk memperjelas citra seperti sebelumnya? 

Jawabannya adalah bisa, tapi hasilnya tidak memperlihatkan warna yang sebenarnya. 

<div class="figure" style="text-align: center">
<img src="img/0qgis_022.png" alt="Visualisasi citra hasil merging" width="70%" />
<p class="caption">(\#fig:qgis022)Visualisasi citra hasil merging</p>
</div>


Hal ini terjadi karena kita belum mengatur susunan band dalam format RGB, seperti berikut :

1. Klik dua kali file hasil merge.

2. Klik Symbology

3. Pilih Band 3 untuk __Red band__, Band 2 untuk __Green band__, Band 1 untuk __Blue band__. 

4. Pilih __Stretch to MinMax__ untuk __Contrast Enhancement__.

5. Klik __OK__.

<div class="figure" style="text-align: center">
<img src="img/0qgis_023.png" alt="Simbologi citra" width="70%" />
<p class="caption">(\#fig:qgis023)Simbologi citra</p>
</div>


<div class="figure" style="text-align: center">
<img src="img/0qgis_024.png" alt="Visualisasi citra RGB True Color" width="70%" />
<p class="caption">(\#fig:qgis024)Visualisasi citra RGB True Color</p>
</div>


Selanjutnya, aktifkan plugin __Temporal/Spectral Profile Tool__ dengan memilih menu __Spectral 
Plugins -> Profile Tool -> Temporal/Spectral Profile__ . Untuk mengetahui profil spektral obyek, klik pada obyek yang diinginkan pada Map Display. Sebagai contoh, tiga gambar berikut memperlihatkan perbedaan _spectral signature_ untuk obyek air, vegetasi dan urban (built up).

<div class="figure" style="text-align: center">
<img src="img/0qgis_026.png" alt="Pola spektral air" width="70%" />
<p class="caption">(\#fig:qgis026)Pola spektral air</p>
</div>


<div class="figure" style="text-align: center">
<img src="img/0qgis_027.png" alt="Pola spektral vegetasi" width="70%" />
<p class="caption">(\#fig:qgis027)Pola spektral vegetasi</p>
</div>

<div class="figure" style="text-align: center">
<img src="img/0qgis_028.png" alt="Pola spektral urban" width="70%" />
<p class="caption">(\#fig:qgis028)Pola spektral urban</p>
</div>


Gambar berikut memperlihatkan perbandingan karakteristik _spectral signature_ air, vegetasi dan urban dari tiga titik sampel sebelumnya. Pola _spectral signature_ untuk air memperlihatkan bahwa semakin panjang panjang gelombang. Hmmm, bahasanya rancu ya? Dalam bahasa Inggris, _the longer the wavelength, the lower the reflectance value_. Untuk vegetasi, terlihat ada lonjakan dari Band 3 ke Band 4, sedangkan untuk urban, tidak ada lonjakan nilai reflektansi untuk kedua obyek ini. 
Dari perbedaan pola grafik ketiga obyek, kita dapat menyimpulkan bahwa air, vegetasi dan urban memiliki _spectral signature_ yang berbeda. Artinya, secara teoritis, data yang ada dapat digunakan untuk membuat peta dengan kelas tataguna lahan air, vegetasi dan urban. Lebih jelasnya akan dibahas pada sub bagian klasifikasi.


<div class="figure" style="text-align: center">
<img src="img/0qgis_039.png" alt="Pola spektral air, vegetasi dan urban" width="70%" />
<p class="caption">(\#fig:qgis039)Pola spektral air, vegetasi dan urban</p>
</div>




## Semua adalah angka

Prinsip #2 inderaja yang perlu dipahami adalah __semua adalah angka__. Reflektansi adalah satuan yang digunakan untuk menampilkan rasio jumlah spektrum elektro magnetik (EM) yang dipantulkan oleh obyek terhadap jumlah spektrum EM yang mengenainya. Peristiwa pemantulan gelombang yang merupakan sebuah peristiwa fisika (analog). Mata kita dapat mengindera pantulan cahaya dari obyek dan otak menginterpretasikannya sesuai intensitas. 

Sistem inderaja merekam intensitas pantulan cahaya dengan melakukan transformasi intensitas pantulan setiap spektrum EM ke dalam bentuk angka. Apa yang kita lihat warna putih, abu-abu atau hitam dalam citra satelit, pada dasarnya adalah angka.

Sebagai contoh, gambar berikut memperlihatkan angka 0 direpresentasikan dengan warna hitam, angka 255 dalam warna putih dan warna lain dengan tingkat keabuan yang berbeda, ditampilkan dengan angka antara 0 hingga 255.

<div class="figure" style="text-align: center">
<img src="img/0qgis_041a.png" alt="Visualisasi angka digital dalam citra" width="70%" />
<p class="caption">(\#fig:qgis041a)Visualisasi angka digital dalam citra</p>
</div>


Angka 0 hingga 255 adalah angka yang disimpan dalam komputer dengan tipe data 8 bit. Tipe data ini mampu menyimpan $2^8 = 256$ nilai. Nilai minimum dan maksimum dari tipe data 8 bit, mungkin antara -128 hingga 127 apabila tipenya _signed integer_, atau antara 0 hingga 255 apabila tipenya _unsigned integer_.

Jadi, angka digital dalam inderaja merepresentasikan nilai reflektansi. Dalam tipe data 8 bit, nilai reflektansi 0 disimpan dalam 0, ditampilkan dalam warna hitam. Nilai reflektansi 100 disimpan dalam angka 255, ditampilkan dalam warna hitam.

<div class="figure" style="text-align: center">
<img src="img/0qgis_041.png" alt="Angka Digital" width="70%" />
<p class="caption">(\#fig:fig041)Angka Digital</p>
</div>


Gambar di atas memperlihatkan nilai digital obyek air untuk B1, B2, B3, B4, B5 dan B6, dengan catatan B6 adalah Band 7 dari Landsat 5 TM. B1-B5 dan B7 dari Landsat 5 TM disebut dengan _multi-spectral channel_. 

Penyimpanan informasi reflektansi dalam bentuk nilai digital, memungkinkan mata kita untuk 'membaca' perilaku obyek dalam memantulkan spektrum EM di luar spektrum tampak. 



<!-- dilakukannya analisis kuantitatif seperti _ratioing_, _change detection_, klasifikasi dan lainnya. -->


## Visualisasi RGB



<!-- Sampai di sini, kita belum membahas tentang mengapa citra satelit -->

<!-- Citra satelit memanfaatkan ragam spektrum EM yang memungkinkan kita untuk mendeteksi dan melakukan klasifikasi obyek-obyek itu berdasarkan Prinsip #1 (_spectral signature_). Ragam spektrum yang digunakan berada dalam rentang spektrum dengan panjang gelombang antara .. - ... . -->

<!-- Spektrum EM gelombang tampak (visible), spektrum yang dapat diindera oleh mata manusia berada di rentang .. Pemanfaatan spektrum EM non-tampak (non-visible  -->





## Minimalisasi kesalahan


### Koreksi radiometrik


### Koreksi geometrik

## Klasifikasi


