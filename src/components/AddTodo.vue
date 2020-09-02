<template>
  <form @submit="addTodo">
    <input type="text" v-model="title" />
    <button type="submit">Add</button>
  </form>
</template>

<script>


export default {
  name: "AddTodo",
  methods:{
      addTodo(e){
          e.preventDefault();

          const newTodoObj = {
          
          title: this.title,
          completed: false}

          this.$emit('on-new-todo',newTodoObj);
          this.title='';
      }
  }
};
</script>

<style>
</style>