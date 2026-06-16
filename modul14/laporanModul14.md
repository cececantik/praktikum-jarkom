## LAPORAN PRAKTIKUM JARINGAN KOMPUTER MODUL 14 - 802.11 WiFi

# Nama: Grace Roswita Sallu
# NIM: 103072400093

# TUJUAN PRAKTIKUM
Tujuan praktikum Modul 14 adalah untuk menginvestigasi cara kerja jaringan nirkabel IEEE 802.11 (WiFi) menggunakan aplikasi Wireshark. Praktikan diharapkan mampu memahami proses komunikasi pada jaringan WiFi, menganalisis Beacon Frame, mengamati proses transfer data, serta memahami mekanisme Association dan Disassociation antara host dan Access Point.

# LANGKAH PRAKTIKUM
1. Mengunduh file wireshark-traces.zip.
2. Mengekstrak file Wireshark_802_11.pcap.
3. Membuka file trace menggunakan Wireshark.
4. Mengamati Beacon Frame pada jaringan WiFi.
5. Menganalisis transfer data yang terjadi melalui jaringan 802.11.
6. Mengamati proses Association dan Disassociation antara host dan Access Point.
7. Mendokumentasikan hasil pengamatan dalam bentuk screenshot.

# HASIL DAN ANALISIS
![4.1 Membuka File Trace WiFi](../assets/image/modul14/Gambar%204.1.png)
 Dari tampilan awal Wireshark terlihat berbagai frame 802.11 yang berhasil ditangkap selama proses komunikasi jaringan nirkabel berlangsung. Frame-frame tersebut nantinya akan digunakan untuk menganalisis aktivitas Access Point dan host pada jaringan WiFi.

Beacon Frame digunakan oleh Access Point untuk mengumumkan keberadaan jaringan WiFi kepada perangkat di sekitarnya.
![4.2 Analisis Beacon Frame 1](../assets/image/modul14/Gambar%204.2.png)
 Pada tahap ini dilakukan penyaringan paket menggunakan filter Beacon Frame sehingga hanya frame beacon yang ditampilkan. Dengan filter tersebut proses identifikasi Access Point menjadi lebih mudah dilakukan.

![Analisis Beacon Frame 2](../assets/image/modul14/Gambar%204.3.png)
 Berdasarkan hasil pengamatan terhadap detail Beacon Frame, diperoleh berbagai informasi penting seperti alamat MAC Access Point (BSSID), SSID jaringan, channel yang digunakan, serta capability information yang menunjukkan kemampuan jaringan nirkabel tersebut.

Setelah host terhubung dengan Access Point, komunikasi data dapat dilakukan melalui Data Frame 802.11.
![4.3 Analisis Data Transfer](../assets/image/modul14/Gambar%204.4.png)
Pada screenshot di atas terlihat proses transfer data yang membawa komunikasi HTTP menuju server gaia.cs.umass.edu. Data yang dikirimkan melalui jaringan WiFi dibungkus dalam frame Data 802.11 sebelum diteruskan ke lapisan jaringan dan transport. Hal ini menunjukkan bahwa protokol 802.11 berfungsi sebagai media pengiriman paket antar perangkat dalam jaringan nirkabel.

Selain itu dapat diamati bahwa paket-paket HTTP ditransmisikan melalui protokol TCP yang kemudian dibawa oleh frame Data 802.11.

Association merupakan proses yang dilakukan host ketika akan bergabung dengan suatu jaringan WiFi.
![4.4 Analisis Asscociation dan Disassociation 1](../assets/image/modul14/Gambar%204.5.png)
Pada tahap ini dilakukan pencarian frame yang berkaitan dengan proses Authentication dan Association. Frame-frame tersebut digunakan untuk membangun koneksi antara host dan Access Point.

![Analisis Association dan Disassociation 2](../assets/image/modul14/Gambar%204.6.png)
Screenshot di atas menunjukkan Association Request yang dikirim oleh host kepada Access Point. Frame ini berisi permintaan untuk bergabung ke jaringan nirkabel tertentu.

![Analisis Association dan Disassociation 3](../assets/image/modul14/Gambar%204.7.png)
Screenshot di atas menunjukkan Association Response yang dikirim oleh Access Point sebagai balasan terhadap permintaan asosiasi dari host. Response ini menandakan bahwa proses asosiasi berhasil dilakukan sehingga host dapat menggunakan layanan jaringan yang disediakan oleh Access Point.

# KESIMPULAN
Berdasarkan praktikum yang telah dilakukan dapat disimpulkan bahwa:
1. Wireshark dapat digunakan untuk menganalisis komunikasi pada jaringan WiFi berbasis IEEE 802.11.
2. Beacon Frame berfungsi untuk mengumumkan keberadaan Access Point dan menyediakan informasi konfigurasi jaringan kepada perangkat di sekitarnya.
3. Transfer data pada jaringan WiFi dilakukan menggunakan Data Frame yang membawa paket IP, TCP, dan HTTP.
4. Host harus melalui proses Association dengan Access Point sebelum dapat melakukan komunikasi data.
5. Association dilakukan melalui pertukaran Association Request dan Association Response antara host dan Access Point.
6. Analisis frame 802.11 menggunakan Wireshark memberikan pemahaman yang lebih baik mengenai mekanisme kerja jaringan nirkabel.