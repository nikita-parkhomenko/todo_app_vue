<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <h3>
      <input type="checkbox" v-on:change="toggleComplete">
      {{todo.title}}
      <button 
        @click="$emit('del-todo', todo.id)"
        class="del"
      >
        x
      </button>
    </h3>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ["todo"],
  methods: {
    toggleComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }
}
</script>

<style scoped>
  .todo-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
  }
  .is-complete {
    text-decoration: line-through;
  }
  .del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    outline: none;
    cursor: pointer;
    float: right;
  }
</style>