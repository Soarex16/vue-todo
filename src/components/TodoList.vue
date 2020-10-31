<template>
  <ul>
    <todo-list-item
      v-for="t in todos"
      :key="t.text"
      :todo="t"
      @delete:todo="deleteTodo(t)"
    />
  </ul>
</template>

<script lang="ts">
import Vue, {PropType} from "vue";

import {Todo} from "../types";

import TodoListItem from "./TodoListItem.vue";

export default Vue.extend({
  components: {
    TodoListItem
  },
  props: {
    todos: {
      type: Array as PropType<Todo[]>
    }
  },
  methods: {
    deleteTodo(todo: Todo): void {
      const todoIdx = this.todos.indexOf(todo);
      this.todos.splice(todoIdx, 1);
    }
  }
})
</script>