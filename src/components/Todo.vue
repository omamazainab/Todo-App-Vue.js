<template>
  <div v-bind:key="todo.id" v-for="todo in todos">
    <h3>
      <TodoItem v-bind:todo="todo" v-on:markCompleted="$emit(markCompleted)" />
    </h3>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";

export default {
  name: "Todos",
  components: {
    TodoItem,
  },
  props: ["todos"],
  methods: {
    markCompleted() {
      console.log("object");
    },
  },
};
</script>

<style scoped>
</style>>
