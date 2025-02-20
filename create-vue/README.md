# create-vue

## Styling
```html
<style scoped> 
/* you scoped if you want to style only this component */
</style>
```

## Options API
```html
<script>
  export default {
    data() { // data is a function
      return { // return an object
        msg: 'Welcome to Your Vue.js App' // msg is a property
        // this object can contain anything
      }
    },
    methods: {
      toggleStatus() {
        this.status = this.status === 'active' ? 'inactive' : 'active'
      }
    }
  }
</script>
```

## Composition API - Long Form
```html
<script>
  export default {
    setup() {
      const msg = 'Welcome to Your Vue.js App';
      const status = 'active';
      const tasks = [
        'Task One',
        'Task Two',
        'Task Three'
      ];
      const link = 'https://www.google.com';
      const toggleStatus = () => {
        this.status = this.status === 'active' ? 'inactive' : 'active'
      }

      return {
        msg,
        status,
        tasks,
        link,
        toggleStatus
      }
    }
  }
</script>
```

## Composition API - Short Form
```html
<script setup>
  import { ref } from 'vue';

  const msg = ref('Welcome to Your Vue.js App');
  const status = ref('active');
  const tasks = ref([
    'Task One',
    'Task Two',
    'Task Three'
  ]);
  const link = 'https://www.google.com';
  const toggleStatus = () => {
    status.value = status.value === 'active' ? 'inactive' : 'active'
  }
</script>
```

## Directives
### v-if, v-else-if, v-else
````html
    <p
        v-if="status === 'active'"
    >   
        <!-- v-if is simple if condition -->
        User is active
    </p>
    <p
        v-else-if="status === 'inactive'"
    >
        <!-- v-else-if is simple else if condition -->
        User is inactive
    </p>
    <p
        v-else
    >
        <!-- v-else is simple else condition -->
        User is something
    </p>
````

### v-for
````html
    <ul>
      <li
        v-for="task in tasks"
        :key="task"
      >
        {{ task }}
      </li>
    </ul>
````

### v-bind
````html
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
````

### v-on
````html
  <!-- <button
    v-on:click="toggleStatus"
  > -->
  <button
    @click="toggleStatus"
  >
    Change status to inactive
  </button>
````

## Form
### @submit
  - use to submit a form
### @submit.prevent
  - use to prevent a form from submitting
### v-model
  - use to bind a form input to a variable
````html
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
````

## button
### @click
  - use to bind a button to a function
````html
  <button
    @click="deleteTask(index)"
  >
    x
  </button>
````
