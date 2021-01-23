<template>
  <div id="app">
    <h1>Todo App</h1>
    <input type="text" v-model="todo" /> <button @click="addTodo">Add Task</button>
    <hr />
    <br />
    <br />
    <TaskList v-bind:todos="todos"></TaskList>
  </div>
</template>

<script>
import TaskList from './components/TaskList';
export default {
  name: 'App',
  data() {
    return {
      todo: '',
      todos: [],
    };
  },
  components: {
    TaskList,
  },
  methods: {
    addTodo() {
      if (this.todo.length > 0) {
        this.todos.push(this.todo);
      }
      this.todo = '';
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
