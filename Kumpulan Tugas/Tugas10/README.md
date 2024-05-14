# Tugas 10
* Berikan tiga contoh pemrograman yang menyediakan multithreading kinerja yang lebih baik daripada solusi single-threaded.
  * Server Web yang melayani setiap permintaan dalam thread terpisah.
  * Aplikasi paralel seperti perkalian matriks dimana bagian-bagian matriks yang berbeda dapat dikerjakan secara paralel.
  * Program GUI interaktif seperti debugger tempat thread berada digunakan untuk memantau input pengguna, thread lain mewakili proses aplikasi yang sedang berjalan, dan thread ketiga memantau kinerja.
    
* Apa dua perbedaan antara user-level threads dan kernel-level threads? Dalam kondisi apa satu jenis lebih baik dibandingkan jenis lainnya?
  * Thread tingkat pengguna tidak diketahui oleh kernel, sedangkan kernel mengetahui thread kernel.
  * Thread kernel tidak perlu dikaitkan dengan suatu proses sedangkan setiap thread pengguna selalu merupakan bagian dari suatu proses. Thread kernel umumnya lebih mahal untuk dipelihara dibandingkan dengan thread pengguna karena mereka harus diwakili dengan struktur data kernel.
    
* Jelaskan tindakan yang diambil oleh kernel untuk beralih konteks antar kernel-level threads.
  * Context Switching antara thread kernel biasanya memerlukan penyimpanan nilai dari register CPU thread yang sedang diganti dan pemulihan register CPU dari thread baru yang dijadwalkan.
    
* Sumber daya apa yang digunakan saat thread dibuat? Apa perbedaannya? dari yang digunakan ketika suatu proses dibuat?
  * Karena thread lebih kecil daripada proses, pembuatan thread biasanya menggunakan lebih sedikit sumber daya dibandingkan dengan pembuatan proses. Membuat proses memerlukan alokasi process control block (PCB), yang merupakan struktur data yang cukup besar. PCB mencakup peta memori, daftar file yang terbuka, dan variabel lingkungan. Alokasi dan pengelolaan peta memori biasanya merupakan aktivitas yang paling memakan waktu. Membuat thread pengguna atau kernel melibatkan alokasi struktur data kecil untuk menyimpan set register, stack, dan prioritas.
    
* Asumsikan bahwa sistem operasi memetakan thread tingkat pengguna ke kernel menggunakan model banyak ke banyak dan pemetaan dilakukan secara menyeluruh LWP. Selain itu, sistem ini memungkinkan pengembang untuk membuat secara real-time thread untuk digunakan dalam sistem real-time. Apakah perlu untuk mengikat secara real-time utas ke LWP? Jelaskan.
  * Ya. Penentuan waktu sangat penting untuk aplikasi real-time. Jika sebuah thread ditandai sebagai real-time tetapi tidak terikat pada Lightweight Process (LWP), thread tersebut mungkin harus menunggu untuk diikat ke LWP sebelum bisa berjalan. Pertimbangkan jika sebuah thread real-time sedang berjalan (terikat pada LWP) dan kemudian terblokir (misalnya harus melakukan I/O, didahului oleh thread real-time dengan prioritas lebih tinggi, sedang menunggu kunci eksklusi mutual, dll.). Saat thread real-time terblokir, LWP yang terikat padanya telah ditugaskan ke thread lain. Ketika thread real-time dijadwalkan untuk berjalan lagi, ia harus terlebih dahulu menunggu untuk diikat ke LWP. Dengan mengikat LWP ke thread real-time, Anda memastikan bahwa thread tersebut dapat berjalan dengan penundaan minimal setelah dijadwalkan.

#
