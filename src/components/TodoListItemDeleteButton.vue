<template>
  <button @click="deleteTodoClicked">❌</button>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  methods: {
    deleteTodoClicked(): void {
      this.$emit("click");
    }
  }
})
</script>