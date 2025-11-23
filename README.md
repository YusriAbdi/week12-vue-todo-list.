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
       - Screenshot/Tampilan jika tidak ada list yang ditambahkan.png
       - Screenshot/Mencoba menambahkan list pada form.png
       - Screenshot/List yangg ditambahkan masuk ke daftar list.png
       - Screenshot/Mencoba menambahkan 1 list lagi.png
       - Screenshot/List terakhir masuk ke daftar.png
       - Screenshot/Menghapus List yang typo dengan menekan button hapus yang berwarna merah.png
       - Screenshot/List yang ditekan button hapus akan terhapus dari daftar list.png
### 2. Penjelasan Singkat
Penjelasan kode:
- `addTask()`
  ```
  const addTask = () => {
    if (newTask.value.trim() === '') return
    tasks.value.push(newTask.value)
    newTask.value = ''
  }
  ```
  Fungsi addTask() digunakan untuk menambahkan tugas baru ke dalam daftar dengan cara memeriksa terlebih dahulu apakah input tidak kosong menggunakan trim(), kemudian memasukkan nilai newTask ke array tasks melalui tasks.value.push(), dan setelah tugas berhasil ditambahkan, nilai input dikosongkan kembali dengan mengatur newTask.value menjadi string kosong; proses ini memanfaatkan reaktivitas Vue sehingga setiap perubahan langsung memperbarui tampilan daftar tugas tanpa perlu memuat ulang halaman.
- `deleteTask`
  ```
  const deleteTask = (index) => {
    tasks.value.splice(index, 1)
  }
  ```
  Fungsi deleteTask(index) digunakan untuk menghapus tugas tertentu dari daftar dengan mengambil posisi item melalui parameter index, lalu menghapusnya menggunakan tasks.value.splice(index, 1), sehingga elemen pada indeks tersebut langsung hilang dari array dan daftar tugas pada tampilan otomatis diperbarui berkat reaktivitas Vue.
- `v-model`
  ```
  <form @submit.prevent="addTask" class="task-form">
      <input
        v-model="newTask"
        type="text"
        placeholder="Tambahkan tugas..."
        class="task-input"
      />
      <button type="submit" class="btn-add">Tambah</button>
  </form>
  ```
  Bagian `<form>` ini berfungsi sebagai tempat pengguna menambahkan tugas baru, di mana input teks terhubung ke variabel newTask melalui v-model sehingga setiap perubahan langsung tersimpan dalam state, lalu saat form dikirim tombol submit akan memicu fungsi addTask() melalui @submit.prevent="addTask" untuk memasukkan tugas tersebut ke dalam daftar tanpa me-reload halaman.
- `v-for`
  ```
  <li
        v-for="(task, index) in tasks"
        :key="index"
        class="task-item"
      >
        {{ task }}

        <button @click="deleteTask(index)" class="btn-delete">
          Hapus
        </button>
  </li>
  ```
  Kode <li> ini menampilkan setiap tugas dalam daftar menggunakan v-for yang melakukan perulangan pada array tasks, dengan index sebagai kunci unik melalui :key="index" untuk menjaga performa render, lalu menampilkan isi tugas dan menyediakan tombol "Hapus" yang memanggil deleteTask(index) sehingga item tersebut dapat dihapus langsung dari daftar secara dinamis.
- `v-if` dan `v-else`
  ```<p v-if="tasks.length === 0" class="empty-text">
      Tidak ada tugas
    </p>

    <!-- Jika ada tugas -->
    <ul v-else class="task-list">
      <li
        v-for="(task, index) in tasks"
        :key="index"
        class="task-item"
      >
        {{ task }}

        <button @click="deleteTask(index)" class="btn-delete">
          Hapus
        </button>
      </li>
    </ul>
  ```
  Bagian ini digunakan untuk menampilkan kondisi daftar tugas, di mana elemen <p> dengan v-if="tasks.length === 0" akan muncul sebagai pesan “Tidak ada tugas” ketika array masih kosong, sedangkan <ul v-else> akan menampilkan daftar tugas menggunakan v-for jika terdapat item di dalam array, lengkap dengan tombol "Hapus" yang memungkinkan pengguna menghilangkan tugas tersebut secara langsung dari daftar.

---
