<template>
<ul>
  <ToDoLIstItem
  v-for="task of tasks" :key="task"
  v-bind:task="task"
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