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
    }
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
```