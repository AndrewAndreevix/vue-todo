<template>
  <div id="app">
    <h1>Todo app</h1>
    <AddTodo @add-todo="addTodo" />
    <hr />
    <TodoList v-bind:todos="todos" @remove-todo="removeTodo" />
  </div>
</template>

<script>
import TodoList from '@/components/TodoList.vue';
import AddTodo from '@/components/AddTodo.vue';
export default {
  name: 'app',
  data() {
    return {
      todos: [
        { id: 1, title: 'buy bread', completed: false },
        { id: 2, title: 'buy butter', completed: false },
        { id: 3, title: 'buy milk', completed: false },
      ],
    };
  },
  components: {
    TodoList,
    AddTodo,
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter((t) => t.id !== id);
    },
    addTodo(todo) {
      this.todos.push(todo);
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
