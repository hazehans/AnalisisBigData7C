# Underrated Chill and Calm Songs on Spotify
Proyek Akhir Mata Kuliah Analisis Big Data yang diampuh oleh Pak Yuda Munarko S.Kom., M.Sc., Sekaligus sebagai portfolio 

# Pendahuluan 
1.	Latar Belakang
Di era digital ini, layanan streaming musik seperti Spotify telah menjadi salah satu platform yang paling banyak digunakan oleh berbagai kalangan, termasuk mahsiswa, terlagi untuk menemani aktivitas sehari – hari. Dalam penggunaan Spotify, saya pribadi sering merasa bahwa terkadang musik dengan genre yang terlalu keras atau penuh energi tidak sesuai dengan kondisi saya, terutama sebagai mahasiswa semester akhir yang sering disibukkan dengan berbagai tugas dan pemikiran masa depan. Dalam hal ini, musik dengan suasana yang lebih tenang dan menangkan seperti lagu – lagu bernuansa “chill” dan “calm” menjadi pilihan yang lebih cocok
Namun, masalah yang sering saya hadapi adalah sulitnya menemukan lagu – lagu dengan karakteristik ini di tengah banyaknya pilihan yang ada. Oleh karena itu, saya tertarik untuk mengangkat topik mengenai seleksi dan filter lagu – lagu dengan genre chill dan calm, sehingga dapat memberikan rekomendasi yang lebih baik sesuai dengan kebutuhan dan kondisi pengguna Spotify, terutama yang memiliki selera yang sama dengan saya dan juga bagi mereka yang mencari ketenangan dan relaksasi dalam musik.
2.	Masalah
Untuk menyelesaikan masalah ini, saya menggunakan data sekunder yang nanti saya jelaskan sumbernya dibawah yang diambil dari Spotify, mencakup berbagai lagu dan fitur terkait, seperti popularitas lagu, energi, tempo, dan karakteristik yang lainnya. Data ini kemudian dianalisis untuk mengidentifikasi lagu – lagu yang sesuai dengan kategori “chill” dan “calm” berdasarkan karakteristik tertentu, seperti tingkat energi yang rendah dipadukan dengan tempo yang lebih lambat dan popularitas yang tidak terlalu tinggi. Dengan menggunakan metode analisis yang relevan, saya dapat menyaring lagu – lagu yang cocok dan mengelompokkan mereka dalam kategori yang diinginkan
3.	Teknik analisis
Untuk mencapai tujuan tersebut, saya menggunakakn teknik analisis sederhana eksplorasi data (EDA) yang mencakup visualisasi distribusi fitur – fitur utama seperti ‘danceability’, ‘energy’, ‘tempo’, dan ‘popularity’. Dengan menganalisis distribusi dan korelasi antar fitur tersebut, saya dapat menentukan batasan yagn tepat untuk mengklasifikasikan lagu – lagu yang cocok sebagai kategori chill dan calm. Setelah itu, teknik seleksi data digunakan untuk memilih lagu – lagu yang memenuhi kriteria tersebut.
4.	Manfaat Analisis 
Hasil analisis ini diharapkan dapat memberikan rekomendasi lagu yang lebih tepat kepada  pengguna Spotify yang mencari musik dengan suasana tenang dan menenangkan. Dengan memiliki daftar lagu chill dan calm yang terstruktur, pengguna dapat lebih mudah menemukan musik yang sesuai dengan mood atau kebutuhan mereka tanpa harus menghabiskan waktu lama dalam pencarian. Hal ii akan sangat bermanfaat bagi konsumen yang ingin menikmati pengalaman mendengarkan musik yang lebih relevan dengan kondisi mental mereka, terutama pada saat – saat yang membutuhkan ketenangan atau saat bekerja.

# Package yang diperlukan
```
# Import package yang diperlukan
import pandas as pd         # Untuk manipulasi dan analisis data
import numpy as np          # Untuk operasi numerik dan array
import matplotlib.pyplot as plt  # Untuk visualisasi data
import seaborn as sns       # Untuk visualisasi statistik
import scipy.stats as stats  # Untuk analisis statistik
import warnings             # Untuk menghindari peringatan yang tidak relevan
```
1. Jika pandas tidak diimport:
   - Error: NameError: name `pd` is not defined
   - Penjelasan: Error ini terjadi ketika mencoba menggunakan pd, tetapi pandas belum diimpor. 
2. Jika numpy tidak diimport:
   - Error: NameError: name `np` is not defined
   - Penjelasan: Error ini terjadi Ketika mencoba menggunakan np, tetapi numpy belum diimpor.
3. Jika matplotlib.pyplot tidak diimport:
   - Error: ImportError: cannot import name `pyplot` from `matplotlib`
   - Penjelasan: Jika tidak mengimpor matplotlib.pyplot, akan mendapatkan error ini saat mencoba menggunakan fungsi seperti plt.plot().
4. Jika seaborn tidak diimpor:
   - Error: ImportError: cannot import name `seaborn`
   - Penjelasan: Error ini terjadi ketika mencoba menggunakan seaborn tetapi paket ini belum diimpor.
5. Jika scipy.stats tidak diimpor:
   - Error: ImportError: cannot import name `stats` from `scipy`
   - Penjelasan: Error ini muncul ketika mencoba menggunakan metode statistik dari scipy.stats, tetapi scipy belum diimpor dengan benar.

# Data Preparation
1. Sumber Data :
   - Data merupakan data sekunder yang saya peroleh dari akun github `rfordatascience`
   - [Download Disini](https://www.dropbox.com/sh/qj0ueimxot3ltbf/AACzMOHv7sZCJsj3ErjtOG7ya?dl=1)
   - [Penjelasan](https://github.com/rfordatascience/tidytuesday/blob/master/data/2020/2020-01-21/readme.md)
2. Penjelasan data
   - Data yang digunakan diupload pada 2 bulan yang lalu (sekitar November 2024) berjumlah 32.834 dengan jumlah total 22 fitur, data yang diberikan tidak memiliki satupun duplikasi dan memiliki beberapa missing value
3. Langkah import dan cleaning
   - Import saya lakukan dengan mendownload dulu data terkait dan menguploadnya ke dalam drive saya untuk akses yang lebih mudah
   - Setelah import dilakukan beberapa cleaning saya lakukan dibawah ini
   - Saya crosscheck informasi dataset yang digunakan beserta statistik deskriptifnya
   - Setelah itu, saya mengkonversi beberapa kolom, seperti kolom `track_album_release_date` ke datetime dan `duration_ms` ke second yang awalnya milisecond dengan menyimpannya ke kolom baru `duration_sec`
   - Kemudian saya drop kolom `duration_ms`
   - Melakukan checking missing value dan menghapus setiap missing valuenya dari dataframe yang saya gunakan
   - Untuk analisis lebih lanjut, saya juga menggabungkan fitur `playlist_genre` dan `playlist_sub_genre` dengan membuat fitur baru `playlist_full_genre` dan menghapus kedua fitur sebelumnya
   - Saya juga membuat fitur baru `album_age` yang berisikan umur albumnya, berdasarkan hari ini (4 Januari 2025) dengan satuan float tahun dan tidak lupa drop fitur `track_album_release_date` 
   ![image](https://github.com/user-attachments/assets/31808022-01eb-4e05-95b3-11a3c5e16e99)
   - Berdasarkan data setelah cleaning yang saya lakukan, yang menjadi fokus saya untuk analisis ini adalah dalam fitur `danceability`, `energy`, `tempo`, dan `track_popularity`, akan tetapi, masih menggunakan fitur - fitur lain seperti yang ada di gambar untuk penjelasan lebih lanjut
4. Eksplorasi data
   - Beberapa penggabungan fitur sudah saya lakukan diatas dan beberapa hal menarik dapat saya temukan seperti berikut 

