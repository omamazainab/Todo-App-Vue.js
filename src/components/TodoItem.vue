<template>
  <div v-bind:class="{ 'completed': completed }">
    <li>
      <p @click="$emit('on-toggle')">{{ title }}</p>
    </li>
  </div>
</template>
<script>
export default {
  name: "TodoItem",
  props: {
    title: String,
    completed: Boolean
  },
  methods: {
    
  },
};
</script>
<style scoped>
.completed {
  text-decoration: line-through;
}
</style>