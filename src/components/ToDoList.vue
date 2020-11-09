<template>
<ul>
  <ToDoLIstItem
  v-for="(task, ind) of tasks" :key="ind"
  v-bind:index="ind"
  v-bind:task="task"
  @deleteTask="deleteTask"
  />
</ul>
</template>

<script>
import ToDoLIstItem from "@/components/ToDoLIstItem";
export default {
  name: "ToDoList",
  props: ['tasks'],
  components: {
    ToDoLIstItem,
  },
  methods: {
    deleteTask(id) {
      this.$emit('deleteTask', id)
    }
  }
}

</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
</style>