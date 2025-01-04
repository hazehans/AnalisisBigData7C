# Underrated Chill and Calm Songs on Spotify
Proyek Akhir Mata Kuliah Analisis Big Data yang diampuh oleh Pak Yuda Munarko S.Kom., M.Sc., Sekaligus sebagai portfolio 

Pendahuluan 
1.	Latar Belakang
Di era digital ini, layanan streaming musik seperti Spotify telah menjadi salah satu platform yang paling banyak digunakan oleh berbagai kalangan, termasuk mahsiswa, terlagi untuk menemani aktivitas sehari – hari. Dalam penggunaan Spotify, saya pribadi sering merasa bahwa terkadang musik dengan genre yang terlalu keras atau penuh energi tidak sesuai dengan kondisi saya, terutama sebagai mahasiswa semester akhir yang sering disibukkan dengan berbagai tugas dan pemikiran masa depan. Dalam hal ini, musik dengan suasana yang lebih tenang dan menangkan seperti lagu – lagu bernuansa “chill” dan “calm” menjadi pilihan yang lebih cocok
Namun, masalah yang sering saya hadapi adalah sulitnya menemukan lagu – lagu dengan karakteristik ini di tengah banyaknya pilihan yang ada. Oleh karena itu, saya tertarik untuk mengangkat topik mengenai seleksi dan filter lagu – lagu dengan genre chill dan calm, sehingga dapat memberikan rekomendasi yang lebih baik sesuai dengan kebutuhan dan kondisi pengguna Spotify, terutama yang memiliki selera yang sama dengan saya dan juga bagi mereka yang mencari ketenangan dan relaksasi dalam musik.
2.	Masalah
Untuk menyelesaikan masalah ini, saya menggunakan data sekunder yang nanti saya jelaskan sumbernya dibawah yang diambil dari Spotify, mencakup berbagai lagu dan fitur terkait, seperti popularitas lagu, energi, tempo, dan karakteristik yang lainnya. Data ini kemudian dianalisis untuk mengidentifikasi lagu – lagu yang sesuai dengan kategori “chill” dan “calm” berdasarkan karakteristik tertentu, seperti tingkat energi yang rendah dipadukan dengan tempo yang lebih lambat dan popularitas yang tidak terlalu tinggi. Dengan menggunakan metode analisis yang relevan, saya dapat menyaring lagu – lagu yang cocok dan mengelompokkan mereka dalam kategori yang diinginkan
3.	Teknik analisis
Untuk mencapai tujuan tersebut, saya menggunakakn teknik analisis sederhana eksplorasi data (EDA) yang mencakup visualisasi distribusi fitur – fitur utama seperti ‘danceability’, ‘energy’, ‘tempo’, dan ‘popularity’. Dengan menganalisis distribusi dan korelasi antar fitur tersebut, saya dapat menentukan batasan yagn tepat untuk mengklasifikasikan lagu – lagu yang cocok sebagai kategori chill dan calm. Setelah itu, teknik seleksi data digunakan untuk memilih lagu – lagu yang memenuhi kriteria tersebut.
4.	Manfaat Analisis 
Hasil analisis ini diharapkan dapat memberikan rekomendasi lagu yang lebih tepat kepada  pengguna Spotify yang mencari musik dengan suasana tenang dan menenangkan. Dengan memiliki daftar lagu chill dan calm yang terstruktur, pengguna dapat lebih mudah menemukan musik yang sesuai dengan mood atau kebutuhan mereka tanpa harus menghabiskan waktu lama dalam pencarian. Hal ii akan sangat bermanfaat bagi konsumen yang ingin menikmati pengalaman mendengarkan musik yang lebih relevan dengan kondisi mental mereka, terutama pada saat – saat yang membutuhkan ketenangan atau saat bekerja.
Package yang diperlukan
```
# Import package yang diperlukan
import pandas as pd         # Untuk manipulasi dan analisis data
import numpy as np          # Untuk operasi numerik dan array
import matplotlib.pyplot as plt  # Untuk visualisasi data
import seaborn as sns       # Untuk visualisasi statistik
import scipy.stats as stats  # Untuk analisis statistik
import warnings             # Untuk menghindari peringatan yang tidak relevan
```
Jika pandas tidak diimport:
•	Error: NameError: name 'pd' is not defined
•	Penjelasan: Error ini terjadi ketika mencoba menggunakan pd, tetapi pandas belum diimpor. 
Jika numpy tidak diimport:
•	Error: NameError: name 'np' is not defined
•	Penjelasan: Error ini terjadi Ketika mencoba menggunakan np, tetapi numpy belum diimpor.
Jika matplotlib.pyplot tidak diimpor:
•	Error: ImportError: cannot import name 'pyplot' from 'matplotlib'
•	Penjelasan: Jika tidak mengimpor matplotlib.pyplot, akan mendapatkan error ini saat mencoba menggunakan fungsi seperti plt.plot().
Jika seaborn tidak diimpor:
•	Error: ImportError: cannot import name 'seaborn'
•	Penjelasan: Error ini terjadi ketika mencoba menggunakan seaborn tetapi paket ini belum diimpor.
Jika scipy.stats tidak diimpor:
•	Error: ImportError: cannot import name 'stats' from 'scipy'
•	Penjelasan: Error ini muncul ketika mencoba menggunakan metode statistik dari scipy.stats, tetapi scipy belum diimpor dengan benar.

