## LAPORAN PRAKTIKUM JARINGAN KOMPUTER MODUL 13 - ETHERNET AND ARP

## Nama: Grace Roswita Sallu
## NIM: 103072400093

## TUJUAN PRAKTIKUM
1. Memahami struktur dan fungsi frame Ethernet.
2. Mengamati proses komunikasi data pada lapisan Data Link menggunakan Ethernet.
3. Memahami cara kerja Address Resolution Protocol (ARP).
4. Mengamati proses pemetaan alamat IP ke alamat MAC menggunakan ARP melalui Wireshark.

## LANGKAH PERCOBAAN
# A. Menangkap dan Menganalisis Frame Ethernet
1. Menjalankan aplikasi Wireshark.
2. Memulai proses packet capture pada interface yang digunakan.
3. Membuka browser dan mengakses halaman:
http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file3.html
4. Menghentikan proses capture setelah halaman berhasil dimuat.
5. Menggunakan filter HTTP pada Wireshark.
6. Memilih paket HTTP GET dan mengamati informasi Ethernet Frame yang terdapat pada paket tersebut.
   
# Bukti Percobaan
![Gambar 1. Capture paket saat mengakses halaman HTTP](../assets/image/modul13/Gambar%2013.1%20Capture%20HTTP%20saat%20Mengakses%20HTTP-wireshark-file3.png)
![Gambar 2. Hasil filter HTTP pada wireshark](../assets/image/modul13/Gambar%2013.2%20Hasil%20Filter%20HTTP%20pada%20Wireshark.png)
![Gambar 3. Detail Ethernet Frame pada paket HTTP GET](../assets/image/modul13/Gambar%2013.3%20Detail%20Ethernet%20Frame%20pada%20Paket%20HTTP%20GET.png)

# B. Mengamati ARP Cache
1. Membuka Command Prompt.
2. Menjalankan perintah: arp -a
3. Mengamati isi ARP Cache yang tersimpan pada komputer
4. Menghapus cache menggunakan perintah: arp -d *
5. Menjalankan kembali perintah: arp -a
6. untuk memastikan cache telah diperbarui.

# Bukti Percobaan
![Gambar 4. Hasil perintah ARP cache](../assets/image/modul13/Gambar%2013.4%20Hasil%20Pengamatan%20dan%20Penghapusan%20ARP%20Cache.png)
# C. Mengamati Proses ARP
1. Menjalankan kembali packet capture pada Wireshark.
2. Menggunakan filter: arp
3. Menghasilkan lalu lintas jaringan dengan mengakses alamat lain dalam jaringan.
4. Mengamati paket ARP Request dan ARP Reply yang muncul
5. Menganalisis informasi Source MAC, Destination MAC, Source IP, dan Target IP.

# Bukti Percobaan
![Gambar 5. Paket ARP yang tertangkap pada wireshark](../assets/image/modul13/Gambar%2013.5%20Paket%20ARP%20Request%20yang%20Tertangkap%20pada%20Wireshark.png)
![Gambar 6. Detail paket ARP Request](../assets/image/modul13/Gambar%2013.6%20Detail%20Informasi%20Paket%20ARP%20Request.png)
![Gambar 7. Detail paket ARP Replay](../assets/image/modul13/Gambar%2013.7%20Detail%20Informasi%20Paket%20ARP%20Replay.png)

## KESIMPULAN
1. Ethernet merupakan protokol pada lapisan Data Link yang menggunakan MAC Address sebagai identitas perangkat dalam proses komunikasi jaringan lokal.
2. Frame Ethernet terdiri dari Destination MAC Address, Source MAC Address, EtherType, dan Payload yang berfungsi untuk mengirimkan data antar perangkat dalam jaringan.
3. Address Resolution Protocol (ARP) digunakan untuk menerjemahkan alamat IP menjadi alamat MAC sehingga perangkat dapat berkomunikasi pada jaringan lokal.
4. Proses ARP diawali dengan pengiriman ARP Request secara broadcast untuk mencari alamat MAC dari suatu alamat IP tertentu.
5. Perangkat yang memiliki alamat IP tujuan akan merespons dengan ARP Reply yang berisi informasi alamat MAC miliknya.
6. Hasil pengamatan menggunakan Wireshark menunjukkan bahwa proses pemetaan alamat IP ke alamat MAC berlangsung melalui pertukaran paket ARP Request dan ARP Reply
7. Wireshark dapat digunakan sebagai alat analisis jaringan untuk mengamati struktur frame Ethernet serta mekanisme kerja ARP secara detail.