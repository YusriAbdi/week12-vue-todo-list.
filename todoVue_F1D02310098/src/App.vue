<script setup>
import { ref } from 'vue'
import './assets/style.css'

// STATE
const tasks = ref([])      
const newTask = ref('')

// Tambah tugas
const addTask = () => {
  if (newTask.value.trim() === '') return
  tasks.value.push(newTask.value)
  newTask.value = ''
}

// Hapus tugas
const deleteTask = (index) => {
  tasks.value.splice(index, 1)
}
</script>

<template>
  <div class="container">

    <h1>To-Do List with Vue.js</h1>

    <!-- Form input tugas -->
    <form @submit.prevent="addTask" class="task-form">
      <input
        v-model="newTask"
        type="text"
        placeholder="Tambahkan tugas..."
        class="task-input"
      />
      <button type="submit" class="btn-add">Tambah</button>
    </form>

    <!-- Jika kosong -->
    <p v-if="tasks.length === 0" class="empty-text">
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

  </div>
</template>