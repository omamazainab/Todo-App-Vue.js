<template>
  <div class="todo-item" >
    <p>
      <input type="checkbox" @change="$emit(markCompleted)" />
      {{todo.task}}
      <button class="del">x</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markCompleted() {
console.log('object')    },
  },
};
</script>

<style>
.todo-item {
  background-color: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #ccc dotted;
}

.is-completed {
  text-decoration: line-through;
}

.del {
  background-color: red;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  position: relative;
  right: 0px;
}
</style>                       