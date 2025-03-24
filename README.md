# NAMA : MOH. YUSRIL
# NIM : 09011382429124
# KELAS : SKU2B

# 1. Jelaskan Struktur Antar Hubungan dan Beri Contohnya? 
**Struktur antar hubungan merupakan** pola atau sistem yang menggambarkan bagaimana elemen-elemen dalam suatu organisasi, kelompok, atau sistem sosial berinteraksi dan berhubungan satu sama lain. Struktur ini menunjukkan bagaimana kekuasaan, komunikasi, dan koordinasi terjadi di antara berbagai pihak.
## Jenis-Jenis Struktur Antar Hubungan
## 1. Struktur Hierarkis (Vertikal)
Struktur ini berbentuk piramid dengan kekuasaan terkonsentrasi di puncak dan mengalir ke bawah. Komunikasi formal biasanya mengikuti jalur vertikal.
Contoh: Perusahaan tradisional dengan CEO di puncak, diikuti oleh direktur, manajer, supervisor, dan karyawan. Keputusan strategis dibuat di level atas dan diimplementasikan oleh level bawah.
## 2. Struktur Jaringan (Network)
Struktur yang lebih fleksibel di mana anggota terhubung satu sama lain tanpa hierarki yang kaku. Komunikasi mengalir ke segala arah.
Contoh: Komunitas peneliti yang berkolaborasi dalam proyek riset. Mereka berbagi pengetahuan dan sumber daya tanpa struktur komando yang ketat, dengan hubungan yang didasarkan pada keahlian dan kontribusi.
## 3. Struktur Matriks
Kombinasi dari struktur fungsional dan proyek, di mana anggota melapor kepada dua atau lebih pemimpin.
Contoh: Perusahaan teknologi dengan departemen fungsional (engineering, desain, marketing) yang juga dibagi berdasarkan proyek produk. Seorang engineer bisa melapor ke manajer engineering dan juga ke pemimpin proyek tertentu.
## 4. Struktur Horizontal
Struktur dengan sedikit tingkatan hierarki, menekankan pada kolaborasi dan partisipasi.
Contoh: Startup kecil di mana semua karyawan bekerja secara langsung dengan pendiri, dengan pembagian wewenang yang minimal dan pengambilan keputusan yang lebih kolektif.
Implikasi Struktur Antar Hubungan
Pemilihan struktur antar hubungan berdampak signifikan pada:

## Kecepatan pengambilan keputusan 
- Struktur hierarkis cenderung lebih lambat, sementara struktur jaringan bisa lebih responsif.
Inovasi
- Struktur yang lebih datar dan terbuka sering mendorong kreativitas dan ide-ide baru.
Ketahanan organisasi
- Struktur jaringan biasanya lebih tahan terhadap perubahan eksternal karena fleksibilitasnya.
Efisiensi komunikasi
- Jalur komunikasi lebih panjang dalam struktur hierarkis, sementara lebih langsung dalam struktur horizontal.

# 2. Bila terlalu banyak modul atau perangkat dihubungkan pada bus maka akan terjadi penurunan kinerja, sebutkan penyebabnya?
## Penurunan Kinerja Bus Akibat Kelebihan Modul
Ketika terlalu banyak modul atau perangkat dihubungkan pada sistem bus, penurunan kinerja yang signifikan memang tak terhindarkan. Fenomena ini bukan sekadar masalah teoretis, tetapi batasan fisik dan elektris yang nyata.
# Penyebab Utama
## 1. Kapasitas Elektris Terbatas
Setiap perangkat yang terhubung ke bus menambahkan kapasitansi parasitik. Akumulasi kapasitansi ini memperlambat waktu naik/turun sinyal, yang secara langsung menurunkan kecepatan maksimum operasi bus. Pada titik tertentu, sinyal bahkan bisa terdistorsi hingga tak dapat dikenali.
## 2. Berbagi Bandwidth yang Terbatas
Bus pada dasarnya adalah jalur komunikasi bersama dengan bandwidth tetap. Semakin banyak perangkat yang menggunakannya, semakin terfragmentasi bandwidth tersebut. Seperti jalan raya yang semakin sesak, penambahan "kendaraan" (data) menyebabkan "kemacetan" (latency).
## 3. Konflik Arbitrasi
Sistem bus memerlukan mekanisme arbitrasi untuk menentukan perangkat mana yang dapat mengakses bus pada waktu tertentu. Dengan bertambahnya jumlah perangkat, kompleksitas dan overhead arbitrasi meningkat secara dramatis. Waktu yang dihabiskan untuk arbitrasi bisa melebihi waktu transfer data aktual.
## 4. Degradasi Integritas Sinyal
Setiap sambungan ke bus menambahkan titik refleksi sinyal potensial. Refleksi ini menciptakan noise dan interferensi yang semakin parah dengan bertambahnya jumlah perangkat. Pada kasus ekstrem, sinyal menjadi tidak dapat diandalkan.
## 5. Peningkatan Beban Daya
Setiap perangkat mengkonsumsi daya dari bus. Pada titik tertentu, beban kolektif bisa melebihi kapasitas catu daya bus, menyebabkan penurunan tegangan dan destabilisasi seluruh sistem.
## 6. Masalah Impedansi
Impedansi karakteristik bus berubah dengan setiap perangkat yang ditambahkan. Ketidakcocokan impedansi ini menghasilkan pantulan sinyal dan degradasi transmisi data.
## 7. Keterbatasan Fan-out Logika
Komponen penggerak bus (driver) memiliki batas fan-out—jumlah maksimum input yang dapat digerakkan oleh satu output. Melampaui batas ini mengganggu kemampuan untuk mempertahankan level logika yang valid.

# 3. Umumnya perangkat berprioritas paling rendah memiliki waktu tunggu rata-rata yang paling singkat. Dengan dasar ini biasanya CPU diberi perioritas tertinggi pada SBI. Sebutkan alasan perangkat berprioritas 16 memiliki waktu tunggu rata-rata paling rendah? Dibawah kondisi seperti apa keadaan diatas tidak berlaku?

## Alasan Perangkat Prioritas 16 (Terendah) Memiliki Waktu Tunggu Rata-rata Rendah

- Efek Statistik Menyesatkan
Waktu tunggu "rata-rata" adalah metrik yang mengaburkan realitas. Perangkat prioritas rendah memiliki distribusi waktu tunggu bimodal ekstrem: ketika sistem tidak sibuk, akses langsung (waktu tunggu nol); ketika sibuk, waktu tunggu sangat panjang. Rata-rata hanya menangkap setengah cerita.
- Mekanisme Kompensasi Tersembunyi
Banyak sistem bus menerapkan mekanisme anti-starvation yang tidak didokumentasikan dengan baik, seperti pemaksaan akses periodik atau peningkatan prioritas dinamis setelah penundaan tertentu, yang secara artifisial meningkatkan statistik perangkat prioritas rendah.
- Perbedaan Fundamental Perilaku Akses
CPU (prioritas tinggi) melakukan request kecil tapi sangat sering. Perangkat prioritas rendah melakukan request besar namun jarang. Ketika mendapat akses, perangkat prioritas rendah memaksimalkannya dengan transfer data besar sekaligus, meningkatkan efisiensi penggunaan bus.
- Overhead Arbitrasi yang Diabaikan
Request bus yang diajukan kemudian ditolak menghasilkan overhead. Perangkat prioritas rendah "belajar" untuk tidak meminta akses ketika sistem sibuk, secara tidak langsung mengurangi kompetisi dan overhead arbitrasi yang menguntungkan seluruh sistem.

## Kondisi di Mana Fenomena Ini Tidak Berlaku

- Sistem Dengan Beban Ekstrem
Pada utilisasi bus mendekati 100%, perangkat prioritas rendah mengalami starvation hampir permanen, dengan waktu tunggu mendekati tak terhingga—mematahkan statistik "rata-rata rendah".
- Skema Preemptive
Dalam sistem yang memungkinkan pemutusan transfer bus yang sedang berlangsung (preemption), waktu tunggu berbanding langsung dengan prioritas, menghilangkan anomali statistik.
- Ketika Transfer Time > Waiting Time
Jika waktu transfer data sangat panjang dibanding waktu tunggu (seperti dalam DMA transfer besar), maka prioritas rendah sebenarnya menghasilkan throughput total lebih buruk meskipun waktu tunggu rata-rata mungkin tampak lebih baik.
- Skenario Mixed-Criticality
Dalam sistem dengan persyaratan waktu-nyata beragam, perangkat prioritas rendah dengan deadline dekat secara teoritis harus diprioritaskan di atas perangkat prioritas tinggi dengan deadline jauh—sesuatu yang diabaikan skema prioritas statis.
- Sistem dengan Pola Akses Tidak Terduga
Pemodelan waktu tunggu mengasumsikan pola akses bus yang dapat diprediksi. Ketika perangkat berperilaku di luar model (seperti burst traffic tiba-tiba), hubungan prioritas-waktu tunggu bisa sepenuhnya terbalik.

**Prioritas CPU yang tinggi pada SBI adalah warisan arsitektur lama ketika CPU adalah "raja" sistem. Dengan kemunculan DMA, pengontrol periferal cerdas, dan sistem multi-core, paradigma ini semakin tidak relevan namun terus dipertahankan sebagai dogma desain yang jarang dipertanyakan.**
