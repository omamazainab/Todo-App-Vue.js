<template>
  <div v-bind:class="{ 'completed': todo.completed }">
    <p v-on:click="markComplete">{{ todo.title }}</p>
  </div>
</template>
<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
      this.$emit("complete", this.todo.id);
      console.log(this.todo.id);
    },
  },
};
</script>
<style scoped>
.completed {
  text-decoration: line-through;
}
</style>