<template>
  <div id="app">
    <Todos />
  </div> 
</template>

<script>
import Todos from "./components/Todos";


export default {
  name: "app",
  components: {
    Todos,
  },
  
};
</script>
<style >
*{
  box-sizing: border-box;
  margin: 0;
}
body{
      font: 14px 'roboto';
    line-height: 1.4em;
    background: #f5f5f5;
    color: #4d4d4d;
    min-width: 230px;
    max-width: 550px;
    margin: 0 auto;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    font-weight: 300;
}
</style>
