<template>
  <form @submit.prevent="onSubmit">
    <input
        type="text"
        placeholder="input your task here"
        v-model="title"
    >
    <button
        type="submit"
    >Create</button>
  </form>
</template>

<script>
export default {
name: "AddTask",
  methods: {
  onSubmit() {
    console.log('success', this.title)
    if (this.title.trim()) {
      const Task = {
        id: Date.now(),
        title: this.title,
        completed: false
      }

      this.$emit('addTask', Task)
      this.title = ''
    }
  }
  },
  data() {
  return {
    title: ''
  }
  }
}
</script>

<style scoped>
button {
  float: right;
  background: cornflowerblue;
  border-radius: 10%;
  color: #fff;
  border: none;
}
input {
  width: 100%;
  border-right: none;
  border-left: none;
  border-top: none;
}
form {
  display: flex;
  justify-content: space-between;
  padding: .5rem 2rem;
  margin-bottom: 1rem;
  width: 500px;
  overflow: hidden;
}
</style>