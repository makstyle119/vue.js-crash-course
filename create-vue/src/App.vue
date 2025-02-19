<script>
  export default {
    data() {
      return {
        msg: 'Welcome to Your Vue.js App',
        status: 'active',
        task: [
          'Task One',
          'Task Two',
          'Task Three'
        ],
        link: 'https://www.google.com'
      }
    },
    methods: {
      toggleStatus() {
        this.status = this.status === 'active' ? 'inactive' : 'active'
      }
    }
  }
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
  <h3>
    Tasks:
  </h3>
  <ul>
    <li
      v-for="task in tasks"
      :key="task"
    >
      {{ task }}
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
