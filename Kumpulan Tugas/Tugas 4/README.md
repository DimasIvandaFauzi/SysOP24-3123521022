# Tugas 4
1. Presentasi Langkah Demi Langkah Tentang Siklus CPU (Fetch, Decode, Execute)
- Ini adalah sebuah siklus CPU dan RAM pada PC kita, dan yang perlu dilakukan adalah menghitung. Prosesor/CPU memiliki 3 langkah yaitu Fetch/Mengambil, Decode/Dekode, Execute/Jalankan, dan ketiga proses tersebut hanya akan saling berulang dalam satu lingkaran dan itulah yang sebenarnya terjadi didalam sebuah CPU
  - ![1](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/3ad68089-7b15-4014-9525-85fe29ebdfd9)
  - ![3](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/417eb795-ed35-43ed-a0f8-1a8067eac917)
     
- Setelah itu kita akan memuat sebuah program kedalam RAM (Random Access Memory). RAM juga berguna untuk menyimpan jawaban dan output/keluaran kita
  - ![2](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/0210bb7b-2475-494a-82ea-61308156f876)

- Sebuah instruksi memiliki 2 bagian, bagian pertama berisi instruksi itu sendiri dan bagian kedua berisi alamat Memory nya. Pada setiap detak jam, CPU akan salah satu dari ketiga langkah yaitu Fetch (mengambil instruksi dari alamat memory), decode (menerjemahkan/memecahkan instruksi tersebut), Execute (menjalankan instruksi tersebut) dan ketiga langkah tadi berulang-ulang dalam satu lingkaran. Jadi itu semua akan dihitung dan akan memulai dengan sebuah angka menambahkan satu kedalam nya, lagi dan lagi.
  - ![4](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/a774bb84-ebfc-4c07-8cac-06aa98413d34)

- (detik 1) Fetch/Ambil. Satu detak jam penghitungan program diatur dari 0, dan CPU mengambil instruksi dari alamat 0 yang ada di RAM lalu memasukkan nya kedalam daftar instruksi.
  - ![5](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/a98a24fd-74c5-4004-bf20-f0e5161c9a2b)

- (detik 2) Decode. CPU menerjemahkan instruksi yang diambil tadi, dalam program ini instruksinya adalah Load/Memuat dan alamat nya adalah 6, yang berarti kita akan memuat nilai/isi dari alamat 6 yang ada di RAM ke dalam akumulator.
   - ![6](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/7433835b-aac2-4c9f-a429-3fedaa410f4e)

- (detik 3) Execute/Jalankan. CPU menjalankan instruksi yang sudah diterjemahkan di Decode dan dibutuhkan nilai dari alamat 6 lalu memuatnya ke akumulator, nilai tersebut bernilai 1.
   - ![7](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/70c962e8-2d78-4d37-8203-9015235f1ad0)

- (detik 4) Fetch/Ambil. Alamat dari penghitungan program bertambah menjadi 1 dan CPU mengambil instruksi dari alamat 1 yang ada di RAM.
   - ![8](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/ace25413-2fd7-49eb-95e4-0e864fd72ea0)

- (detik 5) Decode. CPU menerjemahkan instruksi dan kali ini instruksinya adalah Add/Menambah dan alamat nya adalah 7, yang berarti kita akan menambah nilai dari alamat 7 yang ada di RAM ke dalam apa yang sudah ada di akumulator.
   - ![9](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/1bb65767-1d99-4248-a1d7-94bfe7d3bc5d)

- (detik 6) Execute/Jalankan. CPU menjalankan instruksi dan kita tambahkan nilai nya dari alamat 7 ke dalam akumulator. Nilai didalam akumulator berubah menjadi 2.
   - ![10](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/bdc87791-f3e7-4d17-9103-38d4f9b41c23)
   - ![11](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/88fb1b6f-4b71-42bf-b714-7ef10e604eab)

- (detik 7) Fetch/Ambil. Mengambil dari alamat berikutnya yaitu nomor 2.
   - ![12](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/8b571dd7-5652-4325-b5ba-45c5cffe0e31)

- (detik 8) Decode. Menerjemahkan instruksi yang ada pada alamat nomor 2. Instruksinya adalah Store/Menyimpan ke dalam alamat 6.
   - ![13](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/43140bc7-1ba2-4051-8776-7abe9b0fd69c)

- (detik 9) Execute. Menjalankan instruksi alamat nomor 2, instruksi Store/Menyimpan yaitu kita menyimpan nilai 2 yang ada di akumulator tadi ke dalam alamat 6.
   - ![14](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/0118fc0e-6b81-4f15-9586-0f8f7ec7f4a8)

- (detik 10) Fetch/Ambil. Mengambil alamat berikutnya yaitu nomor 3.
   - ![15](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/3a579cff-3a9a-4593-a5ff-d490de399e77)

- (detik 11) Decode. Menerjemahkan instruksinya yaitu Jump 1 atau Lompat kembali ke alamat 1.
   - ![16](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/6200a0ff-b861-4827-9db3-0ce81938a27c)

- (detik 12) Execute/Jalankan. Penghitungan program sekarang kembali ke alamat 1. Kemampuan untuk melompat, mengulang, dan membuat instruksi secara berulang adalah salah satu dasar dari ilmu komputer.
   - ![17](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/cd5d1ca3-f866-40f9-a81d-284c5dc8d212)

- (detik 13) Fetch/Ambil. Mengambil lagi dari alamat 1.
   - ![18](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/786eb4d7-3de4-4316-bfd3-6dc1954d856c)

- (detik 14) Decode. Menerjemahkan instruksi lagi dan instruksi tersebut adalah Add 7 atau Menambah nilai dari alamat 7 kedalam akumulator.
   - ![19](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/12f45c94-c2f4-4746-a7eb-0e628881abd7)

- (detik 15) Execute. Menjalankan instruksi, menambahkan nilai pada alamat 7 yaitu 1 ke dalam akumulator yang tadinya berisi 2 dan menjadi 3 setelah ditambahkan.
   - ![20](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/199bb0af-bb8d-419f-a9e1-d5649e183450)
   - ![21](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/19de3d29-d5f1-418f-8f32-04452c585fe1)

- (detik 16) Fetch/Ambil. Berlanjut mengambil ke alamat 2.
   - ![22](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/f0184ef3-e081-4158-9113-53bde7149b00)

- (detik 17) Decode. Menerjemahkan instruksinya yaitu Menyimpan ke alamat 6.
   - ![23](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/9a7eaa0b-50b3-40c7-bc2b-7cfc971bc60e)

- (detik 18) Execute/Jalankan. Menjalankan instruksi dan menyimpan nilai yang ada di dalam akumulator ke dalam alamat 6.
   - ![24](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/e6c68e11-bd3e-496e-9fa3-d18569414bd5)
   - ![25](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/a8996b2b-32f2-4cb0-a21e-407286a5eb44)

- Semua siklus tadi berjalan pada satu lingkaran berulang dan kita menghitung satu persatu setiap siklus nya. Program tadi dan dengan instruksi yang sederhana ini, tidak memiliki perintah untuk menghentikannya, jadi program tadi hanya akan terus bertambah nilainya sebanyak satu hingga jumlahnya sangat besar dan tidak bisa lagi ditampung oleh Alamat Memory.
#
