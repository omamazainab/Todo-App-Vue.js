<template>
  <form @submit.prevent="addTodo()">
    <input class="new-todo no-focus" type="text" v-model="newTodo" placeholder="Create a new to-do..." />
  </form>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      newTodo: "",
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo.length > 0) {
        this.$emit("on-new-todo", { title: this.newTodo, completed: false });
      }
      this.newTodo = "";
    },
  },
};
</script>

<style scoped>
.new-todo {
  padding: 16px 16px 16px 60px;
  border: none;
  background: rgba(0, 0, 0, 0.003);
  box-shadow: inset 0 -2px 1px rgba(0, 0, 0, 0.03);
  margin: 0;
    width: 100%;
    font-size: 24px;
    font-family: inherit;
    font-weight: inherit;
    line-height: 1.4em;
}

.no-focus{
  outline: none;
  border: none;
}
</style>