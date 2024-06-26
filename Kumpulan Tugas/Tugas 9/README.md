# Tugas 9
**Arsitektur Komputer**
* Arsitektur komputer adalah konsep perencanaan dan struktur pengoperasian dasar dari suatu sistem komputer. Arsitektur komputer ini merupakan rencana cetak-biru dan deskripsi fungsional dari kebutuhan bagian perangkat keras yang didesain (kecepatan proses dan sistem interkoneksinya). Dalam hal ini, implementasi perencanaan dari masing–masing bagian akan lebih difokuskan terutama, mengenai bagaimana CPU akan bekerja, dan mengenai cara pengaksesan data dan alamat dari dan ke memori cache, RAM, ROM, dan lain-lain.
   * ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/8475cfdc-6352-4681-b561-6a57c29b7ce2)
   * ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/f66251d8-9187-485f-be21-362ef5a5bc8f)

**Perbedaan CISC dan RISC**
* CISC (Complex Instruction Set Computing), sebuah arsitektur komputer yang memiliki Komponen Hardware yang sederhana namun memiliki Instruksi Pemrograman yang kompleks. CISC memiliki kemampuan untuk mengeksekusi mode pengalamatan atau operasi multi-langkah dalam satu set instruksi. Perangkat keras Intel disebut sebagai CISC
   * ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/6987d69a-b6b1-4ec5-8745-644ad6c35307)

* RISC (Reduced Instruction Set Computing), sebuah arsitektur komputer yang memiliki komponen Hardware lebih rumit/kompleks namun memiliki Instruksi Pemrograman yang sederhana. Strategi desain CPU berdasarkan pemahaman bahwa set instruksi yang disederhanakan memberikan kinerja yang lebih tinggi bila dikombinasikan dengan arsitektur mikroprosesor yang memiliki kemampuan untuk mengeksekusi instruksi dengan menggunakan beberapa siklus mikroprosesor per instruksi. Perangkat keras Apple adalah RISC.
   * ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/0cb615a2-558c-4cc1-be14-2515eb6466e2)

* ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/b57d5faa-5621-490d-910b-9ef244678599)


**Hubungan Arsitektur CPU dengan Arsitektur OS**
* Arsitektur CPU adalah fondasi dari sistem komputer, maka dari itu Arsitektur CPU menentukan instruksi yang dapat diproses oleh CPU, berapa banyak bit data yang dapat dimanipulasi CPU dalam satu operasi, cara CPU mengakses data dalam memori, jumlah dan fungsi register internal CPU.
* Arsitektur OS dirancang agar kompatibel dengan arsitektur CPU agar dapat memuat dan menjalankan program dengan benar, mengakses dan mengelola memori secara efisien, berkomunikasi dengan perangkat keras yang terhubung ke CPU, menyediakan layanan dasar untuk aplikasi dan pengguna.

**Fork**
* Sebelum menjalankan Fork, login dulu sebagai root dan update repository setelah itu install g++
```
$ su root
$ apt update
$ apt install g++
```
![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/d1210af4-371d-4665-b669-2b84b9d7ad5b)
![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/dadb931e-99b7-4331-90d7-74da74394ebf)

Setelah itu clonning repo : https://github.com/ferryastika/operatingsystem.git
![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/91755d3e-4b0d-4b2e-97e6-b7293aaf72bb)

1. Fork 01
* Masuk kedalam folder yang baru saja di clonning
```
$ cd operatingsystem
```
* Tampilkan isi folder nya
```
$ ls
$ g++ fork01.cpp -o fork01
```
* Jalankan file nya
```
$ ./fork01
```
![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/71680ac8-dd20-4b4a-b86a-00d219f055dc)

2. Fork 02
```
$ g++ fork02.cpp -o fork02
```
* Jalankan file nya
```
$ ./fork02
```
![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/fd34e7f4-7db5-48f4-afaf-7293e581cede)

3. Fork 03
```
$ g++ fork03.cpp -o fork03
```
* Jalankan
```
$ ./fork03
```
![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/b479b1b6-4a15-4412-8f50-ffaae3008c3a)

4. Orphans
* Tampilkan isi folder dan cari file orphan.c
```
$ ls
$ g++ orphan.c -o orphan
```
* Jalankan file nya
```
$ ./orphan
```
![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/64c5b429-d02b-40b9-8781-d264aae3a585)

5. Zombie
* Tampilkan isi folder dan cari file zombie.c
```
$ ls
$ g++ zombie.c -o zombie
```
* Jalankan file nya
```
$ ./zombie
```
![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/1bda81f4-fd69-47dd-85e9-2a191cd08afd)
![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/375e1d26-134c-4df0-a668-1c1b360ef702)

**Producer-Consumen Problem in C**
* Producer-Consumen Problem adalah suatu masalah yang menggambarkan situasi dimana ada produsen yang membuat barang dan konsumen ingin membelinya namun konsumen tidak tau apakah barang tersebut sudah di produksi atau belum. Hal ini terjadi karena kurangnya sinkronisasi. Untuk mengatasi masalah ini, konsep semaphore digunakan. Semaphore adalah variabel yang digunakan untuk mengontrol akses ke sumber daya bersama oleh banyak proses secara bersamaan. Dengan semaphore, produsen tidak akan membuat kue jika penyimpanan sudah penuh, dan konsumen tidak akan mengambil kue jika penyimpanan kosong.
#
