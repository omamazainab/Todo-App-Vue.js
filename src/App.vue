<template>
  <div id="app">
    <Todos />
    <!-- <AddTodo v-on:add-todo="addTodo" /> -->
  </div>
</template>

<script>
import Todos from "./components/Todos";
// import AddTodo from "./components/AddTodo";

export default {
  name: "app",
  components: {
    Todos,
    // AddTodo,
  },
  
};
</script>
<style>
</style>