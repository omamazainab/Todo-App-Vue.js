<template>
  <div>
    <ul>
      <TodoItem
        v-for="(todo,index) in todos"
        :key="index"
        :title="todo.title"
        :completed="todo.completed"
        @on-toggle="toggleTodo(todo)"
        @on-delete="deleteTodo(todo)"
        @on-edit="editTodo(todo,$event)"
      />
      <AddTodo @on-new-todo="addTodo($event)" />
    </ul>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";
import AddTodo from "./AddTodo";

export default {
  name: "Todos",
  components: {
    TodoItem,
    AddTodo,
  },

  data() {
    return {
      todos: [
        {
          title: "Go workout",
          completed: true,
        },
        {
          title: "Do laundry",
          completed: false,
        },
        {
          title: "Cook food",
          completed: false,
        },
        {
          title: "Clean up room",
          completed: false,
        },
        {
          title: "Finish work",
          completed: false,
        },
      ],
    };
  },
  methods: {
    addTodo(newTodo) {
      this.todos.push(newTodo);
    },
    toggleTodo(todo) {
      todo.completed = !todo.completed;
    },
    deleteTodo(deletedTodo) {
      this.todos = this.todos.filter((todo) => todo !== deletedTodo);
    },
    editTodo(todo,title){
        todo.title = title;
    }
  },
};
</script>

<style>
</style>