<template>
  <div id="app">
    <h1>ToDo List</h1>
    <hr>
    <ToDoList
    v-bind:tasks="tasks"/>
  </div>
</template>

<script>
import ToDoList from "@/components/ToDoList";

export default {
  name: 'App',
  data() {
    return {
      tasks: [
        {id: 1, title: "task 1", completed: false},
        {id: 2, title: "task 2", completed: false},
        {id: 3, title: "task 3", completed: false}
      ]
    }
  },
  components: {
    ToDoList,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
