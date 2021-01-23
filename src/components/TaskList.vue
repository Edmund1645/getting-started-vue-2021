<template>
  <ul>
    <li v-for="(task, index) in todos" v-bind:key="index">
      <span>{{ task }}</span>
      <button @click="deleteTask(task)">delete</button>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'TaskList',
  props: {
    todos: Array,
  },
  methods: {
    deleteTask(task) {
      this.todos = this.todos.filter((item) => item !== task);
    },
  },
};
</script>

<style scoped></style>
