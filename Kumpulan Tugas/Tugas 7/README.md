# Tugas 7
1. Tugas Pendahuluan
- Apa yang dimaksud redirection?
   - Proses mengarahkan input/output dari suatu perintah atau program ke tempat atau aliran yang berbeda.
- Apa yang dimaksud pipeline?
   - Sebuah konsep yang memungkinkan pengguna untuk menghubungkan keluaran (output) dari satu perintah atau program dengan masukan (input) dari perintah atau program berikutnya.
- Apa yang dimaksud perintah di bawah ini : echo, cat, more, sort, grep, wc, cut, uniq
   - echo, menampilkan teks atau nilai variabel ke layar.
   - cat, menampilkan atau menggabungkan isi dari satu atau beberapa file.
   - more, menampilkan isi dari suatu file satu layar pada satu waktu.
   - sort, untuk mengurutkan baris-baris teks dalam suatu file atau output dari perintah lain.
   - grep, untuk mencari pola teks dalam suatu file atau output dari perintah lain.
   - wc, untuk menghitung jumlah baris, kata, dan byte dalam suatu file atau output dari perintah lain.
   - cut, untuk memotong (mengambil sebagian) kolom dari setiap baris dalam suatu file atau output dari perintah lain berdasarkan delimiter tertentu.
   - uniq, untuk menghilangkan baris duplikat dari suatu file atau output dari perintah lain.

2. Percobaan
- Percobaan 1 File Descriptor
   1. Output ke layar (standar output), input dari system (kernel)
      - $ ps
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/a56510bc-9fb8-4242-ab3f-507724fa40d7)

   2. Output ke layar (standar output), input dari keyboard (standard input)
      - $ cat
      - hallo, apa khabar
      - hallo, apa khabar
      - exit dengan ^d
      - exit dengan ^d
      - [Ctrl-d]
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/342987e8-50ee-442e-a898-543623b33151)

   3. Input nama direktori, output tidak ada (membuat direktori baru), bila terjadi error maka tampilan error pada layar (standard error)
      - $ mkdir mydir
      - $ mkdir mydir **(Terdapat pesan error)**
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/b8ccd23f-a5e9-4adc-9186-2c9a91c661b0)

- Percobaan 2 Pembelokan (Redirection)
   1. Pembelokan standar output
      - $ cat 1> myfile.txt
      - Ini adalah teks yang saya simpan ke file myfile.txt
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/804e2491-719c-4fab-b91e-efea4b2fc935)

   2. Pembelokan standar input, yaitu input dibelokkan dari keyboard menjadi dari file
      - $ cat 0< myfile.txt
      - $ cat myfile.txt
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/17b4fedd-4262-411b-ab33-05413c40433e)

   3. Pembelokan standar error untuk disimpan di file
      - $ mkdir mydir (Terdapat pesan error)
      - $ mkdir mydir 2> myerror.txt
      - $ cat myerror.txt
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/be0bf6ae-8fe5-4285-bbe2-01b5fa07318f)

   4. Notasi 2>&1 : pembelokan standar error (2>) adalah identik dengan file descriptor 1.
      - $ ls filebaru (Terdapat pesan error)
      - $ ls filebaru 2> out.txt
      - $ cat out.txt
      - $ ls filebaru 2> out.txt 2>&
      - $ cat out.txt
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/601482bc-1866-4108-b315-824380ccd7d9)

   5. Notasi 1>&2 (atau >&2) : pembelokan standar output adalah sama dengan file descriptor 2 yaitu standar error
      - $ echo “mencoba menulis file” 1> baru
      - $ cat filebaru 2> baru 1>&
      - $ cat baru
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/933f9a77-de18-4285-b31e-2bdc3c41cc63)

   6. Notasi >> (append)
      - $ echo “kata pertama” > surat
      - $ echo “kata kedua” >> surat
      - $ echo “kata ketiga” >> surat
      - $ cat surat
      - $ echo “kata keempat” > surat
      - $ cat surat
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/67ba1aba-e3d6-4682-986f-c8becfad5142)

   7. Notasi here document (<<++ .... ++) digunakan sebagai pembatas input dari keyboard. Perhatikan bahwa tanda pembatas dapat digantikan dengan tanda apa saja, namun harus sama dan tanda penutup harus diberikan pada awal baris
      - $ cat <<++
      - Hallo, apa kabar?
      - Baik-baik saja?
      - Ok!
      - ++
      - $ cat <<%%%
      - Hallo, apa kabar?
      - Baik-baik saja?
      - Ok!
      - %%%
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/bf9b647a-4061-4823-bf41-bf0c80fea4fc)

   8. Notasi – (input keyboard) adalah representan input dari keyboard. Artinya menampilkan file 1, kemudian menampilkan input dari keyboard dan menampilkan file 2. Perhatikan bahwa notasi “-“ berarti menyelipkan input dari keyboard
      - $ cat myfile.txt – surat
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/7e82b2f3-ad14-445f-a386-5ca68ee5daa6)

- Percobaan 3 Pipa (Pipeline)
   1. Operator pipa (|) digunakan untuk membuat eksekusi proses dengan melewati data langsung ke data lainnya.
      - $ who
      - $ who | sort
      - $ who | sort –r
      - $ who > tmp
      - $ sort tmp
      - $ rm tmp
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/e81f072d-9313-4f22-9dab-34da5dd8c8b8)

      - $ ls –l /etc | more
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/d494aa57-315c-479d-b228-0f83f83a6256)

      - $ ls –l /etc | sort | more
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/69c84472-d02e-4c56-ba95-875353650ed4)

   2. Untuk membelokkan standart output ke file, digunakan operator ">"
      - $ echo hello
      - $ echo hello > output
      - $ cat output
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/b2dd5141-ebf5-4fa7-94af-73739a2e904d)

   3. Untuk menambahkan output ke file digunakan operator ">>"
      - $ echo bye >> output
      - $ cat output
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/c9c04d79-b7bc-439e-b338-ef921ba16b3b)

   4. Untuk membelokkan standart input digunakan operator "<"
      - $ cat < output
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/58aaa0d5-cffe-4499-b5fa-7eb4e94c50aa)

   5. Pembelokan standart input dan standart output dapat dikombinasikan tetapi tidak boleh menggunakan nama file yang sama sebagai standart input dan output.
      - $ cat < output > out
      - $ cat out
      - $ cat < output >> out
      - $ cat out
      - $ cat < output > output
      - $ cat output
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/295ae765-9846-43f3-a883-3ddd455737d2)

      - $ cat < out >> out (Proses tidak berhenti)
      [Ctrl-c]
      - $ cat out
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/a670b63d-35f9-4389-9401-fd758d17657f)

- Percobaan 4 Filter
   1. Pipa juga digunakan untuk mengkombinasikan utilitas sistem untuk membentuk fungsi yang lebih kompleks
      - $ w –h | grep <user>
      - $ grep <user> /etc/passwd
      - $ ls /etc | wc
      - $ ls /etc | wc –l
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/e37a8dab-ea3c-4ebb-989c-75f2fe77002b)

      - $ cat > kelas1.txt
      - Badu
      - Zulkifli
      - Yulizir
      - Yudi
      - Ade
      - [Ctrl-d]
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/045135bc-ac0d-4ad7-8d55-0494588d2220)

      - $ cat > kelas2.txt
      - Budi
      - Gama
      - Asep
      - Muchlis
      - [Ctrl-d]
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/f38138ff-9a5c-4df8-b7c8-aaaa8a95d91c)

      - $ cat kelas1.txt kelas2.txt | sort
      - $ cat kelas1.txt kelas2.txt > kelas.txt
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/96de7d97-fcd0-4f7b-a249-300211ed5bf0)

      - $ cat kelas.txt | sort | uniq
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/6db8d10b-73e2-43e4-8be9-5aa339f2617c)
  
3. Latihan
   - Lihat daftar secara lengkap pada direktori aktif, belokkan tampilan standard output ke file baru.
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/bb05f53a-3ced-43fa-a241-2aecb45de378)

   - Lihat daftar secara lengkap pada direktori /etc/passwd, belokkan tampilan standard output ke file baru tanpa menghapus file baru sebelumnya.
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/abfe3bb5-c0ad-49ee-90b9-e71a95b6f834)

   - Urutkan file baru dengan cara membelokkan standard input.
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/e90e42eb-d96c-407f-8104-97be8e240bd9)

   - Urutkan file baru dengan cara membelokkan standard input dan standard output ke file baru.urut.
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/89c6dcc2-7365-40a0-9694-fcc485e5d843)

   - Buatlah direktori latihan 2 sebanyak 2 kali dan belokkan standard error ke file rmdirerror.txt.
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/b670f4d9-576a-4ba0-a08d-61f3ac077cf5)

   - Urutkan kalimat berikut :
   - Jakarta
   - Bandung
   - Surabaya
   - Padang
   - Palembang
   - Lampung
   - Dengan menggunakan notasi here document (<@@@ ...@@@) .
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/9470eec5-52ca-432f-bf9c-d825bfbc3702)

   - Hitung jumlah baris, kata dan karakter dari file baru.urut dengan menggunakan filter dan tambahkan data tersebut ke file baru.
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/de840e3c-6647-4d18-bd64-0db6ffd6cbf2)

   - Gunakan perintah di bawah ini dan perhatikan hasilnya.
      - $ cat > hello.txt
      - dog cat
      - cat duck
      - dog chicken
      - chicken duck
      - chicken cat
      - dog duck
      - [Ctrl-d]
      - $ cat hello.txt | sort | uniq
      - $ cat hello.txt | grep “dog” | grep –v “cat”
      - ![image](https://github.com/DimasIvandaFauzi/SysOP24-3123521022/assets/160553968/16ceec8a-8ee9-46fe-aee0-b2747928ef5b)
#
