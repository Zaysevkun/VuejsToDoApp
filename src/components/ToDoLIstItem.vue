<template>
<li v-bind:class="{completed: task.completed}">
  <span><input type="checkbox" @change="
  task.completed = !task.completed">
  <strong>{{index + 1}}</strong>
  </span>
  {{ task.title }}
  <button class="rm" @click="$emit('deleteTask', task.id)">&times;</button>
</li>
</template>

<script>
export default {
name: "ToDoLIstItem",
  props: {
  task: {
    type: Object,
    required: true
  },
    index: Number
  },
}
</script>

<style scoped>
input {
  margin-right: 1rem;
}
li {
  border: 1px solid #ccc;
  display: flex;
  justify-content: space-between;
  padding: .5rem 2rem;
  margin-bottom: 1rem;
}

.rm {
  background: #cc0000;
  color: #fff;
  border-radius: 30%;
  border: none;
}

.completed {
  background: #39b445;
}
</style>