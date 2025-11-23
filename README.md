# Assignment: Vue.js – Simple To-Do List
## Identitas
- Nama : Yusri Abdi
- NIM : F1D02310098
---
## Deskripsi Tugas
Pada tugas ini saya membuat aplikasi To-Do List sederhana menggunakan Vue.js.
Aplikasi memiliki fitur:
- **Menambah tugas**

  Pengguna dapat memasukkan teks dan menambahkannya ke daftar melalui fungsi addTask() yang menambahkan nilai baru ke array tasks.
- **Menghapus tugas**

  Setiap item dapat dihapus dengan tombol yang memanggil deleteTask(index) untuk menghapusnya dari array.
- **Menampilkan pesan saat daftar kosong**

  Jika tasks masih kosong, Vue menampilkan pesan "Tidak ada tugas" menggunakan v-if.
- **Menggunakan reaktifitas dengan `ref()`**

  State tasks dan newTask dibuat dengan ref() sehingga setiap perubahan otomatis memperbarui tampilan.
---
## Hasil
### 1. Screenshot Hasil Program
       - <img width="1920" height="1080" alt="Tampilan jika tidak ada list yang ditambahkan" src="https://github.com/user-attachments/assets/a5b74e5a-f9b8-430f-81d2-b54a295d94e5" />
       - <img width="1920" height="1080" alt="Mencoba menambahkan list pada form" src="https://github.com/user-attachments/assets/4aea5c43-5dfd-4794-91b2-daac73aafaa0" />
       - <img width="1920" height="1080" alt="List yangg ditambahkan masuk ke daftar list" src="https://github.com/user-attachments/assets/3d01ef10-a0ee-4e2b-8f26-923004aa9028" />
       - <img width="1920" height="1080" alt="Mencoba menambahkan 1 list lagi" src="https://github.com/user-attachments/assets/4f4b6897-c55e-4d61-88ad-68424e202d90" />
       - <img width="1920" height="1080" alt="List terakhir masuk ke daftar" src="https://github.com/user-attachments/assets/325ad974-ace9-4ce2-97c9-063e1d85164b" />
       - <img width="1920" height="1080" alt="Menghapus List yang typo dengan menekan button hapus yang berwarna merah" src="https://github.com/user-attachments/assets/97903194-b68e-4551-a5de-22a1719b6b73" />
       - <img width="1920" height="1080" alt="List yang ditekan button hapus akan terhapus dari daftar list" src="https://github.com/user-attachments/assets/2e42bf20-0325-46ba-a56b-c0f91f9e5f34" />
### 2. Penjelasan Singkat
Jelaskan bagian penting, misalnya:
- bagaimana `addTask()` bekerja
- bagaimana data ditampilkan menggunakan `v-for`

- cara kerja tombol hapus
---
