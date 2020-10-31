<template>
  <div>
    <input v-model="newTodoText"/>
    <button @click="addNewTodo">➕</button>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

interface NewTodoFormState {
  newTodoText: string;
}

export default Vue.extend({
  data(): NewTodoFormState {
    return {
      newTodoText: ''
    };
  },
  methods: {
    addNewTodo() {
      this.$emit('todo:create', this.newTodoText);
      this.newTodoText = '';
    }
  }
})
</script>