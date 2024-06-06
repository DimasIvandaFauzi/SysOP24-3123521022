# Tugas 12
* Producer-Consumer Problem (Bakery Problem)
  * ![WhatsApp Image 2024-05-14 at 09 02 20_60de8942](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/88c7c8cb-c2d3-47f2-bbda-3b0c7e2db435)
  * Producer-Consumer Problem, atau Bounded Buffer Problem, adalah masalah klasik dalam pemrograman konkuren yang melibatkan dua proses, yaitu produser (producer) dan konsumen (consumer), yang berbagi sumber daya bersama berupa buffer terbatas (bounded buffer). Tujuannya adalah agar produser tidak mengisi buffer ketika sudah penuh dan konsumen tidak mengosongkan buffer ketika kosong. Koordinasi antara produser dan konsumen sangat penting untuk menghindari kondisi di mana kedua proses mencoba mengakses buffer secara bersamaan tanpa sinkronisasi yang tepat.
  * ![WhatsApp Image 2024-05-14 at 09 42 47_416c5a60](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/b3001211-aa2e-46ca-bc3a-cb5eef160211)
  * Race condition terjadi ketika dua atau lebih proses (atau thread) mengakses sumber daya bersama secara bersamaan dan hasil dari akses tersebut bergantung pada urutan eksekusi mereka.

* Dining Problem
  * ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/d9f257da-68c4-4952-800a-da9419a253a4)
  * Dining Philosophers Problem adalah masalah klasik dalam ilmu komputer yang memperagakan tantangan dalam sinkronisasi dan alokasi sumber daya bersama dalam sistem paralel dan terdistribusi.
  * Deadlock: Situasi di mana setiap filsuf mengambil garpu di sebelah kanannya secara bersamaan, dan kemudian menunggu garpu di sebelah kirinya yang tidak pernah tersedia karena dipegang oleh filsuf lainnya. Ini menyebabkan semua filsuf terjebak dalam kondisi menunggu tanpa akhir.
  * Starvation: Salah satu atau lebih filsuf mungkin tidak pernah mendapatkan kedua garpu dan, oleh karena itu, tidak pernah bisa makan, meskipun garpu-garpu tidak dalam keadaan deadlock.
  * Concurrency: Mengelola akses filsuf ke garpu secara bersamaan tanpa menyebabkan konflik atau kesalahan.

* Reader-Writer Problem
  * ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/4c5e128e-b469-4b0f-9aea-73f4b517e3d4)
  *  Readers-Writers Problem, masalah ini berkaitan dengan bagaimana mengatur akses ke sumber daya bersama (dalam hal ini, sebuah database) oleh dua jenis proses yang berbeda: pembaca (readers) dan penulis (writers).
  *  Readers (Pembaca): Pembaca dapat mengakses database secara bersamaan tanpa mengganggu satu sama lain karena mereka hanya membaca data dan tidak mengubahnya.
  *  Writers (Penulis): Penulis harus memiliki akses eksklusif ke database saat mereka menulis untuk mencegah inkonsistensi data.
  *  Bagian kiri : Saat pembaca sedang mengakses database, beberapa pembaca dapat mengakses database secara bersamaan. Penulis tidak dapat mengakses database selama ada pembaca yang sedang mengaksesnya. Penulis tidak dapat masuk ke Database karena ada Pembaca yang meng-akses nya.
  *  Bagian kanan : Saat penulis sedang mengakses database, tidak ada pembaca atau penulis lain yang dapat mengakses database. Hal ini untuk mencegah konflik dan memastikan konsistensi data selama proses penulisan.
