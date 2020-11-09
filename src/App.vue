<template>
  <div id="app">
    <h1>ToDo List</h1>
    <hr>
    <AddTask
    @addTask="addTask"
    />
    <ToDoList
    v-bind:tasks="tasks"
    @deleteTask="deleteTask"/>
  </div>
</template>

<script>
import ToDoList from "@/components/ToDoList";
import AddTask from "@/components/AddTask";

export default {
  name: 'App',
  data() {
    return {
      tasks: [
        {id: 1, title: "This is how your task will be showed, when you add one", completed: false},
      ]
    }
  },
  components: {
    ToDoList,
    AddTask,
  },
  methods: {
    deleteTask(id) {
      this.tasks = this.tasks.filter(t => t.id !== id)
    },

    addTask(task) {
      console.log('outer nigga', task.title)
      this.tasks.push(task)
    }
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
