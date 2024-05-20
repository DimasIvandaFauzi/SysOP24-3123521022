# Tugas 11
* Serial
  * ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/add2a2c9-ae01-4ab9-9ac3-8756c144623b)
  * Tugas pada proses dijalankan satu persatu berurutan dan bergantian, tugas setelah nya bisa dikerjakan apabila tugas sebelumnya selesai, jika tugas sebelumnya belum selesai maka tugas setelah nya tidak dapat dijalankan.
    
* Konkuren
  * ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/712b002d-211c-4d6f-9ef0-1b16d7036c59)
  * Beberapa tugas pada proses yang dapat dijalankan secara bersamaan di waktu yang sama, ketika Tugas0 sedang bekerja, di tengah tengah nya bisa dijalankan Tugas1 dan Tugas lainnya.
    
* Paralel
  * ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/01a65e1e-67fe-4d55-a723-385b20130c0d)
  * Menjalankan beberapa tugas secara bersamaan namun dengan Core CPU yang berbeda.
    
* Konkuren Paralel
  * ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/da58846b-a6e2-4b92-8700-d958f310048d)
  * Tugas dibagi menjadi sub tugas dan tiap sub tugas yang berbeda dapat dikerjakan bersamaan di Core CPU yang berbeda
#
**Catatan**
* Perbedaan Proses dan Thread:
  * Tiap 1 PCB hanya 1 proses
  * Tiap 1 PCB lebih dari 1 thread
  * Proses adalah program yang sedang di eksekusi oleh CPU
  * Thread adalah unit eksekusi terkecil dalam sebuah proses
* Multithreading adalah kemampuan sebuah program untuk menjalankan beberapa thread secara bersamaan.
