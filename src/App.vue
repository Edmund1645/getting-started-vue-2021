<template>
  <div id="app">
    <h1>Todo App</h1>
    <input type="text" v-model="todo" /> <button @click="addTodo">Add Task</button>
    <hr />
    <br />
    <br />
    <ul>
      <li v-for="(task, index) in todos" v-bind:key="index">
        <span>{{ task.toUpperCase() }}</span>
        <button @click="deleteTask(task)">delete</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      todo: '',
      todos: [],
    };
  },
  methods: {
    addTodo() {
      if (this.todo.length > 0) {
        this.todos.push(this.todo);
      }
      this.todo = '';
    },
    deleteTask(task) {
      this.todos = this.todos.filter((item) => item !== task);
    },
  },
};
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
