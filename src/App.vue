<template>
  <div id="app">
    <Todos 
      v-bind:todos="todos"
      v-on:del-todo="deleteTodo"
    />
  </div>
</template>

<script>
import Todos from './components/Todos';

export default {
  name: 'App',
  components: {
    Todos,
  },
  data() {
    return {
      todos: [
        { title: 'Learn Vue js', id: 1, completed: false },
        { title: 'Learn TypeScript', id: 2, completed: true },
        { title: 'Develop Test Task', id: 3, completed: false },
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
</style>
