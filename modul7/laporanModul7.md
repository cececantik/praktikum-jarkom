## LAPORAN PRAKTIKUM JARINGAN KOMPUTER MODUL 7 SOCKET PROGRAMMING

Nama: Grace Roswita Sallu
NIM: 103072400093

## Tujuan Praktikum

Berdasarkan modul, tujuan praktikum ini adalah untuk membuat mahasiswa mampu membuat program berbasis socket UDP, dan mampu membuat program berbasis socket TCP

## Langkah Percobaan

# a. Menjalankan UDP Server

\*\*\*\* [Codingan UDP server](UDPServer.py)

1. Membuat sockeT UDP dengan SOCK_DGRAM
2. Melakukan binding ke port tertentu
3. Menunggu data dari client
4. Mengubah pesan menjadi huruf kapital
5. Mengirim kembali ke client

# b. Menjalankan UDP Client

\*\*\*\* [Codingan UDP Client](UDPClient.py)

1. Membuat socket UDP
2. Input pesan dari user
3. Mengirim pesan ke server menggunakan sendto()
4. Menerima balasan dari server menggunakan recvfrom()
5. Menampilkan hasil

Pada UDP, client harus menyertakan alamat server saat mengirim data

# c. Menjalankan TCP Server

\*\*\*\* [Codingan TCP Server](TCPServer.py)

1. Membuat socket dengan SOCK_STREAM
2. Binding ke port
3. Listen koneksi dari client
4. Accept koneksi (membuat socker baru khusus client)
5. Menerima data
6. Mengubah data menjadi huruf kapital
7. Mengirim kembali ke client

# d. Menjalankan TCP Client

\*\*\*\* [Codingan TCP Client](TCPClient.py)

1. Membuat socket TCP
2. Melakukan koneksi ke server dengan connect()
3. Input data dari user
4. Mengirim data menggunakan send()
5. Menerima balasan menggunakan recv()
6. Menutup koneksi
   Pada TCP, koneksi harus dibuat terlebih dahulu sebelum pengiriman data

## Lampiran Hasil Percobaan

# UDP

1. Client mengirim pesan ke server
2. Server menerima dan mengubah menjadi huruf kapital
3. Client menerima kembali pesan

![Output UDP kiri server, kanan client](../assets/image/modul7/output%20UDP.png)

# TCP

1. Client berhasil terhubung ke server
2. Terjadi proses komunikasi dua arah
3. Data berhasil dikirim dan diterima dengan benar

![Output TCP kiri sever, kanan client](../assets/image/modul7/output%20TCP.png)

## Hasil Analisis

1. Pada UDP, komunikasi lebih cepat karena tidak ada proses koneksi, tetapi tidal reliabel
2. Pada TCP, komunikasi lebih aman dan terjamin karena menggunakan koneksi dan mekanisme kontrol
3. TCP menggunakan three-way handshake untuk memastikan koneksi antara client dan server
4. UDP lebih sederhana karena tidak perlu membuat koneksi terlebih dahulu

## Kesimpulan

Socket programming digunakan untuk membangun komunikasi client-server dalam jaringan. Melalui dari praktikum ini dapat disimpulkan UDP bersifat cepat namun tidak menjamin keandalan data dan TCP lebih kompleks tetapi menjamin pengiriman data secara akurat dan berurutan. Sehingga perbedaan utama UDP dan TCP terletak pada koneksi dan keandalannya
