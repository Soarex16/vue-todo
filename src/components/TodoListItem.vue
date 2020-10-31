<template>
  <li>
    {{ todo.text }}

    <input
      type="checkbox"
      v-model="todo.completed"
    />
    
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
      this.$emit("todo:delete")
    }
  }
})
</script>

<style scoped>

</style>