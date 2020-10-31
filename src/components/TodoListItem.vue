<template>
  <li>
    {{ todo.text }}
    <input type="checkbox" checked="todo.completed" />
    <todo-list-item-delete-button @click="deleteTodo"/>
  </li>
</template>

<script lang="ts">
import Vue, {PropType} from "vue";

import {Todo} from "../types";

import TodoListItemDeleteButton from "./TodoListItemDeleteButton.vue";

export default Vue.extend({
  components: {
    TodoListItemDeleteButton
  },
  props: {
    todo: Object as PropType<Todo>
  },
  methods: {
    deleteTodo() {
      this.$emit("delete:todo")
    }
  }
})
</script>

<style scoped>

</style>