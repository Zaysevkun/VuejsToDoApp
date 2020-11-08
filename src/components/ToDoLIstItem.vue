<template>
<li>
  <span><input type="checkbox"></span>
  <strong>{{task.id}}</strong>
  {{ task.title }}
  <button class="rm">&times;</button>
</li>
</template>

<script>
export default {
name: "ToDoLIstItem",
  props:['task'],
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