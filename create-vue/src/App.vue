<script>
  export default {
    data() {
      return {
        msg: 'Welcome to Your Vue.js App',
        status: 'active'
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
</template>
