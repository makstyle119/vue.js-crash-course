<script setup>
  import { ref, onMounted } from 'vue';

  const msg = ref('Welcome to Your Vue.js App');
  const status = ref('active');
  const tasks = ref([
    'Task One',
    'Task Two',
    'Task Three'
  ]);
  const newTask = ref('');

  const link = 'https://www.google.com';
  
  const toggleStatus = () => {
    status.value = status.value === 'active' ? 'inactive' : 'active'
  }

  const addTask = () => {
    if (!newTask.value.trim()) return;
    tasks.value.push(newTask.value);
    newTask.value = '';
  }

  const deleteTask = (index) => {
    tasks.value.splice(index, 1);
  }

  onMounted(async () => {
    try {
      const response = await fetch('https://jsonplaceholder.typicode.com/todos');
      const data = await response.json();
      tasks.value = data.map(task => task.title);
    } catch (error) {
      console.log(error);
    }
  })
</script>

<template>
  <h1>
    {{ msg }}
  </h1>
  <p
    v-if="status === 'active'"
  >
    User is active
  </p>
  <p
    v-else-if="status === 'inactive'"
  >
    User is inactive
  </p>
  <p
    v-else
  >
    User is something
  </p>

  <form 
    @submit.prevent="addTask"
  >
    <label 
      for="newTask"
    >
      Add Task
    </label>
    <input 
      type="text" 
      id="newTask" 
      name="newTask" 
      v-model="newTask"
    >
    <button 
      type="submit"
    >
      Add
    </button>
  </form>

  <h3>
    Tasks:
  </h3>
  <ul>
    <li
      v-for="(task, index) in tasks"
      :key="task"
    >
      <span>
        {{ task }}
      </span>
      <button
        @click="deleteTask(index)"
      >
        x
      </button>
    </li>
  </ul>
  <!-- <a 
    v-bind:href="link"
    target="_blank"
  >
    Click for Google
  </a> -->
  <a 
    :href="link"
    target="_blank"
  >
    Click for Google
  </a>
  <!-- <button
    v-on:click="toggleStatus"
  > -->
  <button
    @click="toggleStatus"
  >
    Change status to inactive
  </button>
</template>
