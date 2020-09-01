<template>
  <div id="app">
    <Todos v-bind:todos="todos" />
  </div>
</template>

<script>
import Todos from "./components/Tododo";
export default {
  name: "App",
  components: {
    Todos,
  },
  data(){
    return{
      todos: [
        {
          id:1,
          todo:'todo 1',
          completed:false
        },
         {
          id:2,
          todo:'todo 2',
          completed:false
        },
         {
          id:3,
          todo:'todo 3',
          completed:false
        }
      ]
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0%;
  padding: 0%;
}
</style>
