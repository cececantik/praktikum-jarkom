## LAPORAN PRAKTIKUM MODUL 12

Nama: Grace Roswita Sallu
NIM: 103072400093

# Tujuan Praktikum
1. Mahasiswa dapat memahami cara kerja protokol ICMP
2. Mahasiswa dapat menganalisis proses ping menggunakan wireshark
3. Mahasiswa dapat memahami proses tracert/tracerout pada jaringan

# Pengujian Ping pada CMD
Pada tahap awal dilakukan pengujian konektivitas jaringan mengguhnakan perintah ping -n 10 www.ust.hk
![Hasil ping pada cmd](../assets/image/modul12/cmd%20ping.png)
Hasil menunjukkan bahwa host tujuan berhasil dijangkau karena seluruh paket mendapatkan balasan.
Namun terdapat beberapa delay yang cukup besar seperti:
- 2578 ms
- 1044 ms
- 1001 ms
Hal tersebut dapat disebabkan oleh: Koneksi internet tidak stabil, jarak server yang cukup jauh, kepadatan lalu lintas jaringan.
Walaupun demikian, karena packet loss = 0%, maka koneksi masih tergolong berhasil.

# Analisis Paket ICMP Ping di Wireshark
Setelah melakukan ping, paket ICMP diamati menggunakan wireshark dengan filter icmp
![Paket ICMP Ping](../assets/image/modul12/icmp%20ping2.png)
creenshot ini menunjukkan bahwa:
- Paket ping dikirim dengan berbagai nilai TTL.
- Router memberikan respons ketika TTL habis.
- Beberapa router menolak paket sehingga muncul Destination Unreachable.
Hal tersebut sangat sesuai dengan konsep kerja traceroute.

# Pengujian Tracert pada CMD
Pengujian berikutnya dilakukan menggunakna perinta tracert www.inria.fr
![Hasil Tracert pada CMD](../assets/image/modul12/cmd%20tracert.png)
Pesan Request timed out tidak selalu berarti jaringan gagal.
Hal tersebut dapat terjadi karena:
- Router tidak mengizinkan ICMP reply.
- Firewall memblokir paket.
- Router mengabaikan traceroute.
Namun karena traceroute berhasil mencapai tujuan akhir, maka koneksi masih berhasil.

# Analisis ICMP pada Tracert
![Paket ICMP Tracert](../assets/image/modul12/icmp%20tracert.png)
Pada proses traceroute:
- Paket dikirim dengan TTL kecil.
- Router pertama mengurangi TTL.
- Ketika TTL habis, router mengirim ICMP Time Exceeded.
- Dengan cara ini traceroute dapat mengetahui jalur routing.
Destination Unreachable muncul ketika router tertentu tidak dapat meneruskan paket.

# Kesimpulan 
Berdasarkan praktikum yang telah dilakukan dapat disimpulkan bahwa:
- ICMP digunakan untuk komunikasi kontrol dan diagnosa jaringan.
- Ping digunakan untuk menguji konektivitas jaringan
- Tracert digunakan untuk mengetahui jalur routing paket.
- Wireshark dapat digunakan untuk menganalisis paket ICMP secara detail.
- Paket ICMP yang berhasil diamati meliputi Echo Request, Echo Reply, Time Exceeded, dan Destination Unreachable.