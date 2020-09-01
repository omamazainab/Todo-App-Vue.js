<template>
  <div id="app">
    <Todos v-bind:todos="todos" v-on:markCompleted="$emit(markCompleted)" />
  </div>
</template>

<script>
import Todos from "./components/Todo";
export default {
  name: "App",
  components: {
    Todos,
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          task: "todo 1",
          completed: true,
        },
        {
          id: 2,
          task: "todo 2",
          completed: false,
        },
        {
          id: 3,
          task: "todo 3",
          completed: false,
        },
      ],
    };
  },
  methods: {
    markCompleted() {
      console.log("object");
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0%;
  padding: 0%;
}
</style>
