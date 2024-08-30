<script>
// Options
export default {
  data(){
    return {
      name: "Yago",
      status: 'pending',
      tasks: ['task 1', 'task 2'],
      link: "https://blog.arraialofertas.com/"
    }
  },
  methods: {
    toggleStatus(){
      if(this.status === 'active') {
        this.status = 'pending'
      }else if(this.status === 'pending'){
        this.status = 'inactive'
      }else{
        this.status = 'active'
      }
    }
  }
}
</script>

<template>
  <h1>{{name}}</h1>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <h3>Tasks:</h3>
  <ul>
    <li v-for="task in tasks" :key="task">
      {{ task }}
    </li>
  </ul>
  <a :href="link">Click for my personal Blog</a>

  <button @click="toggleStatus">Change status</button>
</template>

<style scoped>
h1 {
  color: red;
}
</style>
