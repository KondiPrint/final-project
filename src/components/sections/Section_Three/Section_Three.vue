<!-- Her er en anden måde jeg har brugt 'ref' på, samt en ny funktion, v-model. -->
<!-- v-model binder form inputs til data. -->
<!-- newTask som er en 'ref' holder på den data jeg skriver ind i input og pusher den så ind i den anden 'ref' (task), hvilket så opdaterer array'et med den nye data. -->

<template>
  <div class="container">
    <div class="input-group">
      <label class="input-filled">
        <input required v-model="newTask" @keyup.enter="addTask" />
        <span class="input-label">Add new task</span>
      </label>
      <table>
        <thead>
          <tr>
            <th>Task</th>
            <th>Action</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(task, index) in tasks" :key="index">
            <td @click="toggleCompletion(index)" :class="{ completed: task.completed }">
              {{ task.description }}
            </td>
            <td>
              <button class="btn" @click="deleteTask(index)">Delete</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const tasks = ref([
  { description: 'Learn Vue.js', completed: false },
  { description: 'Build a todo list', completed: false },
  { description: 'Practice coding', completed: true }
])

const newTask = ref('')

const addTask = () => {
  if (newTask.value.trim() !== '') {
    tasks.value.push({ description: newTask.value, completed: false })
    newTask.value = ''
  }
}

const toggleCompletion = (index) => {
  tasks.value[index].completed = !tasks.value[index].completed
}

const deleteTask = (index) => {
  tasks.value.splice(index, 1)
}
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 100%;
  margin: 0 auto;
}

table {
  width: auto;
  border-collapse: collapse;
  margin: 0 auto;
}

th,
td {
  padding: 8px;
  border-bottom: 1px solid aquamarine;
  text-align: center;
  font-size: 1.2rem;
}

.completed {
  text-decoration: line-through;
  font-style: italic;
}

.input-group {
  margin-bottom: 1.5rem;
  position: relative;
  width: auto;
  margin: 0 auto;
}

input {
  border: none;
  border-radius: 6px 6px 0 0;
  border-bottom: 0.3rem solid aquamarine;
  width: 100%;
  height: 3rem;
  font-size: 1.5rem;
  padding-left: 0.5rem;
  padding-top: 1rem;
  padding-bottom: 0.5rem;
  color: #fff;
  background: #222222;
}

.input-filled > .input-label {
  position: absolute;
  top: 10px;
  left: 7px;
  transition: top 0.3s;
  font-size: 1rem;
}

.input-filled > input:hover {
  background: rgb(65, 65, 65);
  border-color: aquamarine;
}

input:focus + .input-label,
input:valid + .input-label {
  top: -30px;
  font-size: 1rem;
  margin-bottom: 32px;
}

input:focus + .input-label {
  color: aquamarine;
}

input:focus {
  border-color: aquamarine;
  outline: none;
  background: rgb(65, 65, 65);
}
</style>
