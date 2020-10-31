<template>
  <div id="app">
    <new-todo-form @create:todo="createTodo" />
    <todo-list :todos="todos" />
  </div>
</template>

<script lang="ts">
import Vue from "vue";

import {Todo} from "./types";

import TodoList from "./components/TodoList.vue";
import NewTodoForm from "./components/NewTodoForm.vue";

interface TodoListState {
  todos: Todo[];
}

export default Vue.extend({
  name: "App",
  components: {
    NewTodoForm,
    TodoList
  },
  data(): TodoListState {
    return {
      todos: [
        {
          text: "Todo 1",
          completed: false
        },
        {
          text: "Todo 2",
          completed: false
        }
      ]
    };
  },
  methods: {
    createTodo(text: string) {
      this.todos.push({
        text: text,
        completed: false
      });
    }
  }
});
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
