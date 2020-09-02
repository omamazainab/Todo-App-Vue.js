<template>
  <div>
    <li>
      <button
        v-if="!isEditing"
        @click="$emit('on-toggle')"
        v-bind:class="{ 'completed': completed }"
      >
        <span>{{ title }}</span>
      </button>
      <form v-else @submit.prevent="finishEditing()">
        <input type="text" ref="newTodo" v-model="newTodoTitle" @blur="finishEditing()" />
      </form>
      <button class="edit" @click="startEditing()">edit</button>
      <button class="delete" @click="$emit('on-delete')">x</button>
    </li>
  </div>
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
    }
  },
  data() {
    return {
      isEditing: false,
      newTodoTitle: ""
    };
  },
};
</script>
<style scoped>
.completed {
  text-decoration: line-through;
}
</style>