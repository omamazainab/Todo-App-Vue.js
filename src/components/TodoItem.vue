<template>
  <li class="todo-item">
    <button
      class="btn flex-2"
      v-if="!isEditing"
      @click="$emit('on-toggle')"
      v-bind:class="{ 'completed': completed }"
    >
      <span>{{ title }}</span>
    </button>
    <form v-else @submit.prevent="finishEditing()" class="flex-2">
      <input type="text" ref="newTodo" v-model="newTodoTitle" @blur="finishEditing()" class="no-focus full-width" />
    </form>
    <div class="btn-container">
      <button class="btn edit" @click="startEditing()">edit</button>
    <button class="btn delete" @click="$emit('on-delete')">x</button>
    </div>
    </li>
</template>
<script>
export default {
  name: "TodoItem",
  props: {
    title: String,
    completed: Boolean,
  },
  methods: {
    startEditing() {
      if (this.isEditing) {
        this.finishEditing();
      } else {
        this.newTodoTitle = this.title;
        this.isEditing = true;
        this.$nextTick(() => this.$refs.newTodo.focus());
      }
    },
    finishEditing() {
      this.isEditing = false;
      this.$emit("on-edit", this.newTodoTitle);
    },
  },
  data() {
    return {
      isEditing: false,
      newTodoTitle: "",
    };
  },
};
</script>
<style scoped>
.completed {
  text-decoration: line-through;
}
.btn {
  background: transparent;
  border: transparent;
}
.btn-container{
  display: inline-block;
}
.todo-item{
  display: flex;
  justify-content: space-between;
  padding: 10px;
}

.flex-2{
  flex: 2;
  text-align: left;
}

.full-width{
  width: 100%;
}

button:focus{
  outline: none;
}

.no-focus{
  outline: none;
  border: none;
}

</style>